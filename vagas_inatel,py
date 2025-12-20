from bs4 import BeautifulSoup
from datetime import date
import requests
import csv
import os

# --- CONFIGURAÇÃO DO BOT ---
TOKEN_BOT = "SEU_TOKEN_AQUI"
MEU_CHAT_ID = "SEU_USER_ID_DO_TELEGRAM_AQUI"

def enviar_telegram(mensagem):
    url = f"https://api.telegram.org/bot{TOKEN_BOT}/sendMessage"
    dados = {"chat_id": MEU_CHAT_ID, "text": mensagem, "parse_mode": "Markdown"}
    try:
        requests.post(url, data=dados)
    except Exception as e:
        print(f"Erro ao avisar no Telegram: {e}")

# --- CONFIGURAÇÕES ---
base_url = "https://inatel.br"
url_inicial = "https://inatel.br/estudante/vagas/estagio?page="
historico = "vagas_estagio_inatel.csv"
links_antigos = set()

# 1. Carregar links antigos para saber o que já foi avisado
if os.path.exists(historico):
    with open(historico, "r", encoding="utf-8") as arquivo:
        reader = csv.DictReader(arquivo)
        for linha in reader:
            links_antigos.add(linha["Link"])

# 2. Listas para guardar o que vamos encontrar hoje
todas_as_vagas_atuais = []
novas_vagas_count = 0

print("INICIANDO SCRAPING...")

start = 1
while start <= 10:
    url_final = url_inicial + str(start)
    requisicao = requests.get(url_final)
    
    if requisicao.status_code != 200: break

    site = BeautifulSoup(requisicao.content, "html.parser")
    vagas = site.find_all("a", class_="boxLink")

    if not vagas: break
    
    for vaga in vagas:
        texto = vaga.text.strip()
        link_completo = base_url + vaga.get("href")

        if "/" in texto:
            titulo, empresa = texto.split("/", 1)
        else:
            titulo, empresa = texto, "Não informado" 

        # Colocamos os dados em um dicionario
        dados_vaga = {
            "Titulo": titulo.strip(),
            "Empresa": empresa.strip(),
            "Link": link_completo,
            "Página": start
        }
        
        # Guardamos na nossa lista de "Vagas que estão no site agora"
        todas_as_vagas_atuais.append(dados_vaga)

        # SE FOR NOVA: Avisa no Telegram
        if link_completo not in links_antigos:
            print(f"🆕 NOVIDADE: {titulo.strip()}")
            #Só avisa as 12 novas vagas para caso seja a primeira vez rodando nao mandar de todas paginas e sobrecarregar
            if novas_vagas_count <=12:
                msg = (
                    f"🚀 *NOVA VAGA NO INATEL!*\n\n"
                    f"📌 *Vaga:* {titulo.strip()}\n"
                    f"🏢 *Empresa:* {empresa.strip()}\n"
                    f"🔗 [Clique aqui para ver]({link_completo})"
                )
                enviar_telegram(msg)
            novas_vagas_count += 1

    print(f"Página {start} processada.")
    start += 1


# 3. Agora reescrevemos o histórico do zero ("w") apenas com o que encontramos na run atual
hoje = date.today().strftime("%d-%m-%Y")
arquivo_hoje = f"vagas_estagio_inatel_{hoje}.csv"
campos = ["Titulo", "Empresa", "Link", "Página"]

# Função auxiliar para salvar o arquivo (evita repetir código)
def salvar_csv(nome_arquivo, lista_dados):
    with open(nome_arquivo, "w", newline="", encoding="utf-8") as f:
        writer = csv.DictWriter(f, fieldnames=campos)
        writer.writeheader()
        writer.writerows(lista_dados) # Escreve a lista inteira de uma vez!

# Salvamos o Histórico Atualizado (Apenas com o que está no site agora)
salvar_csv(historico, todas_as_vagas_atuais)

# Salvamos a "Xerox" do dia (Exatamente os mesmos dados)
salvar_csv(arquivo_hoje, todas_as_vagas_atuais)


print("Processo finalizado")

if(novas_vagas_count) > 12:
    print("12 novas vagas enviadas no telegram🚀")
else:
    print(f"{novas_vagas_count} novas vagas enviadas no telegram🚀")

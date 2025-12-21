---

# 🚀 Inatel Job Hunter: Monitorização Automatizada de Vagas

Sistema de automação desenvolvido em Python para a recolha, monitorização e notificação em tempo real de vagas de estágio publicadas no portal oficial do Inatel (Instituto Nacional de Telecomunicações).

---

## 🎯 Objetivo do Projeto

Este projeto foi desenvolvido como um estudo prático sobre Web Scraping e Integração de APIs. O objetivo principal é otimizar o acompanhamento de novas oportunidades, eliminando a verificação manual constante.

A motivação surgiu durante o 2º período de Engenharia de Software, procurando aplicar conceitos de extração de dados para auxiliar os estudantes do Inatel a receberem a informação da vaga o mais rápido possível, facilitando o acesso ao primeiro estágio.

---

## ✨ Funcionalidades

* 🔍 **Extração de Dados (Scraping):** Varredura inteligente das páginas de estágio utilizando BeautifulSoup4.
* 🔄 **Sincronização de Histórico:** Mantém uma base local (CSV) sincronizada. Se uma vaga for removida do portal, o robô deteta e limpa o histórico, permitindo novos alertas caso a vaga reabra.
* 📱 **Notificação Remota:** Integração com a API do Telegram para envio imediato de detalhes (Título, Empresa e Link), com um sistema de proteção contra spam na primeira execução.
* 📄 **Persistência de Dados:** Geração automática de relatórios diários datados para conferência manual.
* ☁️ **Execução em Nuvem:** Automatizado via GitHub Actions para rodar diariamente sem necessidade de ligar o computador local. **(Novo!)**

---

## 📂 Estrutura do Repositório

Como o projeto evoluiu, agora temos arquivos específicos para cada situação:

* **`vagas_inatel_automatizada.py`**: Versão principal preparada para rodar no GitHub Actions (usa variáveis de ambiente seguras).
* **`vagas_inatel.py`**: Versão original para testes rápidos e execução no seu computador.
* **`vagas_estagio_inatel.csv`**: A base de dados que o robô usa para não te mandar a mesma vaga duas vezes.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.11
* **Bibliotecas:** BeautifulSoup4 (Parsing), Requests (HTTP) e CSV (Dados).
* **Mensageria:** Telegram Bot API.
* **Infraestrutura:** GitHub Actions (CI/CD e Agendamento).

---

## 📸 Demonstração

<div align="center">
<img height="500" alt="image" src="[https://github.com/user-attachments/assets/4e7cd34a-1b99-4d93-bc4c-5122db10cc21](https://github.com/user-attachments/assets/4e7cd34a-1b99-4d93-bc4c-5122db10cc21)" />
<img  height="700" alt="image" src="[https://github.com/user-attachments/assets/de93c482-3ea3-4872-94c5-97775f480bff](https://github.com/user-attachments/assets/de93c482-3ea3-4872-94c5-97775f480bff)" />
</div>

---

## 🚀 Como Utilizar (Localmente)

### 1. Configuração do Telegram (Onde conseguir as chaves?)

Para o robô conseguir te enviar mensagens, você precisa de duas informações do Telegram:

* **TOKEN_BOT:** Mande uma mensagem para o [@BotFather](https://t.me/botfather). Ele vai te dar um TOKEN após você criar seu bot.
* **CHAT_ID:** É o seu endereço pessoal no Telegram. Você pode descobrir o seu enviando uma mensagem para o bot [@userinfobot](https://t.me/userinfobot).

### 2. Instalação

```bash
pip install beautifulsoup4 requests

```

### 3. Execução

```bash
python vagas_inatel.py

```

---

## 🤖 Configuração da Automação (GitHub Actions)

Se você deseja que o robô rode sozinho todos os dias na nuvem:

1. **Secrets:** No GitHub, vá em `Settings > Secrets and variables > Actions` e crie as chaves `TOKEN_BOT` e `MEU_CHAT_ID`.
2. **Permissões:** Em `Settings > Actions > General`, habilite **"Read and write permissions"** para que o robô consiga salvar o histórico de vagas no repositório.
3. **Workflow:** O arquivo `.github/workflows/main.yml` já está configurado para despertar o robô diariamente às 09h (BRT).

---

## 👨‍💻 Sobre o Autor

**João Victor Simões Rosa**

* 🎓 Graduando em Engenharia de Software no **Inatel** (2º Período).
* 🔬 Atuante em Iniciação Científica com foco em **Machine Learning** e **Cibersegurança**.
* 🔗 **Conecte-se comigo:** [LinkedIn](https://www.linkedin.com/in/joaovictorsimoesr/)

---

<p align="center">Documentação técnica para suporte ao monitoramento de carreiras académicas.</p>

---

<div align="center">
  <h1>🚀 Inatel Job Hunter</h1>
  <p><i>Monitorização Automatizada de Vagas de Estágio</i></p>

  <img src="https://img.shields.io/badge/Python-3.11+-blue?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Status-Ativo-success?style=for-the-badge">
  <img src="https://img.shields.io/badge/Local-Inatel-orange?style=for-the-badge">
</div>

---

## 📝 Sobre o Projeto

O **Inatel Job Hunter** é um sistema de automação desenvolvido em Python para a recolha, monitorização e notificação em tempo real de vagas de estágio no portal oficial do **Inatel**.

Este projeto foi um estudo prático sobre **Web Scraping** e **Integração de APIs**. O objetivo é eliminar a verificação manual, ajudando os estudantes a receberem a informação da vaga o mais rápido possível.

---

## ✨ Funcionalidades

* **🔍 Extração de Dados (Scraping):** Varredura inteligente com `BeautifulSoup4`.
* **🔄 Sincronização de Histórico:** Mantém uma base local (CSV). Se uma vaga for removida e depois reabrir, o robô detecta e avisa novamente!
* **📱 Notificação Remota:** Integração com a **API do Telegram** para envio imediato de detalhes (Título, Empresa e Link).
* **📂 Persistência:** Geração automática de relatórios diários para conferência manual.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.11
* **Bibliotecas:** BeautifulSoup4 (Parsing), Requests (HTTP) e CSV (Dados).
* **Mensageria:** Telegram Bot API.

---

## 📸 Demonstração

<div align="center">
  <img width="45%" alt="image" src="https://github.com/user-attachments/assets/4e7cd34a-1b99-4d93-bc4c-5122db10cc21" />
  <img width="25%" alt="image" src="https://github.com/user-attachments/assets/de93c482-3ea3-4872-94c5-97775f480bff" />
</div>

---

## 🚀 Como Utilizar

### 1. Configuração do Telegram
Para o robô te enviar mensagens, você precisa:
* **TOKEN_BOT:** Mande mensagem para o [@BotFather](https://t.me/botfather) para criar seu bot.
* **CHAT_ID:** Descubra o seu enviando uma mensagem para o [@userinfobot](https://t.me/userinfobot).

### 2. Instalação e Execução

	# Instalar bibliotecas
		pip install beautifulsoup4 requests

	# Rodar o projeto
		python vagas_estagio_inatel_github.py


👨‍💻 Sobre o Autor
João Victor Simões Rosa 🎓 Graduando em Engenharia de Software no Inatel (2º Período).

🔬 Atuante em Iniciação Científica com foco em Machine Learning e Cibersegurança.

📄 Documentação técnica para suporte ao monitoramento de carreiras acadêmicas.

<a href="https://www.google.com/url?sa=E&source=gmail&q=https://www.linkedin.com/in/joaovictorsimoesrI/" target="_blank"> <img src="https://www.google.com/search?q=https://img.shields.io/badge/LinkedIn-0077B5%3Fstyle%3Dfor-the-badge%26logo%3Dlinkedin%26logoColor%3Dwhite"> </a>

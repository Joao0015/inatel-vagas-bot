🚀 Inatel Job Hunter: Monitorização Automatizada de Vagas

Sistema de automação desenvolvido em Python para a recolha, monitorização e notificação em tempo real de vagas de estágio publicadas no portal oficial do Inatel (Instituto Nacional de Telecomunicações).

🎯 Objetivo do Projeto

Este projeto foi desenvolvido como um estudo prático sobre Web Scraping e Integração de APIs. O objetivo principal é otimizar o acompanhamento de novas oportunidades, eliminando a verificação manual constante.

A motivação surgiu durante o 2º período de Engenharia de Software, procurando aplicar conceitos de extração de dados para auxiliar os estudantes do Inatel a receberem a informação da vaga o mais rápido possível, facilitando o acesso ao primeiro estágio.

✨ Funcionalidades

Extração de Dados (Scraping): Varredura inteligente das páginas de estágio utilizando BeautifulSoup4.

Sincronização de Histórico: Mantém uma base local (CSV) sincronizada. Se uma vaga for removida do portal, o robô deteta e limpa o histórico, permitindo novos alertas caso a vaga reabra.

Notificação Remota: Integração com a API do Telegram para envio imediato de detalhes (Título, Empresa e Link), com um sistema de proteção contra spam na primeira execução.

Persistência de Dados: Geração automática de relatórios diários datados para conferência manual.

🛠️ Tecnologias Utilizadas

Linguagem: Python 3.11

Bibliotecas: BeautifulSoup4 (Parsing), Requests (HTTP) e CSV (Dados).

Mensageria: Telegram Bot API.

📸 Demonstração

<img width="839" height="691" alt="image" src="https://github.com/user-attachments/assets/4e7cd34a-1b99-4d93-bc4c-5122db10cc21" />
<img width="427" height="901" alt="image" src="https://github.com/user-attachments/assets/de93c482-3ea3-4872-94c5-97775f480bff" />





🚀 Como Utilizar

1. Configuração do Telegram (Onde conseguir as chaves?)

Para o robô conseguir te enviar mensagens, você precisa de duas informações do Telegram:

TOKEN_BOT: Mande uma mensagem para o @BotFather no Telegram. Ele vai te dar uma chave secreta após você criar seu bot.

CHAT_ID: É o seu endereço pessoal no Telegram. Você pode descobrir o seu enviando uma mensagem para o bot @userinfobot.


2. Instalação

pip install beautifulsoup4 requests



3. Execução

python vagas_estagio_inatel_github.py



👨‍💻 Sobre o Autor

João Victor Simões Rosa Graduando em Engenharia de Software no Inatel (2º Período).

Atuante em Iniciação Científica com foco em Machine Learning e Cibersegurança.

Documentação técnica para suporte ao monitoramento de carreiras académicas.

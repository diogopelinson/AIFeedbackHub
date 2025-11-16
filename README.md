# ✨ AI Feedback Hub: Seu Assistente Pessoal de Escrita com IA ✨

## 🚀 Desvende o Poder da Sua Escrita com Inteligência Artificial!

Bem-vindo ao **AI Feedback Hub**, uma plataforma revolucionária que transforma a maneira como você aprimora seus textos.
Desenvolvida por mim, **Diogo Pelinson**.

Está Cansado de revisões demoradas e incertas? Prepare-se para receber feedback instantâneo, inteligente e super detalhado, tudo isso impulsionado pela magia da Inteligência Artificial!

## 💡 A Ideia por Trás do Projeto

Nosso objetivo é simples, mas poderoso: democratizar o acesso a avaliações textuais de altíssima qualidade. Imagine ter um revisor expert sempre à sua disposição, pronto para analisar seus rascunhos e apontar o caminho para a perfeição. O AI Feedback Hub nasceu para ser essa ferramenta indispensável, oferecendo uma solução automatizada e escalável que coloca insights valiosos sobre sua escrita na palma da sua mão. Seja você um estudante em busca da nota máxima, um profissional que preza pela clareza ou um criador de conteúdo que quer cativar seu público, este é o seu novo melhor amigo!

## 🎯 O que o AI Feedback Hub Faz por Você?

É super fácil! Você insere seu texto em nossa interface web intuitiva e, em questão de segundos, nossa IA entra em ação. Utilizando um modelo de linguagem avançado da OpenAI, realizamos uma avaliação completa e te entregamos um feedback que vai muito além do básico:

*   **🌟 Pontos Fortes:** Descubra o que já está brilhando na sua escrita e merece ser mantido!
*   **🛠️ Sugestões de Melhoria:** Receba dicas práticas e acionáveis para aprimorar a clareza, gramática, coesão e garantir que sua mensagem atinja o alvo em cheio.
*   **📊 Nota de Qualidade:** Uma avaliação clara (de 0 a 10) para clareza, gramática e coesão, te ajudando a visualizar seu progresso.

## 🛠️ As Ferramentas Mágicas por Trás da Cortina

Construído com uma arquitetura serverless robusta na AWS e a inteligência da OpenAI, o AI Feedback Hub é uma sinfonia de tecnologias de ponta. Conheça os maestros dessa orquestra:

*   **AWS Lambda:** Nosso motor inteligente! É aqui que o código do backend ganha vida, processando suas requisições e conversando com a OpenAI. Tudo sem precisar gerenciar servidores!
*   **Amazon API Gateway:** A porta de entrada para o nosso sistema. Ele recebe suas requisições do frontend e as encaminha de forma segura e eficiente para a Lambda.
*   **Amazon S3:** Onde seu frontend ganha um lar! Armazenamos todos os arquivos estáticos (HTML, CSS, JavaScript) de forma segura e escalável.
*   **Amazon CloudFront:** O turbo do nosso frontend! Garante que a plataforma seja entregue rapidamente para usuários em qualquer canto do mundo, com baixa latência e alta disponibilidade.
*   **AWS Secrets Manager:** Nosso cofre de segredos! Guarda a chave da OpenAI e outras informações sensíveis com a máxima segurança, longe do código.
*   **AWS IAM (Identity and Access Management):** O guardião das permissões! Garante que cada parte do nosso sistema tenha acesso apenas ao que realmente precisa, mantendo tudo seguro.
*   **OpenAI API:** O cérebro da operação! É ela quem nos fornece os modelos de linguagem avançados (como o GPT-4o-mini) que analisam seus textos e geram o feedback incrível.
*   **React:** A estrela do nosso frontend! Com ele, construímos uma interface de usuário moderna, responsiva e super agradável de usar.

## 🗺️ Diagrama de Arquitetura
![DiagramaAWS](https://github.com/user-attachments/assets/99e11f5f-0b48-485d-850d-02d1ac0dfe28)


Este diagrama visualiza o fluxo de dados e a interação harmoniosa entre os serviços AWS e a OpenAI, desde o momento em que você envia seu texto até o feedback mágico aparecer na tela.

## 🌐 Projeto no Deploy
> [!IMPORTANT]
> **DEPLOY DESATIVADO POR HORA!**

Projeto Online pra você pode acessar e testar o AI Feedback Hub diretamente aqui:
https://d2yr5vo2914kpt.cloudfront.net

---

## 🚀 Como Rodar o Projeto (Básico)

Para ter o AI Feedback Hub funcionando, você precisará configurar tanto o backend (na AWS) quanto o frontend (localmente ou também na AWS).

### 1. Configuração do Backend (AWS)

O backend é composto por uma função AWS Lambda e um Amazon API Gateway. Você precisará:

*   **Obter uma chave de API da OpenAI:** Acesse [platform.openai.com](https://platform.openai.com/) para gerar sua chave.
*   **Configurar o AWS Secrets Manager:** Armazene sua chave da OpenAI de forma segura no Secrets Manager (ex: com o nome `openai-api-key-feedback-hub`).
*   **Criar uma Role IAM:** Conceda permissões à sua função Lambda para acessar o Secrets Manager e gravar logs.
*   **Criar e Fazer Upload da Função Lambda:** Utilize o código Python fornecido (que se comunica com a OpenAI e o Secrets Manager) e empacote-o em um `.zip` para fazer o upload para a AWS Lambda (runtime Python 3.13, arquitetura x86_64).
*   **Configurar o API Gateway:** Crie um endpoint REST (`/feedback`) que acione sua função Lambda e configure o CORS para permitir requisições do seu frontend. Após o deploy, você obterá uma `Invoke URL`.

### 2. Configuração do Frontend (Local)

O frontend é um aplicativo React. Para rodá-lo localmente:

*   **Clone o repositório:** Obtenha o código do frontend para sua máquina.
*   **Instale as dependências:** Navegue até a pasta do frontend no terminal e execute `npm install`.
*   **Configure a URL da API:** No arquivo `src/FeedbackForm.js`, substitua `SUA_API_GATEWAY_INVOKE_URL` pela `Invoke URL` que você obteve do API Gateway.
*   **Inicie o aplicativo:** Execute `npm start` no terminal. Isso abrirá o aplicativo no seu navegador (geralmente em `http://localhost:3000`).

### 3. Testando o Projeto

Com o frontend rodando localmente e o backend configurado na AWS, você pode:

*   **Acessar o frontend no navegador:** Digite um texto na caixa e clique em 'Enviar'.
*   **Verificar o feedback:** O feedback da IA deve aparecer na tela, indicando que a comunicação entre frontend, API Gateway e Lambda/OpenAI está funcionando perfeitamente.

para explorar, aprimorar e contribuir com este projeto! Sua criatividade é bem-vinda para tornar o AI Feedback Hub ainda mais incrível.

## 📄 Licença

Este projeto está licenciado sob a licença MIT. Sinta-se livre para usar e modificar!


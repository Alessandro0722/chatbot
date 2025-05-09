# CHATBOT
**Projeto de criação de chatbot baseado em conteúdos de PDF**

#Sou estudante de Engenharia de Software e estou me preparando para realizar meu TCC. Preciso estudar artigos em PDF para embasar minhas ideias, mas este trabalho é desafiador devido ao grande volume de informações das quais devo encontrar conexões relevantes. Tenho o objetivo de estruturar melhor minha pesquisa de modo a encontrar conexões pertinentes ao tema do meu TCC, utilizando como ferramenta inteligência artificial generativa construída no Azure Foundry.

Para tanto, vamos criar uma estrutura no Azure Faundry para elaborar, testar e validar nosso modelo. Primeiro, precisamos preparar o ambiente de desenvolvimento deste projeto seguindo os seguintes passos:

1. Criar uma conta no Azure Machine Learning e criar um grupo de recursos em uma assinatura ativa
2. Criar um Hub de IA que estará vinculado ao grupo de recuros que criei Obs.: selecionar região: Sweden Central. Criar ao clicar em Examinar + criar  e, em seguida, clicar em Criar.
3. Criar um projeto e nomeá-lo.
4. No menu → models + endpoints -> deploy model, escolher um deploy base model (gpt-4o chat completition). Dar confirm e, no customize -> settings : Deployment: Global Standard, Tokens per minute rate limit: 100k, clicar em Deploy
3. Criar no mesmo caminho o text-embedding-3-large seguindo os passos do item acima.

Após a criação do Grupo de Recuros e do Azure Foundry:
1. Acesso meu ambiente criado e nele, seleciono Playgrounds
2. insiro uma mensagem no prompt Give the model instructions and context: “ Voce é um especialista em SNA que irá me ajudar com dúvidas asobre o tema.Traga em formato de citação. Referencie autor e ano.” executo em seeguida aplly changes
3. Escrevo a mensagem no prompt: “ O que é SNA” para testar a resposta do modelo.
4. Em Playgrounds → View Code → Add your data → clique em + Add a new data source, e faça upload de arquivos pdf no campo Data source
5. No meu grupo de recursos, criar um Azure AI Search nomeando e colocar região: Sweden Central. 
6. Em Source Data, Voltar no upload dos arquivos pdfs e se estiverem carregados, clicar em next. 
7. Em index configuration, no campo “Select Azure AI Search service “ selecionar o Azure Ai Foundry criado e clicar em connect. Em seguinda, clicar em next.
8. Em Search Settins, clique em next.
9. Em Review and finish, clique em Create vector index.
10. Após o Azure AI Search vetorizar os pdfs, posso enviar uma pergunta no prompt para testar a acurácia do modelo.
11. Em Deploy → deploy to a web app, com os settings: nome: criar nome, Subscription: minha assinatura, Resource Group: meu grupo de recursos, Location: Sweden Central, Pricing plan: basic, Enable chat history: selecionado.
Obs: deploy pode ser dado com as opções: as a web app, as a new teams app, to a new copilot in copilot studio, 
12. No menu Web Apps selecionar o projeto criado e realizar teste no prompt com a questão “O que é SNA?”

Obs: Outros recursos do AI Foundry:
- AI Services
-Agents
-Fine-tuning
-Prompt-flow

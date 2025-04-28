# 🚀 **Testes E2E Automatizados com Cypress e Azure DevOps** 🧪

Bem-vindo ao repositório! Este projeto visa garantir a **qualidade e confiabilidade** de sistemas através de testes **End-to-End** (E2E) automatizados utilizando a poderosa ferramenta **Cypress**, com integração total ao **Azure DevOps** para automação de testes no **pipeline de CI/CD**. 


##  Explore o repositório no Azure DevOps!
Acesse o repositório no Azure DevOps: https://dev.azure.com/MatheusManoel45/_git/e2e-testing-cypress-azure

Neste repositório, você encontrará tudo o que precisa para entender como os testes são executados e como o pipeline está configurado para rodar os testes automaticamente.

✨ Confira o projeto no LinkedIn!

Acesse o post sobre o projeto no LinkedIn: https://www.linkedin.com/in/matheus-manoel/ 

---

## 🎯 **Objetivo do Projeto**

Este projeto foi criado para:

- **Automatizar testes E2E**: Utilizando o Cypress, cobrimos funcionalidades cruciais como validação de formulários, responsividade e comportamentos esperados de erro.
- **Garantir entregas contínuas e confiáveis**: Integrado ao **Azure DevOps**, o pipeline de **CI/CD** executa os testes automaticamente em cada alteração no código, garantindo qualidade em tempo real.
- **Monitoramento constante**: Com os resultados dos testes sendo automaticamente publicados, é possível ter visibilidade completa sobre a saúde do sistema a cada mudança.

---

## ⚙️ **Como Funciona o Pipeline no Azure DevOps**

O grande diferencial deste projeto é a **integração contínua** com o **Azure DevOps**. O pipeline foi configurado para garantir que cada alteração no código seja validada automaticamente, realizando os testes e gerando relatórios detalhados sobre os resultados. 

### 🔥 **Visão Geral do Pipeline:**
1. **Instalação das dependências**: O pipeline começa instalando a versão necessária do **Node.js** e as dependências do projeto.
2. **Execução dos Testes E2E**: Os testes são executados automaticamente utilizando o **Cypress** com o comando `npx cypress run`.
3. **Relatório de Resultados**: Os resultados dos testes são gerados e apresentados de forma clara com o formato **JUnit**, permitindo que você veja facilmente o status de cada teste.

### 📈 **O que está incluso no Pipeline**:
- **Trigger**: O pipeline é acionado sempre que há um push para a branch `main`.
- **Instalação de Node.js**: A versão 14.x do Node.js é instalada para garantir a compatibilidade com o Cypress.
- **Execução de Testes**: O Cypress roda todos os testes E2E definidos, cobrindo casos de uso críticos como formulários, CEP, e-mail e responsividade.
- **Publicação dos Resultados**: O Azure DevOps publica automaticamente os resultados dos testes para fácil monitoramento.


Aqui está o **arquivo YAML** do pipeline configurado no Azure DevOps:

```yaml
trigger:
  - main

pool:
  name: WindowsAgent

steps:
- task: NodeTool@0
  inputs:
    versionSpec: '14.x'
  displayName: 'Instalar Node.js'

- script: |
    npm install
    npm test
  displayName: 'Instalando dependências e rodando os testes'

- script: |
    npx cypress run
  displayName: 'Rodando os testes E2E'
  continueOnError: True

- task: PublishTestResults@2
  inputs:
    testResultsFormat: 'JUnit'
    testResultsFiles: '**/output.xml'
    mergeTestResults: true
    testRunTitle: 'Resultados dos Testes'

🔧 Como Configurar o Azure DevOps Pipeline
Para configurar este pipeline no seu próprio ambiente, siga os seguintes passos:

Crie um projeto no Azure DevOps e vincule-o ao seu repositório do GitHub.

Crie um pipeline de CI/CD no Azure DevOps utilizando o arquivo azure-pipelines.yml (disponível no repositório).

Adapte a configuração de Node.js se necessário, especialmente se você precisar de uma versão diferente para seu projeto.

Adicione os testes do Cypress ao seu projeto e garanta que eles sejam executados automaticamente após cada push.

🌟 Testes Realizados
A seguir, os testes E2E que garantem a qualidade do sistema:

Documento Incorreto

E-mail Incorreto

Campos Obrigatórios

Cadastro de Conta

CEP Inválido

Responsividade (Desktop, Tablet, Mobile)

Mensagem de Erro com Campos Vazios

Esses testes são executados automaticamente no pipeline, dando visibilidade total da integridade do sistema após cada alteração no código.

🚀 Por Que Usar CI/CD com Azure DevOps?
A integração contínua com o Azure DevOps ajuda a manter a qualidade do código com validações automáticas a cada alteração. Isso permite que a equipe desenvolva e entregue novas funcionalidades com confiança, sabendo que cada alteração foi validada por testes automatizados.

Além disso, com o relatório de resultados sendo gerado automaticamente após cada execução, é possível detectar falhas imediatamente, garantindo que elas sejam corrigidas antes que o código chegue à produção.

👥 Contribuindo
Se você quiser melhorar ou adicionar novas funcionalidades a este projeto, siga estas etapas para contribuir:

Fork o repositório.

Crie uma nova branch (git checkout -b feature/nome-da-funcionalidade).

Faça suas alterações.

Envie suas alterações para o repositório (git push origin feature/nome-da-funcionalidade).

Abra um Pull Request.


---


## 🙌 Agradecimentos

Este projeto de automação foi inspirado em dicas e conceitos aprendidos através dos conteúdos do canal [Fernando Papito](https://www.youtube.com/@fernandopapito) no YouTube.

A automação dos testes foi baseada em um sistema proposto no canal, adaptado e configurado para execução automatizada via Azure DevOps Pipelines.

---

Obrigado por conferir o projeto! 🌟




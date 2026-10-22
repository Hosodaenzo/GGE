# 📖 Guia de Fluxo de Trabalho e Contribuição - GGE

Este documento define as regras de uso do nosso repositório e a organização do quadro Kanban. É essencial que toda a equipe siga este fluxo para mantermos o projeto organizado.

## 📋 1. Gestão de Tarefas (Kanban)

Todas as atividades do projeto devem ser gerenciadas através do nosso board oficial.

- **Criação:** Toda nova demanda deve ser criada como uma **Issue** (e não apenas um rascunho de texto no board), garantindo a integração com o repositório e histórico de código.
- **Vínculo:** Certifique-se sempre de selecionar o projeto "GGE Development" no painel lateral direito (seção "Projects") no momento de criação da Issue.
- **Campos Obrigatórios:** Preencha os campos customizados antes de mover a tarefa para "In Progress":
  - `Prioridade`
  - `Tamanho`
  - `Data de Início`
  - `Data Final`
- **Atribuição:** Sempre defina o responsável pela tarefa no campo `Assignee`.

## 🌿 2. Arquitetura de Branches

Nosso repositório possui três branches principais para proteger o código que vai para produção:

- **`prd` (Produção):** Contém apenas o código estável e validado. NUNCA deve receber commits diretos.
- **`qa` (Qualidade/Testes):** Ambiente de validação. Recebe as funcionalidades prontas da DEV para testes em conjunto.
- **`dev` (Desenvolvimento):** Branch central de integração técnica. Todas as novas funcionalidades (features) saem daqui e voltam para cá.

## 🔄 3. Ciclo de Vida do Código (O Dia a Dia)

Para atuar em uma tarefa, siga o fluxo abaixo:

1. Acesse o Kanban, puxe uma tarefa para "In Progress" e certifique-se de que você está como Assignee.
2. No seu terminal/GitHub Desktop, crie uma branch temporária SEMPRE a partir da branch `dev`. 
   * **Nomenclatura da branch temporária:** `tipo/nome-da-tarefa` (ex: `feature/configurar-vm`, `bugfix/erro-login`).
3. Faça os seus commits e envie (push) a branch temporária para o GitHub.
4. Quando finalizar, abra um **Pull Request (PR)** apontando a sua branch temporária para a `dev`.
5. Após o código ser revisado e aprovado, o merge é feito na `dev`.

### Integração e Lançamento
- **Testes (QA):** Periodicamente, abriremos um Pull Request da `dev` para a `qa` para testar todas as funcionalidades juntas.
- **Produção (PRD):** Se tudo funcionar na `qa`, um Pull Request final será aberto da `qa` para a `prd`, oficializando a nova versão do projeto.
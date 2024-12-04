# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.

## TRPC

O tRPC é uma biblioteca TypeScript que facilita a criação de APIs do tipo end-to-end (E2E), fornecendo tipagem compartilhada entre o cliente e o servidor sem necessidade de um arquivo de especificação (como no GraphQL ou REST).

Um router no tRPC é o componente principal onde você define e organiza os procedimentos (queries e mutations) que compõem a API. Ele funciona como um ponto central para gerenciar as rotas do servidor e estruturar a lógica da aplicação.

Função do Router no tRPC
O router tem três principais responsabilidades:

Agrupar Procedimentos

Um procedimento é como um "endpoint" que o cliente pode chamar, definido como:
Query: Para leitura de dados (sem efeitos colaterais).
Mutation: Para alteração de dados (com efeitos colaterais).
Definir Hierarquias

Você pode criar routers hierárquicos, ou seja, um router pode conter outros routers. Isso ajuda na organização de APIs grandes, como dividir funcionalidades por módulo (ex.: userRouter, postRouter).
Expor Tipos para o Cliente

Como o tRPC utiliza TypeScript, o router automaticamente gera tipos que são compartilhados entre o servidor e o cliente, permitindo comunicação segura e sem discrepâncias.

O context no tRPC é um objeto que armazena informações compartilhadas entre todos os procedimentos (queries e mutations) em um router. Ele é criado no momento da execução de uma solicitação e pode conter dados como:

Informações sobre o usuário autenticado (ex.: ID, permissões).
Conexões a serviços externos (ex.: banco de dados, APIs).
Variáveis globais ou dependências específicas do servidor.

O context no tRPC:

É uma forma de compartilhar dados e dependências de forma segura e organizada.
É criado no início de cada requisição e passado para todos os procedimentos.
É tipado, garantindo segurança no uso.

No contexto do SvelteKit, um middleware é um código ou função que intercepta a requisição, podendo realizar tarefas como autenticação, logging, modificação de dados ou manipulação de cabeçalhos, antes ou depois do processamento da solicitação. O middleware no SvelteKit é implementado principalmente através do handle nos hooks, permitindo um controle centralizado sobre o fluxo de requisições e respostas.


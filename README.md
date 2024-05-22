# Http Server with Typescript

## Starting point

### Prerequisites
- Install NodeJS version 20 or later [ [fast](https://nodejs.org) ] [ [better](https://github.com/nvm-sh/nvm) ]

### From scratch
- Run in terminal
    ```sh
    npm init -y
    npm install typescript @types/node tsx -D
    npx tsc --init
    ```
- Update tsconfig.json using the microsoft recommendations
[Node-Target-Mapping](https://github.com/microsoft/TypeScript/wiki/Node-Target-Mapping).

### Next step

- Basic Structure
    ```sh
    mkdir -p src/http
    touch src/http/server.ts
    ```
    - Update the "scripts" property for package.json to run tsc in watch mode.
        ```json
        "dev": "tsx watch src/http/server.ts"
        ```
    ### Fastify
    - Using Fastify [Getting Started](https://fastify.dev/docs/latest/Guides/Getting-Started/).
        ```sh
        npm install fastify
        ```
    - Update the server.ts file with the code below.
        ```typescript
        import fastify, { FastifyInstance } from "fastify";

        const app: FastifyInstance = fastify();

        app.get("/", () => {
            return { hello: "world" };
        });

        app.listen({ port: 3333 }).then(() => {
            console.log("HTTP server running on http://localhost:3333");
        });
        ```
- Run your server 
    ```sh
    npm run dev
    ```

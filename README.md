This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.


## Criação do projeto
Next.js
npx create-next-app@latest

## dockerfile.yaml
version: 
services:
    [nomeprojeto]:
        container_name:
        build:
            context: 
            dockerfile: 
        volumes:
            -
        ports:
            - 
networks:
    default:
        driver:

## Subir para Docker
docker-compose up -d --build

docker-compose exec [nomeprojeto] sh -c "npm install"

docker-compose exec [nomeprojeto] sh -c "npm start"



#####
https://www.youtube.com/watch?v=fqr0mhQrASU&ab_channel=hcode
## Ambiente
Criar arquivos
.env
.env.production
instalar módulo para carregar arquivos .env de acordo com o ambiente:
    npm i @nextjs/config
importar o módulo em arquivo app.module.ts
imports: [ ConfigModule.forRoot() ]

## Criar arquivo .Dockerignore
Dentro dele:
node_modules
.env
dist

## Criar arquivo Dockerfile
Dentro dele 
FROM node:latest

WORKDIR /usr/src/api

COPY . .
COPY ./.env.production ./.env

RUN npm install --quiet --no-optional --no-fund --loglevel=error

RUN npm run build

EXPOSE 3000

CMD ["npm", "run", "start:prod"]

## Criar imagem docker
No terminal:
    docker build --pull --rm -f "app-tutorials-ti/Dockerfile" -t projetos:latest "app-tutorials-ti"

## Rodar imagem docker


#####
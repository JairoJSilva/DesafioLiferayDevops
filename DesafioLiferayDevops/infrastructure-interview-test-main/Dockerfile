# 1. Usar a imagem oficial do Node.js
FROM node:18-alpine

# 2. Definir o diretório de trabalho dentro do container
WORKDIR /app

# 3. Copiar o package.json e yarn.lock para o container
COPY package.json yarn.lock ./

# 4. Instalar as dependências da aplicação
RUN yarn install

# 5. Copiar o restante dos arquivos da aplicação para o container
COPY . .

# 6. Executar as migrations para configurar o banco de dados
CMD yarn typeorm migration:run && yarn start

# 7. Expor a porta que a aplicação vai utilizar
EXPOSE 3000
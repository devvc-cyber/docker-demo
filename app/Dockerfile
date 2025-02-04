# Use uma imagem leve do Node.js
FROM node:14-alpine

# Definir o diretório de trabalho dentro do container
WORKDIR /app

# Copiar package.json e instalar as dependências
COPY package.json .
RUN npm install --production

# Copiar o código da aplicação
COPY index.js .

# Expor a porta que a aplicação irá utilizar
EXPOSE 3000

# Comando para iniciar a aplicação
CMD ["npm", "start"]

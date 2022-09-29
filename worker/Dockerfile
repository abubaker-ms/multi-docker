FROM node:alpine
USER node 
RUN mkdir -p /home/node/app
#working directory
WORKDIR /home/node/app       

#copy to root directory ./
COPY --chown=node ./package.json ./
RUN npm install
COPY --chown=node:node ./ ./
 
CMD ["npm", "run", "start"]
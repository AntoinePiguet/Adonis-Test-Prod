FROM node:20-alpine

# Définir le répertoire de travail
WORKDIR /app

# Copier d'abord le dossier AdonisCode
COPY ./AdonisCode/package*.json ./

# Installer les dépendances
RUN npm install --production

# Copier le reste des fichiers de l'application
COPY ./AdonisCode ./

# Build pour la production
RUN npm run build

# Exposer le port (Render utilisera PORT=10000)
EXPOSE 10000

# Définir les variables d'environnement pour la production
ENV HOST=0.0.0.0
ENV PORT=10000
ENV NODE_ENV=production

# Le point d'entrée
CMD ["node", "server.js"]
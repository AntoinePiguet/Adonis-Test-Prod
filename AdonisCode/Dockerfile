FROM node:20-alpine

# Installer netcat
RUN apk add --no-cache netcat-openbsd

# Définir le répertoire de travail
WORKDIR /app

# Copier le contenu du dossier AdonisCode dans /app
COPY ./AdonisCode/package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste des fichiers de l'application
COPY ./AdonisCode ./

# Exposer le port
EXPOSE 3333

# Définir les variables d'environnement
ENV HOST=0.0.0.0
ENV PORT=3333

# Le point d'entrée
CMD ["npm", "run", "dev"]
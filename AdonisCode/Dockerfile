FROM node:20-alpine

# Définir le répertoire de travail
WORKDIR ./AdonisCode

# Copier d'abord le dossier AdonisCode
COPY ./AdonisCode/package*.json ./

# Installer TOUTES les dépendances (y compris devDependencies)
RUN npm install

# Copier le reste des fichiers de l'application
COPY ./AdonisCode ./

# Build pour la production
RUN npm run build

# Supprimer les devDependencies après le build
# RUN npm prune --production
WORKDIR ./build 
RUN npm ci --omit="dev"  

# Exposer le port
EXPOSE 10000

# Définir les variables d'environnement pour la production
ENV HOST=0.0.0.0
ENV PORT=10000
ENV NODE_ENV=production

# Le point d'entrée
CMD ["node", "bin/server.js"]

RUN PGPASSWORD=VPWRK02GwrPlghrESKxYfPPVXE8MPFcJ psql -h dpg-d092kmhr0fns73dv6130-a.oregon-postgres.render.com -U db_flashcards_xi1o_user db_flashcards_xi1o
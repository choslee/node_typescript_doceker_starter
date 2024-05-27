FROM node:20-alpine

# Setujemo radni direktorijum u kontejneru
WORKDIR /user/src/app

# Kopiramo package.json i package-lock.json u radni direktorijum   
# (./ je radni direktorijum tj. app)
COPY package*.json ./

# Instaliramo zavisnosti iz package.json fajla samo kada je produkcija 
# koristeći "clean install" (npm ci) koji prvo obriše node_modules folder
RUN npm ci --only=production

# Kopiramo sve fajlove iz trenutnog direktorijuma u radni direktorijum
COPY . .

# Expose port (dodajte port na kojem vaš server sluša, npr. 3000)
EXPOSE 3000

CMD [ "npm", "run", "dev" ]

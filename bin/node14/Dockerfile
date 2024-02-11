# Usa una imagen oficial de Node como imagen base
FROM node:21

# Establece el directorio de trabajo dentro del contenedor
WORKDIR ${NODEJS_WORK_DIR}

# Copia los archivos de configuración de tu proyecto (package.json y package-lock.json, si existe)
COPY package*.json ./

# Instala las dependencias de tu proyecto
RUN npm install

# Copia el resto de los archivos de tu proyecto al directorio de trabajo
COPY . .

# Expone el puerto que tu aplicación utilizará
EXPOSE 3000

# El comando para ejecutar tu aplicación
CMD ["npm", "start"]

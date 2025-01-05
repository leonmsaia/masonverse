FROM debian:bullseye-slim

# Instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    mono-complete \
    libsqlite3-0 \
    libmariadb-dev \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Copiar el archivo descargado al contenedor y descomprimirlo
WORKDIR /opensim
COPY opensim-0.9.3.0.zip /opensim/
RUN unzip opensim-0.9.3.0.zip && rm opensim-0.9.3.0.zip

# Configurar el punto de entrada
CMD ["mono", "OpenSim.exe"]

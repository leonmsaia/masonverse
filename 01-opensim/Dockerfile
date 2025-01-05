FROM debian:bullseye-slim

# Instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    mono-complete \
    libsqlite3-0 \
    libmariadb-dev \
    wget \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Descargar y descomprimir OpenSimulator
WORKDIR /opensim
RUN wget -q http://opensimulator.org/dist/opensim-0.9.3.0.zip -O opensim.zip \
    && unzip opensim.zip && rm opensim.zip

# Configurar el punto de entrada
CMD ["mono", "OpenSim.exe"]

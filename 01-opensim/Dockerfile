FROM debian:bullseye-slim

# Instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    mono-complete \
    libsqlite3-0 \
    libmariadb-dev \
    wget \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Copiar los archivos de Diva Distribution al contenedor
WORKDIR /opensim
COPY core/ /opensim/

# Ejecutar configuración automática de Diva
RUN mono /opensim/bin/Configure.exe --no-prompt

# Configurar el punto de entrada para iniciar OpenSim
CMD ["mono", "/opensim/bin/OpenSim.exe"]

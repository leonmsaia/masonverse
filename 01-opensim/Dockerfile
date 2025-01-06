FROM debian:bullseye-slim

# Instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    mono-complete \
    libsqlite3-0 \
    libmariadb-dev \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Copiar los archivos descomprimidos al contenedor
WORKDIR /opensim
COPY opensim-files/ /opensim/

# Asegurar permisos de ejecución
RUN chmod +x /opensim/bin/OpenSim.exe

# Configurar el punto de entrada
CMD ["mono", "/opensim/bin/OpenSim.exe"]

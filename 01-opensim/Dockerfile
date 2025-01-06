FROM debian:bullseye-slim

# Instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    mono-complete \
    libsqlite3-0 \
    libmariadb-dev \
    wget \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Copiar todos los archivos al contenedor
WORKDIR /opensim
COPY core/ /opensim/

# Cambiar al directorio bin para ejecutar OpenSim
WORKDIR /opensim/bin

# Asegurar permisos de ejecución
RUN chmod +x /opensim/bin/OpenSim.exe

# Configurar el punto de entrada para iniciar OpenSim
CMD ["mono", "OpenSim.exe"]

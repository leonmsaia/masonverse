FROM debian:bullseye-slim

# Instalar dependencias necesarias
RUN apt-get update && apt-get install -y \
    mono-complete \
    wget \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Descargar y descomprimir OpenSimulator
WORKDIR /opensim
RUN wget -q https://opensimulator.org/dist/latest/OpenSim-0.9.2.2.zip -O opensim.zip \
    && unzip opensim.zip && rm opensim.zip

# Configurar el punto de entrada
COPY data /opensim/data
CMD ["sh", "-c", "./OpenSim.exe"]

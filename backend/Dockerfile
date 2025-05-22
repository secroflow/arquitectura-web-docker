FROM debian:bullseye

# Instalar Python e pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Directorio de traballo
WORKDIR /app

# Copiar requirements.txt e instalar dependencias
COPY requirements.txt .

RUN pip3 install --no-cache-dir -r requirements.txt

# Comando por defecto
CMD ["python3", "app.py"]

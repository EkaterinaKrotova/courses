FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt ./
RUN pip3 install --no-cache-dir -r requirements.txt
COPY ./ ./

# RUN apt update && \
#     apt upgrade --yes && \
#     rm -rf /var/lib/apt/lists/*

RUN useradd python
RUN chown -R python:python ./

# ONBUILD RUN ls -la

USER python:

# HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 CMD [ "curl", "localhost:5000" ]

EXPOSE 5000

CMD [ "python3", "app.py" ]

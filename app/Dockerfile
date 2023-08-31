FROM ubuntu:latest

# Create app directory
WORKDIR /app

ENV AZURE_OPENAI_API_VERSION="2022-12-01"
ENV AZURE_OPENAI_DALLE_API_VERSION="2023-06-01-preview"

RUN apt update
RUN apt install python3 python3-pip curl -y

RUN curl -sL https://aka.ms/InstallAzureCLIDeb | bash

RUN mkdir /backend

COPY ./backend /backend

RUN pip3 install -r ./backend/requirements.txt

EXPOSE 5000
CMD [ "flask", "run","--host","0.0.0.0","--port","5000"]
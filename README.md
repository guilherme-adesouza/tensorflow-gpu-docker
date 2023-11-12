# Tensorflow GPU 

Esse projeto é um ambiente Docker para a execução de ambientes TensorFlow que necessitem a utilização de GPU. 

## Tabela de Conteúdo

- [Pré-requisitos](#)
- [Instalação](#instalação)
- [Uso](#uso)
- [Configuração](#configuração)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Pré-requisitos

- NVIDIA drivers
- nvidia-smi funcionando corretamente

## Instalação

```bash
git clone https://github.com/guilherme-adesouza/tensorflow-gpu-docker.git
cd tensorflow-gpu-docker
docker-compose up -d
```

## Uso 

Como este docker-compose utiliza volumes, basta colocar os arquivos dentro da pasta onde o docker-compose está que eles serão espelhados para o container do Docker.

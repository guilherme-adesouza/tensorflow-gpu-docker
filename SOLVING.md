# Suporte a GPU NVIDIA para Docker no Ubuntu 22.04

## Pré-requisitos
- GPU NVIDIA

## Ubuntu 22.04
- 
- GPU NVIDIA (por exemplo, GeForce RTX 3060 Mobile / Max-Q)

## Problemas Encontrados

### 1. Erro de Acesso à GPU pelo Docker
Inicialmente, as tentativas de executar contêineres Docker com suporte a GPU resultaram em erros indicando que o Docker não conseguia acessar a GPU.

**Mensagem de Erro:**
```shell
docker: resposta de erro do daemon: não foi possível selecionar o driver de dispositivo "" com as capacidades: [[gpu]].
```

### 2. Compatibilidade do Driver NVIDIA e Toolkit CUDA
Investigações adicionais revelaram a falta de instalação adequada do driver NVIDIA, evidenciada pela ausência do comando `nvidia-smi`.

**Mensagem do Sistema:**
```shell
Comando 'nvidia-smi' não encontrado...
```

### 3. Erro no Runtime do Container NVIDIA
Após uma configuração parcial, outro erro foi encontrado relacionado ao runtime do container NVIDIA.

**Mensagem de Erro:**
```shell
nvidia-container-cli: erro de inicialização: falha ao carregar a biblioteca: libnvidia-ml.so.1: não foi possível abrir o arquivo de objeto compartilhado: nenhum arquivo ou diretório desse tipo
```

## Soluções

### Etapa 1: Instalação do Driver NVIDIA
1. **Atualizar o Sistema:**
```bash
sudo apt update
sudo apt upgrade
```

2. Instalar os Drivers Recomendados:
```bash
ubuntu-drivers devices
sudo ubuntu-drivers autoinstall
```

3. Reiniciar computador:
```bash
reboot
```

4. Verificar drivers
```bash
nvidia-smi
```

## Recursos Adicionais

- [GitHub do NVIDIA Docker](https://github.com/NVIDIA/nvidia-docker)
- [Documentação do Docker](https://docs.docker.com/)

## Contribuições

Contribuições para este projeto são bem-vindas. Por favor, certifique-se de que quaisquer pull requests ou questões sejam concisas e claras na descrição.


Você pode copiar e colar esse conteúdo em um arquivo `README.md` no seu repositório GitHub. A formatação Markdown será renderizada corretamente na plataforma GitHub.

# Atividade 3 – Docker
![image](https://github.com/user-attachments/assets/da982609-a80f-4103-a20c-45ed66ca5a60)

> IFC – Campus Camboriú  
> Prof. Rafael Speroni  
> Discente: Hisllaylla Kézia  
> Matéria: Tópicos Avançados em Programação Web

## Sobre o projeto

Atividade 3 da disciplina com foco na exploração de conceitos básicos e práticos do Docker: instalação, execução de containers, mapeamento de portas, montagem de volumes, personalização, etc.

## Ambiente

- Fedora Linux (versão 42+)
- Docker Engine (via repositório oficial)
- Terminal com privilégios de root (ou grupo docker)

## Instalação do Docker no Fedora

1. **Remove pacotes antigos (se existirem):**

```
sudo dnf remove docker \
  docker-client docker-client-latest docker-common \
  docker-latest docker-latest-logrotate docker-logrotate docker-engine
```

2. **Adição do repositório oficial**

> É necessária a instalação tanto pelo Fedora não vir com o docker pré-instalado por conta da filosofia "sem daemon" (como o Podman, alternativa do Docker), assim compatível com tecnologias OCI (Open Container Initiative), quanto porque é necessário que o sistema proteja posteriormente a instalação dos pacotes que rodam o Docker, assim evitando versões antigas e quebradas, além de receber atualizações oficiais e seguras.
```
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
```

3. **Instalação do Docker e plugins**
```
sudo dnf install docker-ce docker-ce-cli containerd.io \
  docker-buildx-plugin docker-compose-plugin
```

4. **Ativa e inicia o serviço**
```
sudo systemctl enable docker
sudo systemctl start docker
```

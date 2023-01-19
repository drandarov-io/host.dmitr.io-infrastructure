# host.dmitr.io - Infrastructure

[![host.dmitr.io](https://img.shields.io/website?down_color=red&down_message=offline&label=host.dmitr.io&up_color=green&up_message=online&url=https%3A%2F%2Fhost.dmitr.io)](https://host.dmitr.io)

## Core services

### Traefik

[![host.dmitr.io/traefik](https://img.shields.io/website?down_color=red&down_message=offline&label=host.dmitr.io%2Ftraefik&up_color=green&up_message=online&url=https%3A%2F%2Fhost.dmitr.io%2Ftraefik)](https://host.dmitr.io/traefik)

- [Traefik](https://host.dmitr.io/traefik) - Reverse proxy

### Authelia

[![host.dmitr.io/authelia](https://img.shields.io/website?down_color=red&down_message=offline&label=host.dmitr.io%2Fauthelia&up_color=green&up_message=online&url=https%3A%2F%2Fhost.dmitr.io%2Fauthelia)](https://host.dmitr.io/authelia)

- [Authelia](https://host.dmitr.io/authelia) - Authentication and authorization server

## Utilities

### SearXNG

[![host.dmitr.io/searxng](https://img.shields.io/website?down_color=red&down_message=offline&label=host.dmitr.io%2Fsearxng&up_color=green&up_message=online&url=https%3A%2F%2Fhost.dmitr.io%2Fsearxng)](https://host.dmitr.io/searxng)

- [host.dmitr.io/searxng](https://host.dmitr.io/searxng)

## Game Servers

### Minecraft

[![host.dmitr.io/minecraft](https://img.shields.io/website?down_color=red&down_message=offline&label=host.dmitr.io%2Fminecraft&up_color=green&up_message=online&url=https%3A%2F%2Fhost.dmitr.io%2Fminecraft)](https://host.dmitr.io/minecraft)

- [host.dmitr.io/minecraft](https://host.dmitr.io/minecraft)

### Project Zomboid

[![host.dmitr.io/zomboid](https://img.shields.io/website?down_color=red&down_message=offline&label=host.dmitr.io%2Fzomboid&up_color=green&up_message=online&url=https%3A%2F%2Fhost.dmitr.io%2Fzomboid)](https://host.dmitr.io/zomboid)

- [host.dmitr.io/zomboid](https://host.dmitr.io/zomboid)

## Deployment

### Mermaid Diagram:

```mermaid
graph LR
    %% User
    user(User)
    
    %% Core Services
    traefik(fa:fa-docker host.dmitr.io/traefik)
    authelia(host.dmitr.io/authelia)
    searxng(host.dmitr.io/searxng)
    whoami(host.dmitr.io/whoami)
    
    minecraft(host.dmitr.io/minecraft)
    zomboid(host.dmitr.io/zomboid)
    
    subgraph public[Public facing]
        authelia -->|authenticate| traefik
        traefik --> whoami
    end
    
    subgraph private[Private]
        minecraft
        zomboid
    end
    
    subgraph protected[Protected]
        searxng
    end
    
    admin --> traefik
    user --> traefik
    traefik --> minecraft
    traefik --> zomboid
    traefik --> searxng
```

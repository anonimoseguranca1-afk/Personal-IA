# IA-Pessoal2 — Open WebUI + 9Router

Ambiente de IA pessoal com interface web, gateway unificado de modelos e recursos como pesquisa web, visão via Gemini, e túnel Cloudflare.

## O que funciona

- ✅ **Open WebUI** – interface de chat com suporte a RAG, pesquisa web, code interpreter e ferramentas.
- ✅ **9Router** – gateway que unifica provedores (DeepSeek, Gemini, OpenRouter, Groq, etc.) em uma única API compatível com OpenAI.
- ✅ **Pesquisa web** – integrada com Brave Search (free tier) e/ou SearXNG (local ou público).
- ✅ **Visão** – imagens e documentos processados via Gemini (free tier) através do 9Router.
- ✅ **Túnel Cloudflare** – exposição pública temporária (opcional, para testes).
- ✅ **Portabilidade** – todo o sistema configurado via Docker Compose com bind mounts; basta copiar a pasta e rodar `docker compose up -d`.

## Stack

| Serviço | Tecnologia | Porta |
|---------|------------|-------|
| Interface | Open WebUI | 3000 |
| Gateway | 9Router | 20128 |
| Busca (opcional) | SearXNG | 8888 |
| Túnel | Cloudflare Tunnel | (dinâmico) |

## Pré‑requisitos

- Docker e Docker Compose (instalados)
- Git (para clonar)
- Chaves de API (criar contas nos serviços abaixo)

## Chaves necessárias (gratuitas / free tier)

- [DeepSeek API](https://platform.deepseek.com/) – paga, barata, para raciocínio.
- [Google Gemini](https://makersuite.google.com/app/apikey) – gratuita, para visão.
- [Brave Search](https://brave.com/search/api/) – gratuita, para pesquisa web.
- (opcional) Chaves para OpenRouter, Groq, etc., se desejar mais modelos.

## Instalação

```bash
git clone https://github.com/seu-usuario/IA-Pessoal2.git
cd IA-Pessoal2
cp .env.example .env   # preencha com suas chaves
docker compose up -d

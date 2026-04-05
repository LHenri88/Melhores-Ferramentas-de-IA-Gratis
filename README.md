# 🚀 Arsenal Gratuito de IA — Henri MAESTR[IA]

> Atualizado: Abril 2026  
> Todos os links, limites reais e instruções de instalação das ferramentas do vídeo.

---

## 📋 Índice Rápido

| # | Ferramenta | Categoria | Acesso | Limite Free |
|---|-----------|-----------|--------|-------------|
| 1 | [Wan 2.6](#1-wan-26) | Vídeo Open Source | Local / Web | ♾️ Ilimitado local |
| 4 | [Google AI Studio](#4-google-ai-studio) | API Multimodal | Web + API | 1.500 req/dia · 1M tokens |
| 5 | [Google Stitch](#5-google-stitch) | Design de UI/UX | Web | 350 gerações/mês (Flash) |
| 6 | [NotebookLM](#6-notebooklm) | Pesquisa + Podcast IA | Web | 100 notebooks · 50 fontes cada |
| 7 | [ComfyUI](#7-comfyui) | Geração Local de Imagem/Vídeo | Local / Cloud | ♾️ Ilimitado local |
| 8 | [Lovable.dev](#8-lovabledev) | Construtor de Apps | Web | Créditos iniciais generosos |
| 9 | [OpenCode](#9-opencode) | Agente de Código no Terminal | CLI / Desktop | ♾️ (usa sua própria API key) |
| 10 | [ElevenLabs](#10-elevenlabs) | Clonagem de Voz / TTS | Web + API | 10k chars/mês |
| 11 | [LMNT](#11-lmnt) | TTS Ultra-Rápido para Dev | Web + API | 15k chars grátis |
| 12 | [Chatterbox (Resemble AI)](#12-chatterbox-resemble-ai) | TTS Open Source | Local / HuggingFace | ♾️ Ilimitado local |
| 13 | [ACE Studio 2.0](#13-ace-studio-20) | Voz Cantada por IA | Desktop + Web | Plano gratuito disponível |
| 14 | [Suno V4.5](#14-suno-v45) | Música Completa por IA | Web | 50 músicas/dia |
| 15 | [Pippit AI](#15-pippit-ai) | Vídeo de Marketing / E-commerce | Web | 150 créditos/semana |
| 16 | [CapCut](#16-capcut) | Edição de Vídeo com IA | Web / Desktop / Mobile | Grátis com recursos IA |
| 17 | [Magic Eraser (Cleanup.pictures)](#17-magic-eraser--cleanuppictures) | Remoção de Objetos | Web | 5 imagens/dia grátis |

---

## 1. Wan 2.7

**Categoria:** Geração de Vídeo Open Source  
**Site Oficial:** https://wan.video  
**GitHub:** https://github.com/Wan-Video/Wan2.1  
**HuggingFace (Web, sem instalação):** https://huggingface.co/spaces/Wan-AI/Wan2.1-T2V-14B  

### O que é
Modelo open source da Alibaba para geração de texto-para-vídeo e imagem-para-vídeo. Os pesos são públicos, sem DRM, sem assinatura. É o único gerador de vídeo verdadeiramente ilimitado do mercado — se você tiver GPU.

### Capacidades
- Geração T2V (texto para vídeo) e I2V (imagem para vídeo)
- Resolução até 1080p (local com GPU adequada)
- Clips de até 15 segundos por geração
- Suporte a câmera cinematográfica no prompt (zoom, pan, dolly)
- Arquitetura Mixture-of-Experts para eficiência

### Limites Free
| Caminho | Limite | Qualidade |
|---------|--------|-----------|
| HuggingFace Space público | Fila de espera (3–15 min), sem limite de gerações | 720p, 5s |
| Instalação local (GPU própria) | **Ilimitado** | Até 1080p |
| wan.video (site oficial) | Check-in diário = 10 créditos bônus | 720p, 5s |

### Instalação Local (GPU NVIDIA ≥ 12GB VRAM)

**Pré-requisitos:** Python 3.10+, CUDA 12.x, Git

```bash
# 1. Clone o repositório
git clone https://github.com/Wan-Video/Wan2.1.git
cd Wan2.1

# 2. Crie um ambiente virtual (recomendado)
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows

# 3. Instale as dependências
pip install -r requirements.txt

# 4. Baixe os checkpoints do modelo (escolha conforme sua VRAM)
# Modelo 1.3B — para GPUs com 12GB VRAM
python scripts/download_weights.py --model Wan2.1-T2V-1.3B

# Modelo 14B — para GPUs com 24GB+ VRAM
python scripts/download_weights.py --model Wan2.1-T2V-14B

# 5. Gere um vídeo via CLI
python generate.py \
  --task t2v-1.3B \
  --size 832*480 \
  --ckpt_dir ./Wan2.1-T2V-1.3B \
  --prompt "Um astronauta caminhando em Marte ao pôr do sol, câmera lenta, 4K cinemático"
```

### Uso via HuggingFace (sem GPU, zero instalação)
1. Acesse: https://huggingface.co/spaces/Wan-AI/Wan2.1-T2V-14B
2. Faça login com conta HuggingFace (gratuita)
3. Digite o prompt em inglês
4. Aguarde na fila (3 a 15 minutos dependendo do horário)
5. Baixe o vídeo gerado

> 💡 **Dica:** Prompts em inglês têm melhor resultado. Inclua termos como `cinematic lighting`, `slow motion`, `4K`, `shallow depth of field` para resultados mais cinematográficos.

---

## 4. Google AI Studio

**Categoria:** API Multimodal Gratuita (Texto, Imagem, Vídeo, Áudio, PDF)  
**Site Oficial:** https://aistudio.google.com  
**Documentação:** https://ai.google.dev/docs  
**Acesso:** Login com Google

### O que é
O playground e gateway de API para os modelos Gemini do Google. Não é o chat do Gemini — é acesso direto à API com os limites mais generosos do mercado no tier gratuito.

### Capacidades
- Gemini 2.5 Pro e Flash: reasoning, código, texto
- Multimodal nativo: envie imagens, PDFs, vídeos de até 1 hora, áudios
- Geração de áudio (Text-to-Speech nativo via API)
- Geração de imagens via Imagen (em modelos selecionados)
- API key gratuita para integrar em seus projetos
- Streaming de respostas, function calling, tool use

### Limites Free (Tier Gratuito)
| Modelo | RPM | RPD | Tokens por req |
|--------|-----|-----|----------------|
| Gemini 2.5 Flash | 10 | 500 | 1M tokens |
| Gemini 2.5 Pro | 5 | **1.500** | **1M tokens** |
| Gemini 2.0 Flash | 15 | 1.500 | 1M tokens |

> ⚡ **1.500 requisições/dia com 1 milhão de tokens cada = infraestrutura absurda de graça.**

### Como obter sua API Key
1. Acesse https://aistudio.google.com
2. Faça login com Google
3. No menu lateral, clique em **Get API Key**
4. Clique em **Create API Key**
5. Copie a chave e guarde em local seguro

### Exemplo de uso com Python
```python
pip install google-generativeai

import google.generativeai as genai

genai.configure(api_key="SUA_API_KEY_AQUI")

model = genai.GenerativeModel("gemini-2.5-pro")

# Texto simples
response = model.generate_content("Crie um roteiro de 5 minutos sobre Bitcoin")
print(response.text)

# Multimodal: enviar imagem
import PIL.Image
img = PIL.Image.open("screenshot.png")
response = model.generate_content(["Descreva esta imagem em detalhes", img])
print(response.text)

# Multimodal: enviar PDF
with open("relatorio.pdf", "rb") as f:
    pdf_data = f.read()

response = model.generate_content([
    "Extraia os principais dados financeiros deste PDF",
    {"mime_type": "application/pdf", "data": pdf_data}
])
print(response.text)
```

### Uso com n8n (sem código)
1. No n8n, adicione o node **HTTP Request**
2. Method: POST
3. URL: `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=SUA_API_KEY`
4. Body: JSON com `{"contents": [{"parts": [{"text": "{{$json.mensagem}}"}]}]}`

---

## 5. Google Stitch

**Categoria:** Design de UI/UX com IA  
**Site Oficial:** https://stitch.withgoogle.com  
**Blog de lançamento:** https://developers.googleblog.com/stitch-a-new-way-to-design-uis  
**Acesso:** Login com Google, sem cadastro adicional

### O que é
Ferramenta do Google Labs (adquirida da Galileo AI) que gera interfaces completas de apps mobile e web a partir de texto ou imagens. Exporta para Figma e HTML/CSS funcional.

### Capacidades
- Geração de UI a partir de texto, sketch ou screenshot
- Canvas infinito com múltiplas variantes simultâneas
- Exportação para Figma (layers editáveis + Auto Layout)
- Geração de código HTML/Tailwind CSS funcional
- Prototipagem interativa com cliques entre telas
- Integração com Google AI Studio e Google Jules
- DESIGN.md: arquivo que documenta o sistema de design e pode ser importado em outros projetos
- Suporte a voz para refinamento em tempo real
- Integração com MCP Server (para uso com Cursor, Gemini CLI)

### Limites Free
| Modo | Modelo base | Limite mensal |
|------|-------------|---------------|
| Standard (padrão) | Gemini 2.5 Flash | **350 gerações/mês** |
| Experimental (alta qualidade) | Gemini 2.5 Pro | **50 gerações/mês** |

### Como usar
1. Acesse https://stitch.withgoogle.com
2. Login com Google (sem cadastro adicional)
3. Clique em **New Project**
4. Escolha **Mobile App** ou **Web App**
5. Escolha o modo: **Standard** (rápido) ou **Experimental** (qualidade superior)
6. Descreva sua interface. Exemplo de prompt efetivo:

```
Dashboard mobile para rastreamento de portfólio de criptomoedas.
Tema dark com acentos em verde neon.
Componentes: header com foto do usuário e saldo total, 
gráfico de linha 7 dias, lista de assets com preço e variação 24h,
botões flutuantes de Comprar/Vender na parte inferior.
Estilo: glassmorphism, cantos arredondados 16px.
```

7. Aguarde a geração (cerca de 90 segundos para modo Pro)
8. Refine com prompts de ajuste no chat lateral
9. Exporte: **Figma** (cola direto) ou **Code** (HTML/CSS)

---

## 6. NotebookLM

**Categoria:** Pesquisa e Podcast Automatizado com IA  
**Site Oficial:** https://notebooklm.google.com  
**Acesso:** Login com Google, disponível globalmente

### O que é
IA de pesquisa do Google que cria um especialista personalizado baseado exclusivamente nas fontes que você envia. Sem alucinação de fontes externas — só responde com o que você alimentou.

### Capacidades
- Aceita: PDFs, Google Docs, links de sites, vídeos do YouTube, arquivos de áudio, TXT
- Cada notebook tem seu próprio "universo de conhecimento"
- Citações precisas de onde cada informação veio
- **Audio Overview:** gera episódio de podcast completo (dois hosts, debate natural) sobre o conteúdo das fontes
- Personalização do Audio Overview: tom, foco, formato, idioma (incluindo português)
- Geração de FAQ, briefing, glossário e timeline das fontes

### Limites Free
| Recurso | Limite |
|---------|--------|
| Notebooks | **100 por conta** |
| Fontes por notebook | **50 fontes** |
| Tamanho por fonte | Até 500.000 palavras |
| Audio Overviews | Ilimitados |
| Custo | **100% gratuito** |

### Como usar
1. Acesse https://notebooklm.google.com
2. Login com Google
3. Clique em **New Notebook**
4. Clique em **+ Add source** e escolha o tipo:
   - **Website**: cole a URL
   - **YouTube**: cole o link do vídeo (transcrição automática)
   - **Upload**: PDF, DOCX, TXT, MP3
5. Após adicionar as fontes, faça perguntas no chat
6. Para gerar o podcast: clique em **Audio Overview → Generate** no painel direito

### Exemplo de uso: Podcast de nicho semanal
```
Workflow:
1. Criar notebook "Cripto Semanal"
2. Adicionar 5 artigos da semana (sites de notícias cripto)
3. Adicionar 2 relatórios em PDF de análise de mercado
4. Clicar em Audio Overview → Generate
5. Instrução personalizada: "Gere um podcast em português, tom informal, 
   focado em oportunidades práticas para investidores individuais. 
   Inclua debate sobre os riscos de cada ponto."
6. Baixar o áudio gerado (MP3)
7. Editar levemente no CapCut e publicar no Spotify
```

---

## 7. ComfyUI

**Categoria:** Geração Local de Imagem e Vídeo (nível avançado)  
**GitHub Oficial:** https://github.com/comfyanonymous/ComfyUI  
**ComfyUI Manager:** https://github.com/ltdrdata/ComfyUI-Manager  
**Cloud (sem GPU):** https://rundiffusion.com · https://comfyworkflows.com  

### O que é
Interface de nós (nodes) para pipelines personalizados de geração de imagem e vídeo com IA. Suporta SDXL, FLUX, Wan 2.6, HunyuanVideo, e centenas de extensões. O padrão ouro para controle total sobre a geração.

### Requisitos para instalação local
| Componente | Mínimo | Recomendado |
|-----------|--------|-------------|
| GPU NVIDIA | 8GB VRAM | 16–24GB VRAM |
| RAM | 16GB | 32GB |
| Armazenamento | 50GB livre | 200GB+ (para múltiplos modelos) |
| Python | 3.10+ | 3.11 |
| CUDA | 11.8+ | 12.x |

### Instalação Local (Windows/Linux)

```bash
# 1. Clone o repositório
git clone https://github.com/comfyanonymous/ComfyUI.git
cd ComfyUI

# 2. Instale as dependências Python
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
pip install -r requirements.txt

# 3. Inicie o servidor
python main.py
# Acesse: http://127.0.0.1:8188

# 4. Instale o ComfyUI Manager (para instalar modelos e extensões com 1 clique)
cd custom_nodes
git clone https://github.com/ltdrdata/ComfyUI-Manager.git
# Reinicie o ComfyUI após isso
```

### Baixar modelos (exemplos)
```bash
# Pasta onde ficam os modelos
cd ComfyUI/models/checkpoints

# FLUX.1 Dev (recomendado para qualidade)
# Baixe de: https://huggingface.co/black-forest-labs/FLUX.1-dev

# SDXL Base (boa relação qualidade/velocidade)
# Baixe de: https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0
```

### Acesso Cloud (RunDiffusion — sem GPU)
1. Acesse https://rundiffusion.com
2. Cadastre-se (créditos gratuitos ao criar conta)
3. Clique em **Launch ComfyUI**
4. Interface idêntica à local, rodando em GPU deles na nuvem
5. Upload de workflows personalizados (arquivo `.json`)

### Workflows recomendados para baixar
- **Geração de thumbnails:** https://comfyworkflows.com/workflows (busque "thumbnail YouTube")
- **Upscaling 4x:** integrado via ComfyUI Manager, node Real-ESRGAN
- **Wan 2.6 no ComfyUI:** https://github.com/kijai/ComfyUI-WanVideoWrapper

---

## 8. Lovable.dev

**Categoria:** Construção de Apps Web via Prompt  
**Site Oficial:** https://lovable.dev  
**Acesso:** Cadastro com Google ou e-mail

### O que é
Agente de engenharia de software que gera aplicativos web completos (React + Tailwind + Supabase) a partir de prompts em texto. Publica automaticamente em URL funcional.

### Capacidades
- Geração de frontend em React/Tailwind CSS
- Integração nativa com Supabase (banco de dados PostgreSQL)
- Autenticação de usuários out-of-the-box
- Deploy automático no Lovable Cloud (URL pública imediata)
- Export do código-fonte completo (GitHub sync)
- Iteração via chat: descreva ajustes e ele atualiza o código ao vivo
- Integração com APIs externas (Stripe, SendGrid, etc.)

### Limites Free
- Créditos iniciais ao criar conta (suficientes para 1 a 3 apps completos)
- Código-fonte exportável mesmo após créditos esgotados
- Hospedagem própria no Vercel/Netlify/Railway após export (todos têm planos gratuitos)

### Como maximizar os créditos gratuitos
**Regra de ouro: prompt longo e detalhado na primeira mensagem.**

```
Exemplo de prompt efetivo:

"Crie um app de CRM para clínicas de estética com as seguintes funcionalidades:
1. Autenticação por e-mail e senha (usando Supabase Auth)
2. Dashboard com métricas: total de leads, leads quentes/mornos/frios, 
   conversões do mês
3. Lista de leads com filtros por status e data de cadastro
4. Tela de detalhe do lead com: nome, telefone, procedimento de interesse,
   histórico de contatos, campo de anotações
5. Botão de envio de WhatsApp via link (wa.me/)
6. Tema dark com cores roxo e branco
7. Layout responsivo para mobile e desktop
Banco de dados: Supabase. Stack: React + Tailwind CSS."
```

### Deploy gratuito após export
```bash
# 1. Exporte o código do Lovable (GitHub sync ou Download ZIP)
# 2. Deploy no Vercel (gratuito)
npm install -g vercel
cd seu-projeto
vercel deploy

# 3. Deploy no Railway (gratuito com $5 de crédito mensal)
# Acesse https://railway.app → New Project → Deploy from GitHub
```

---

## 9. OpenCode

**Categoria:** Agente de Código Open Source no Terminal  
**Site Oficial:** https://opencode.ai  
**GitHub (SST):** https://github.com/sst/opencode  
**Documentação:** https://opencode.ai/docs  
**Licença:** MIT (100% gratuito)

### O que é
Agente de código open source com 95.000+ estrelas no GitHub, criado pelo time do SST. Alternativa gratuita ao Claude Code, Cursor e Copilot. Roda no terminal com TUI (Terminal User Interface) completa. Suporta 75+ modelos de IA — você traz sua própria API key.

### Capacidades
- TUI interativa (built com Bubble Tea/Go)
- Suporte a 75+ modelos: OpenAI, Anthropic, Google Gemini, Groq, AWS Bedrock, Ollama (modelos locais gratuitos)
- Lê, edita e cria arquivos em todo o projeto
- Executa comandos shell direto do chat
- LSP integration (code intelligence nativo)
- GitHub Actions integration (revisão automática de PRs)
- Dois agentes: **build** (edição completa) e **plan** (somente leitura, para planejamento)
- Sessões salvas em SQLite local

### Instalação

```bash
# Método mais rápido (qualquer OS)
curl -fsSL https://opencode.ai/install | bash

# macOS (Homebrew — recomendado, sempre atualizado)
brew install anomalyco/tap/opencode

# Windows (Scoop)
scoop install opencode

# Windows (Chocolatey)
choco install opencode

# Node.js (npm/bun/pnpm)
npm install -g opencode-ai

# Arch Linux
paru -S opencode-bin

# Aplicativo Desktop (GUI)
# Download direto: https://opencode.ai/download
# macOS Desktop via Homebrew:
brew install --cask opencode-desktop
```

### Configuração com modelos gratuitos (Gemini via Google AI Studio)
```bash
# 1. Inicie o OpenCode
opencode

# 2. Na primeira execução, ele pedirá a API key
# Cole sua API key do Google AI Studio:
# GOOGLE_API_KEY=sua_chave_aqui

# 3. Selecione o modelo: google/gemini-2.5-pro (gratuito até o limite diário)

# 4. Configure no arquivo ~/.config/opencode/config.json
{
  "model": "google/gemini-2.5-flash",
  "provider": {
    "google": {
      "apiKey": "SUA_API_KEY"
    }
  }
}
```

### Uso com modelos 100% locais (Ollama, custo zero absoluto)
```bash
# 1. Instale o Ollama
curl -fsSL https://ollama.com/install.sh | sh

# 2. Baixe um modelo de código
ollama pull qwen2.5-coder:7b  # Recomendado para desenvolvimento

# 3. Configure o OpenCode para usar Ollama
{
  "model": "ollama/qwen2.5-coder:7b"
}

# 4. Execute
opencode
```

### Uso básico
```bash
# Modo interativo (TUI completa)
opencode

# Modo não-interativo (útil para scripts e automações)
opencode -p "Crie uma função Python que valida CPF"
opencode -p "Revise os arquivos TypeScript em src/ e corrija erros de tipagem"
opencode -p "Crie testes unitários para todos os endpoints em routes/"
```

---

## 10. ElevenLabs

**Categoria:** Clonagem de Voz e TTS Premium  
**Site Oficial:** https://elevenlabs.io  
**Acesso:** Cadastro com e-mail ou Google

### O que é
A plataforma líder em síntese de voz realista. Reconhecida pela qualidade humana do áudio, suporte a 29 idiomas e clonagem de voz a partir de poucos segundos de gravação.

### Capacidades
- Text-to-Speech em 29 idiomas com vozes premium
- **Instant Voice Cloning** (Starter+): clone com 60 segundos de áudio
- **Professional Voice Cloning** (Creator+): clone de alta fidelidade com amostras mais longas
- Dubbing Studio: tradução e dublagem automática de vídeos
- Sound Effects Generator: geração de SFX por prompt
- API completa para integração em apps e automações n8n
- Controle de estabilidade, similaridade e estilo da voz

### Limites por plano
| Plano | Preço | Chars/mês | Clonagem | Uso Comercial |
|-------|-------|-----------|----------|---------------|
| **Free** | $0 | **10.000** (~10 min áudio) | Não | **Não** |
| Starter | $5/mês | 30.000 | Instant (até 10 vozes) | **Sim** |
| Creator | $22/mês | 100.000 | Professional | Sim |
| Pro | $99/mês | 500.000 | Professional | Sim |

> ⚠️ **Atenção:** O tier gratuito **não permite uso comercial**. Para monetizar qualquer conteúdo (YouTube, produtos, serviços), use no mínimo o plano Starter ($5/mês).

### Como usar (Web)
1. Acesse https://elevenlabs.io e crie uma conta
2. No menu lateral: **Speech Synthesis**
3. Escolha uma voz da biblioteca ou clique em **Add Voice**
4. Para clonar sua própria voz: **Voices → Add Voice → Instant Voice Clone**
5. Faça upload de 60 segundos de áudio claro (MP3 ou WAV, sem ruído de fundo)
6. Nomeie a voz e clique em **Add Voice**
7. Agora use ela no Speech Synthesis: cole o texto, selecione a voz, clique em **Generate**

### Como usar via API (Python)
```python
pip install elevenlabs

from elevenlabs.client import ElevenLabs
from elevenlabs import play

client = ElevenLabs(api_key="SUA_API_KEY")

audio = client.generate(
    text="Olá, este é um teste de voz clonada com IA.",
    voice="Rachel",  # ou o ID da sua voz clonada
    model="eleven_multilingual_v2"
)

play(audio)

# Salvar em arquivo
with open("output.mp3", "wb") as f:
    for chunk in audio:
        f.write(chunk)
```

---

## 11. LMNT

**Categoria:** TTS Ultra-Rápido para Desenvolvedores  
**Site Oficial:** https://lmnt.com  
**Documentação API:** https://docs.lmnt.com  
**Acesso:** Playground gratuito sem cadastro; API com conta gratuita

### O que é
Plataforma de TTS focada em latência ultra-baixa (150–200ms). Desenvolvida por ex-engenheiros do Google, usada por Khan Academy e HeyGen. Clone de voz a partir de 5 segundos de áudio. 24 idiomas.

### Capacidades
- Latência de 150–200ms (ideal para agentes de voz em tempo real)
- Voice cloning a partir de apenas 5 segundos de áudio (ou qualidade premium com 5 minutos)
- Clones ilimitados em todos os planos
- Suporte a 24 idiomas com troca de idioma mid-sentence
- API com SDKs para Python e Node.js
- Sem limite de concorrência (sem fila de espera)
- SOC 2 Type II compliance

### Limites por plano
| Plano | Preço | Characters/mês | Uso Comercial |
|-------|-------|----------------|---------------|
| **Free** | $0 | **15.000 chars** | Apenas com atribuição |
| Basic | $10/mês | 200.000 | **Sim** |
| Standard | $49/mês | 1.250.000 | Sim |
| Premium | $199/mês | 5.700.000 | Sim |

### Como usar (API Python)
```bash
pip install lmnt
```

```python
import asyncio
from lmnt.api import Speech

async def main():
    async with Speech("SUA_API_KEY") as speech:
        synthesis = await speech.synthesize(
            "Bitcoin é a maior revolução monetária do século 21.",
            voice="lily",
            language="pt"
        )
        with open("output.mp3", "wb") as f:
            f.write(synthesis["audio"])

asyncio.run(main())
```

### Como clonar uma voz
```python
async with Speech("SUA_API_KEY") as speech:
    # Upload do arquivo de referência (mín. 5 segundos)
    voice = await speech.create_voice(
        name="Minha Voz",
        enhance=True,
        filenames=["referencia_voz.wav"]
    )
    print(f"Voice ID: {voice['id']}")
```

> 💡 **Dica para devs:** O LMNT é a melhor escolha para agentes de atendimento por voz (chatbots de voz, assistentes de WhatsApp com áudio) devido à latência sub-200ms. Para narração de vídeos onde latência não importa, ElevenLabs tem qualidade superior.

---

## 12. Chatterbox (Resemble AI)

**Categoria:** TTS Open Source — Clone de Voz Local Ilimitado  
**GitHub Oficial:** https://github.com/resemble-ai/chatterbox  
**HuggingFace (sem instalação):** https://huggingface.co/spaces/ResembleAI/Chatterbox  
**Demo web:** https://resemble-ai.github.io/chatterbox_demopage  
**Licença:** MIT (uso comercial liberado)

### O que é
O modelo TTS open source mais avançado de 2025, desenvolvido pela Resemble AI. Supera o ElevenLabs em testes cegos (blind tests). Licença MIT — você pode usar em produtos comerciais sem pagar nada. Roda localmente, sem limite de geração.

### Capacidades
- Clone de voz zero-shot (sem treinamento, só um arquivo de referência)
- **Emotion Exaggeration Control**: parâmetro único para controlar intensidade emocional de 0 (monótono) a 1 (dramaticamente expressivo)
- **Paralinguistic Tags** (modelo Turbo): use `[laugh]`, `[cough]`, `[chuckle]`, `[sigh]` no texto
- 23 idiomas no modelo multilingual (incluindo Português)
- 3 modelos: Original (inglês, emoção), Multilingual (23 idiomas), Turbo (mais rápido, paralinguístico)
- Watermark neural invisível (Perth) em todo áudio gerado — detecção de IA embutida
- API compatível com OpenAI TTS (substituto drop-in)

### Instalação Local

```bash
# Pré-requisitos: Python 3.11, CUDA (opcional, funciona em CPU mas mais lento)

# 1. Clone e instale
git clone https://github.com/resemble-ai/chatterbox.git
cd chatterbox
pip install -e .

# 2. Geração básica (inglês)
python -c "
import torchaudio as ta
from chatterbox.tts import ChatterboxTTS

model = ChatterboxTTS.from_pretrained(device='cuda')  # ou 'cpu'

text = 'Bitcoin não é uma moeda. É uma tecnologia de liberdade financeira.'
wav = model.generate(text)
ta.save('output.wav', wav, model.sr)
print('Áudio gerado: output.wav')
"

# 3. Clone de voz (use seu próprio arquivo .wav como referência)
python -c "
import torchaudio as ta
from chatterbox.tts import ChatterboxTTS

model = ChatterboxTTS.from_pretrained(device='cuda')
text = 'Esta é a minha voz clonada com IA de código aberto.'
wav = model.generate(text, audio_prompt_path='minha_voz.wav')
ta.save('voz_clonada.wav', wav, model.sr)
"

# 4. Controle de emoção
python -c "
import torchaudio as ta
from chatterbox.tts import ChatterboxTTS

model = ChatterboxTTS.from_pretrained(device='cuda')
text = 'Isso é incrível! Não acredito que é de graça!'

# exaggeration: 0.0 = monótono, 1.0 = muito expressivo
wav = model.generate(text, exaggeration=0.8, cfg_weight=0.5)
ta.save('expressivo.wav', wav, model.sr)
"
```

### Uso com modelo Turbo (mais rápido + tags paralinguísticas)
```bash
pip install chatterbox-tts  # versão turbo via pip direto
```

```python
from chatterbox.tts import ChatterboxTTS

model = ChatterboxTTS.from_pretrained("ResembleAI/chatterbox-turbo", device="cuda")

# Tags paralinguísticas para naturalidade
text = "Cara, [laugh] você não vai acreditar no que acabei de descobrir. [chuckle] É de graça!"
wav = model.generate(text, audio_prompt_path="referencia.wav")
```

### Uso sem GPU (HuggingFace — zero instalação)
1. Acesse https://huggingface.co/spaces/ResembleAI/Chatterbox
2. Cole seu texto
3. Faça upload de um arquivo .wav de referência (sua voz, 10–30s)
4. Ajuste os parâmetros de emoção
5. Clique em Generate e baixe o áudio

### Servidor com API OpenAI-compatível (para integração com n8n, apps)
```bash
# Repositório da API compatível com OpenAI TTS
git clone https://github.com/travisvn/chatterbox-tts-api.git
cd chatterbox-tts-api

# Via Docker (mais fácil)
docker compose -f docker/docker-compose.yml up -d

# Após iniciar, a API fica disponível em http://localhost:4123
# Documentação Swagger: http://localhost:4123/docs

# Usar exatamente como a API da OpenAI:
curl http://localhost:4123/v1/audio/speech \
  -H "Content-Type: application/json" \
  -d '{
    "model": "chatterbox",
    "input": "Texto para converter em voz",
    "voice": "sua_voz_clonada"
  }' --output audio.mp3
```

---

## 13. ACE Studio 2.0

**Categoria:** Síntese de Voz Cantada por IA  
**Site Oficial:** https://acestudio.ai  
**Download Desktop:** https://acestudio.ai/download  
**Acesso:** Plano gratuito disponível

### O que é
DAW especializada em voz cantada com IA. 140+ vozes AI com estilos variados (Pop, R&B, Rap, Sertanejo, Clássico, Infantil). Cria vocais a partir de MIDI + letra — você tem controle total de pitch, timing e expressividade. 8 idiomas, incluindo Português.

### Capacidades
- 140+ vozes AI treinadas em diferentes gêneros e idiomas
- Editor de fonemas: controle de pronúncia sílaba por sílaba
- Controle de pitch, vibrato, dinâmica e expressão
- Importação de MIDI e audio para guia melódico
- Video Composer: analisa vídeo e gera música + SFX automaticamente para a cena
- Integração com DAWs (Ableton, FL Studio, Logic Pro) via VST/AU
- Exportação de vocais em WAV para uso em qualquer projeto

### Como usar
1. Acesse https://acestudio.ai/download e instale o aplicativo desktop (Windows/macOS)
2. Crie uma conta gratuita
3. Abra o editor, crie um novo projeto
4. Desenhe as notas na piano roll ou importe um arquivo MIDI
5. Adicione a letra nos blocos de nota
6. Selecione uma voz AI na biblioteca
7. Ajuste expressividade, vibrato e timing no painel de parâmetros
8. Exporte o vocal final em WAV

---

## 14. Suno V4.5

**Categoria:** Geração de Música Completa por IA  
**Site Oficial:** https://suno.com  
**Acesso:** Login com Google ou Discord, sem cartão

### O que é
O padrão ouro em geração de músicas completas com IA. Uma descrição de texto gera vocal, letra, melodia, arranjo instrumental e masterização em menos de 60 segundos.

### Capacidades
- Geração de músicas completas com letra e vocal em ~45 segundos
- Todos os gêneros: sertanejo, funk, trap, jazz, clássico, gospel, rock, etc.
- Controle de BPM, tonalidade, estilo vocal, instrumentação
- Continuação de músicas (extend)
- Remix e replicação de estilo
- Geração de instrumental sem vocal
- **Modo Custom:** você escreve a letra completa e o Suno só cria a música

### Limites por plano
| Plano | Preço | Músicas/dia | Uso Comercial |
|-------|-------|-------------|---------------|
| **Free** | $0 | **50 músicas/dia** | **Não** |
| Pro | $8/mês | 500 músicas/mês | **Sim** |
| Premier | $24/mês | 2.000 músicas/mês | Sim |

> ⚠️ No free, os arquivos são hospedados publicamente e não há direitos comerciais. Para monetizar (YouTube, produtos, etc.), use o plano Pro.

### Como usar
1. Acesse https://suno.com
2. Login com Google ou Discord
3. Clique em **Create**
4. Escolha modo **Simple** (prompt livre) ou **Custom** (você escreve a letra)
5. No modo Simple, escreva o prompt:

```
Exemplos de prompts efetivos:

"Sertanejo universitário romântico, voz masculina grave, 
tema: liberdade financeira e Bitcoin, BPM 90, estilo Gusttavo Lima"

"Funk carioca animado, tema: empreendedorismo digital, 
produção trap, voz feminina, letra em português do Brasil"

"Lo-fi hip hop instrumental, chill study music, 
piano melancólico, vinyl crackle, 80 BPM"
```

6. Clique em **Create** e aguarde ~45 segundos
7. Escute as 2 variantes geradas e escolha a melhor
8. Use **Extend** para adicionar bridge, outro refrão ou final

---

## 15. Pippit AI

**Categoria:** Vídeo de Marketing e E-commerce Automatizado  
**Site Oficial:** https://pippit.ai  
**Empresa:** ByteDance (mesma do CapCut e TikTok)  
**Acesso:** Cadastro gratuito, sem cartão

### O que é
Plataforma da ByteDance para criação automatizada de conteúdo de marketing. Cola o link de um produto (Shopify, TikTok Shop, Amazon) e ela gera vídeos, fotos de produto e conteúdo de social media automaticamente.

### Capacidades
- **Link-to-Video:** cole URL de produto → gera múltiplos vídeos de venda
- **AI Avatars:** 600+ avatares realistas em 28 idiomas via 869 vozes
- **Image Studio:** geração em lote de fotos de produto com backgrounds AI
- **AI Talking Photo:** anima fotos estáticas com lip-sync
- **Smart Creations (Beta):** analisa seus assets e gera conteúdo alinhado à marca
- Publicação direta em TikTok, Instagram, YouTube
- Analytics de performance integrado

### Limites Free
| Recurso | Free Tier |
|---------|-----------|
| Créditos | **150 créditos/semana** (renovam semanalmente) |
| Vídeo ~2min | ≈ 2 minutos de vídeo/semana |
| Imagens | ≈ 75 imagens/semana |
| Armazenamento | 500 GB cloud |
| Social accounts | 3 contas |
| Trial 7 dias | 400 créditos, acesso completo |

### Como usar
1. Acesse https://pippit.ai
2. Cadastro com e-mail (sem cartão)
3. No dashboard, clique em **Link to Video**
4. Cole a URL do produto (funciona com Shopify, Amazon, Mercado Livre, TikTok Shop)
5. Escolha o formato de vídeo (Reels 9:16, YouTube 16:9, etc.)
6. Selecione o avatar ou estilo visual
7. Aguarde a geração (~1–2 minutos)
8. Edite o script e o avatar se necessário
9. Exporte ou publique direto

---

## 16. CapCut

**Categoria:** Edição de Vídeo com Recursos de IA  
**Site Oficial:** https://capcut.com  
**Desktop:** https://www.capcut.com/capcut_pc  
**Mobile:** App Store / Google Play  
**Empresa:** ByteDance

### O que é
O editor de vídeo mais popular do mundo com recursos de IA integrados. Gratuito e extremamente poderoso para criadores de conteúdo.

### Capacidades com IA (no plano gratuito)
- **Auto Captions:** legendas automáticas com IA em português com timing perfeito
- **AI Background Remove:** remove background de vídeo sem chroma key
- **AI Script to Video:** gera vídeo completo a partir de texto
- **Auto Beat Sync:** sincroniza cortes na batida da música automaticamente
- **AI Voice:** troca de voz em tempo real
- **Enhance Face:** melhoria automática de rosto em vídeos
- **Magic Eraser:** remove objetos indesejados de vídeos frame a frame
- **AI Stickers e Efeitos:** biblioteca de efeitos gerados por IA

### Como usar (Web — sem instalação)
1. Acesse https://capcut.com
2. Login com TikTok, Google ou e-mail
3. Clique em **Create New Project**
4. Faça upload do seu vídeo
5. No painel direito, explore: **Captions → Auto Captions** para legendas automáticas
6. Para remover fundo: selecione o clip → **Remove BG**
7. Para Magic Eraser: selecione região → **Edit → Smart Remove**

---

### O que é
Ferramentas baseadas em inpainting de IA para remover objetos, pessoas, texto, logos ou qualquer elemento indesejado de imagens de forma realista.

### Magic Eraser — Limites Free
| Recurso | Free |
|---------|------|
| Imagens/dia | **6 imagens** |
| Resolução | Até 4K |
| Marcas d'água | Não |
| API | Disponível (planos pagos) |

### Como usar (Magic Eraser)
1. Acesse https://magiceraser.org/
2. Faça upload da imagem (PNG, JPG, WebP)
3. Use o pincel para pintar sobre o que quer remover
4. Ajuste o tamanho do pincel conforme necessário
5. Clique em **Clean** e aguarde 3–5 segundos
6. Download da imagem processada

### Alternativas gratuitas ilimitadas
- **Inpaint Web (local):** https://github.com/lkwq007/IOPaint — roda localmente, ilimitado
- **Google Fotos Magic Eraser:** disponível no app Google Fotos (Android/iOS)
- **CapCut Smart Remove:** integrado no editor de vídeo

---

## 🔗 Links Rápidos — Todos em um lugar

### Geração de Vídeo
- Wan 2.6 (web): https://huggingface.co/spaces/Wan-AI/Wan2.1-T2V-14B
- Wan 2.6 (GitHub): https://github.com/Wan-Video/Wan2.1
- Kling AI: https://klingai.com
- Hailuo AI: https://hailuoai.video

### Imagem e Design
- Google Stitch: https://stitch.withgoogle.com
- Ideogram: https://ideogram.ai
- Leonardo AI: https://app.leonardo.ai
- ComfyUI: https://github.com/comfyanonymous/ComfyUI

### APIs e Desenvolvimento
- Google AI Studio: https://aistudio.google.com
- OpenCode: https://opencode.ai
- Lovable: https://lovable.dev

### Pesquisa e Conteúdo
- NotebookLM: https://notebooklm.google.com

### Áudio e Voz
- ElevenLabs: https://elevenlabs.io
- LMNT: https://lmnt.com
- Chatterbox (GitHub): https://github.com/resemble-ai/chatterbox
- Chatterbox (HuggingFace): https://huggingface.co/spaces/ResembleAI/Chatterbox
- ACE Studio: https://acestudio.ai
- Suno: https://suno.com

### Marketing e Edição
- Pippit AI: https://pippit.ai
- CapCut: https://capcut.com
- Cleanup Pictures: https://cleanup.pictures

---

## 📺 Sobre o Canal

- 📺 YouTube: https://www.youtube.com/channel/UCeuFBcGylQkMhDvlnLvgAxg
- 💬 Comunidade (Patreon): Fluxos, automações e projetos reais que usamos nas nossas empresas
- 📧 Newsletter: Análises semanais de ferramentas, casos de uso e oportunidades de negócio com IA

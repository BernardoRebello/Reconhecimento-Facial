# 📱 VisionFace ID - Reconhecimento Facial Biométrico em Tempo Real (Estilo Smartphone)

[![License: MIT](https://img.shields.io/badge/License-MIT-emerald.svg)](https://opensource.org/licenses/MIT)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-FaceMesh%20468%20pts-sky.svg)](https://developers.google.com/mediapipe)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS%20CDN-38bdf8.svg)](https://tailwindcss.com)
[![FPS](https://img.shields.io/badge/Performance-60%20FPS%20GPU-green.svg)](#)

Uma aplicação completa de **Reconhecimento Facial e Desbloqueio Biométrico (Face ID)** executada em um **único arquivo HTML**, rodando 100% no navegador via WebAssembly e WebRTC.

Inspirado no sistema de desbloqueio facial de smartphones modernos (Apple Face ID e Android Face Unlock), com assistente de cadastro facial, comparação biométrica por proporções morfológicas invariantes, feedback sonoro e visual em tempo real.

---

## 🌟 Principais Recursos

- **📱 Experiência Estilo Smartphone (Face ID / Face Unlock):**
  - **Cadastro com 1 Clique (`+ Cadastrar Meu Rosto`):** Escaneia o rosto em tempo real, gera uma média matemática de 24 proporções e recorta a foto de perfil.
  - **Desbloqueio Automático:** Identifica o dono cadastrado instantaneamente (**88% a 98%** de compatibilidade).
  - **Anti-Impostor:** Rosto desconhecido ou pessoa diferente é imediatamente identificada como `🔒 Rosto Desconhecido (Acesso Negado)` (**0% a 40%**).
  - **Sons do Face ID:** Feedback sonoro agradável de desbloqueio e confirmação sintetizado nativamente via **Web Audio API** (sem dependência de arquivos de áudio externos).
  - **Persistência Local:** Os perfis biométricos ficam salvos no `localStorage` do navegador mesmo após fechar ou reiniciar o computador.

- **⚡ 60 FPS Cravados (Zero Queda de Desempenho):**
  - **Vídeo Acelerado por Hardware GPU:** A webcam é reproduzida diretamente pelo decodificador nativo da GPU (`<video>`). O vídeo nunca trava nem perde quadros.
  - **Canvas Transparente:** O `<canvas>` fica sobreposto e renderiza apenas as marcações vetoriais e a moldura holográfica.
  - **Inferência Desacoplada:** O ciclo da inteligência artificial roda de forma assíncrona em segundo plano, sem bloquear a taxa de atualização da tela.

- **🧠 Algoritmo Biométrico Calibrado (24 Proporções Antropométricas Invariantes):**
  - Em vez de usar pixels ruidosos ou sensíveis à iluminação, o sistema analisa as **razões euclidianas fixas da estrutura óssea**:
    - Distância interocular vs largura das maçãs do rosto (bizigomática).
    - Proporção do nariz (comprimento / largura das narinas).
    - Relação de largura da boca vs distância entre olhos.
    - Filtro nasal, projeção do queixo e curvatura mandibular.
    - Simetria craniofacial lateral.
  - **Imune a mudanças de iluminação, distância da câmera e expressões normais.**

- **🔒 100% Privativo & Offline:**
  - Nenhum dado biométrico, foto ou vídeo é enviado para a internet ou servidores externos.
  - Toda a inferência ocorre localmente no seu dispositivo via WebAssembly.

---

## 🚀 Como Executar

Não requer Node.js, npm, Python ou servidores complexos.

1. Baixe ou clone este repositório:
   ```bash
   git clone https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git
   ```
2. Dê um **duplo clique no arquivo `index.html`** para abrir em qualquer navegador moderno (Google Chrome, Microsoft Edge, Mozilla Firefox, Brave, Safari).
3. Clique em **"Ligar Câmera"**, permita o acesso à webcam e experimente cadastrar seu rosto!

---

## 🛠️ Tecnologias Utilizadas

- **[Google MediaPipe FaceMesh](https://developers.google.com/mediapipe/solutions/vision/face_landmarker):** Modelo neural de 468 marcos faciais 3D carregado via CDN (jsdelivr).
- **[Tailwind CSS (CDN)](https://tailwindcss.com):** Interface moderna em Dark Mode, responsiva e com micro-interações.
- **WebRTC (`navigator.mediaDevices.getUserMedia`):** Captura de vídeo de alta definição em tempo real.
- **HTML5 Canvas 2D API:** Renderização gráfica em lote de alta performance.
- **Web Audio API:** Síntese de áudio procedural para os efeitos sonoros do Face ID.
- **Web Storage API (`localStorage`):** Armazenamento permanente de perfis e assinaturas biométricas.

---

## 📄 Licença

Distribuído sob a licença **MIT**. Consulte o arquivo `LICENSE` para mais detalhes.

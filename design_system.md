# Design System - Portfólio Bento Box

Este documento descreve as diretrizes visuais, componentes, micro-interações e tokens de design utilizados no portfólio de **Caio Pestana**. O sistema foca em uma estética minimalista, moderna, com layout "Bento Box" otimizado para visualização em tela única (single-screen) no desktop, adaptação fluida no mobile e suporte nativo a temas Light e Dark.

---

## 1. Visão Geral
- **Estilo:** Minimalista, Bento Box, Premium High-End.
- **Cores Predominantes:** Verde Menta (`#A2D5C6`), Cinza Escuro Refinado (`#1b1b1b`), Creme (`#F9F8F6`).
- **Filosofia:** Hierarquia visual clara, espaços em branco generosos (white space), micro-interações fluidas e acessibilidade universal.

---

## 2. Cores (Design Tokens)

### ☀️ Light Mode
| Token | Valor | Descrição |
| :--- | :--- | :--- |
| `--bg-page` | `#CFFFE2` | Fundo principal da página (Menta Suave) |
| `--bg-card` | `#F9F8F6` | Fundo dos cards (Off-white/Creme) |
| `--bg-card-element` | `#A2D5C6` | Elementos de destaque/Hover |
| `--text-main` | `#000000` | Texto principal e títulos |
| `--text-muted` | `#4A4A4A` | Texto secundário e legendas |
| `--border-color` | `#A2D5C6` | Bordas sutis e divisores padrão do site |
| *Borda de Estudos / Sobre* | `rgba(0, 0, 0, 0.08)` | Bordas cinza-claro ultra sutis para cards de estudos e foto de biografia |

### 🌙 Dark Mode
| Token | Valor | Descrição |
| :--- | :--- | :--- |
| `--bg-page` | `#1b1b1b` | Fundo principal (Cinza Escuro Refinado) |
| `--bg-card` | `#1b1b1b` | Mesma cor do fundo para efeito de profundidade via bordas |
| `--bg-card-element` | `#A2D5C6` | Destaques no Dark Mode |
| `--bg-element-dark` | `#CFFFE2` | Elementos que invertem para Verde Claro |
| `--text-main` | `#F9F8F6` | Texto principal (Creme) |
| `--text-muted` | `#A2D5C6` | Texto secundário (Menta) |
| `--border-color` | `rgba(255, 255, 255, 0.1)` | Bordas translúcidas (Cinza sutil do tema escuro) |

---

## 3. Tipografia
- **Fonte Principal:** Space Grotesk (Local - `/Space_Grotesk/static/`)
- **Pesos Utilizados:** 300 (Light), 400 (Regular), 500 (Medium), 600 (SemiBold), 700 (Bold).
- **Fallbacks:** sans-serif.

---

**Hierarquia Visual:** Baseada em pesos (*font-weight*) e espaçamentos (*letter-spacing*).

| Elemento | Tamanho | Peso | Espaçamento | Cor |
| :--- | :--- | :--- | :--- | :--- |
| **H1 (Nome / Títulos de Projeto)** | `36px` / `48px` | `700` | `-1.5px` / `-2.5px` | `--text-main` |
| **H2 (Cargo)** | `18px` | `500` | `0` | `--text-muted` |
| **Títulos de Seção**| `13px` | `800` | `2px` (Caps) | `--text-muted` |
| **H3 (Projetos / Cards de Estudo)** | `16px` | `700` | `1.5px` (Caps) | `--text-main` |
| **Corpo de Texto** | `14px` | `400` | `0` (Line-height 1.7)| `--text-main` |
| **Tooltips / Badges** | `11px` - `12px` | `700` | `0` | `--text-main` / `--bg-element-dark` |

---

## 4. Layout & Espaçamento

### 🍱 Bento Box Otimizado
- **Grid Principal:** Duas colunas (`320px` Sidebar \| `1fr` Conteúdo).
- **Mobile Grid:** Transição para 1 coluna abaixo de `768px`.
- **Gap entre Seções:** `24px` (Desktop) / `20px` (Mobile).
- **Padding Lateral Header:** `32px 40px` (Desktop) / `16px` (Mobile).
- **Padding dos Cards:** `40px` (Desktop) / `20px-24px` (Mobile).

### 📏 Bordas (Radius)
- **Cards Principais:** `32px` (`--border-radius-lg`).
- **Cards Internos / Cards de Estudos:** `24px` (`--border-radius-md`).
- **Botões / Pílulas / Tooltips:** `999px` (`--border-radius-full`).
- **Botões de Modais / Highlights:** `18px` (`--border-radius-sm`).

---

## 5. Componentes do Sistema

### 📋 Sidebar (Página Inicial)
- **Localização:** Ícone de pin (`ph-map-pin`) com texto `BSB (DF) - JLLE (SC)` posicionado no topo antes da formação acadêmica.
- **Hierarquia:** Títulos com `margin-bottom: 24px` para separação clara.
- **Texto:** Parágrafos com `margin-bottom: 16px` para facilitar a leitura.
- **Scrollbar:** Customizada em verde menta (`#8EBAAC`), fina e discreta.

### 🖼️ Cabeçalho Global Padronizado
- **Estrutura Limpa:** Sem geolocalização (dedicada à sidebar da home), exibindo apenas Foto de Perfil flipable, Nome, Cargo animado, Virtual Pet e dois grupos de ações:
  - **Ações Superiores:** Botão Home (`ph-house`), Alternador de Tema (`ph-sun`/`ph-moon`) e Botão de Idioma (`ph-translate`).
  - **Ações Inferiores:** Botões de navegação rápida: **Sobre**, **Currículo** e **Estudos**.
- **Distribuição Mobile:** Em telas pequenas, os botões inferiores preenchem a largura de forma proporcional (`flex: 1 1 0`), com altura mínima de toque (`min-height: 40px` / `38px`) para garantir acessibilidade (WCAG).

### 💬 Sistema Universal de Tooltips
O projeto conta com tooltips integradas via atributos `data-tooltip-pt`, `data-tooltip-en` e `data-tooltip`:
1. **Redes Sociais:** Balões flutuantes acima de cada ícone social com setas direcionais.
2. **Foto de Perfil do Header:** Balão estilo pílula sobreposto na parte inferior da imagem (`bottom: 12px; left: 50%`) com texto *"Olha eu aqui!"* / *"Hello there!"*.
3. **Capas de Projetos (Home):** Balão estilo pílula sobreposto na base da imagem com texto *"Ver projeto"* / *"View project"*.
4. **Foto da Página Sobre:** Balão estilo fala de personagem acima da foto com rabicho apontando para a cabeça da imagem e texto *"Esse sou eu."* / *"That's me."*.

### 👤 Página "Sobre Mim" (`sobre.html`)
- **Layout:** Grid de duas colunas no desktop (`1.2fr` texto \| `0.8fr` foto de perfil).
- **Mobile:** A foto sobe automaticamente para o topo via `order: -1` logo abaixo do título, com largura máxima reduzida (`max-width: 200px`) e alinhamento à esquerda.
- **Carregamento Responsivo de Imagem:** Uso da tag `<picture>` carregando `assets/foto-eu-mobile.webp` no mobile (`max-width: 1024px`) e `assets/foto-eu.webp` no desktop.

### 📚 Lista de Projetos de Estudo (`projetos-estudos.html`)
- **Cards de Estudo:** Cards verticais com capa de `480px` (desktop) / `220px` (mobile).
- **Placeholders Futuros:** Cards 2 e 3 padronizados com o ícone de paleta de tinta (`ph-palette`) e título/descrição *"Em breve"* / *"Coming soon"*.

### ✉️ Footer CTA (custom-cta)
- **Design:** Bloco centralizado com fundo verde-menta `#A2D5C6` e botão preto `#1b1b1b` no Dark Mode (cores invertidas no Light Mode).
- **Link Notion / Contato:** Botão direto para proposta com espaçamento vertical compacto (`40px` desktop / `32px` mobile).

---

## 6. Interatividade & Micro-animações

- **Transições Suaves de Navegação:**
  - **Entrada:** Animação `pageFadeIn` com leve subida de `4px` em `0.35s` (`cubic-bezier(0.4, 0, 0.2, 1)`).
  - **Saída:** Transição suave de fade-out de `250ms` ao clicar em qualquer link interno `.html`.
- **Sincronização de Tema do Navegador:**
  - Detecção nativa de preferência do sistema via `prefers-color-scheme: dark`.
  - Execução imediata no topo do body evitando *flash of unstyled content* (FOUC).
  - Persistência das escolhas manuais do usuário no `localStorage` sob a chave `dark-mode`.
- **Detecção de Idioma do Navegador:**
  - Leitura automática de `navigator.language` definindo inglês (`en`) ou português (`pt`) no primeiro acesso.
  - Persistência no `localStorage` sob a chave `portfolio-lang`.
- **Virtual Pet Persistente:**
  - Posição horizontal (`posX`) e direção do movimento (`velX`) são salvas no `beforeunload` e restauradas em cada navegação entre páginas.
  - Normalização segura de limites (`bounds`) garantindo que o mascote nunca fique fora da tela ao redimensionar o dispositivo.
- **Efeito de Digitação Humana (Typing Effect):**
  - Digitação e exclusão cíclica de especialidades com suporte a tradução síncrona via `MutationObserver`.

---

## 7. Melhores Práticas & Acessibilidade

- **Acessibilidade (WCAG):** Contraste calibrado em ambos os modos; áreas de toque em botões mobile `>= 44px` / `>= 38px`.
- **Performance:** Imagens em formato moderno `.webp` com tags `<picture>` responsivas; animações aceleradas por GPU.
- **SEO & Semântica:** Uso rigoroso de tags semânticas (`<main>`, `<header>`, `<nav>`, `<aside>`, `<picture>`).
- **Favicon Multi-dispositivo:** Declarado via `favicon.png` e `apple-touch-icon` em todas as páginas para renderização nítida em desktops, iOS e Android.
- **Alinhamento do ANO no Mobile:** Nos projetos e estudos, o título fica à esquerda e a tag `ANO` alinhada à direita na mesma linha horizontal (`flex-direction: row; justify-content: space-between`).

# Guia de Animações: Thomas Birthday Website

Este guia detalha as animações para o website de aniversário do Thomas, com o objetivo de criar uma experiência de usuário fluida, imersiva e ultra-premium. As animações serão implementadas principalmente com **Framer Motion** e **GSAP**, aproveitando suas capacidades para performance e complexidade. A consistência nas durações e curvas de easing é fundamental para a coesão visual do projeto.

## Princípios Gerais de Animação

As animações no Thomas Birthday Website devem aderir aos seguintes princípios para garantir uma experiência de alta qualidade:

- **Fluidez e Suavidade**: Todas as transições e movimentos devem ser suaves, sem engasgos, mesmo em dispositivos com menor capacidade de processamento. A prioridade é a experiência do usuário.

- **Intencionalidade**: Cada animação deve ter um propósito claro, seja para guiar o usuário através da interface, fornecer feedback visual sobre interações, ou aprimorar a narrativa visual e a imersão no tema futurista.

- **Performance**: Priorizar animações que utilizem propriedades CSS otimizadas, como `transform` e `opacity`, para aproveitar a aceleração de hardware. Evitar animações que causem `reflows` ou `repaints` desnecessários.

- **Consistência**: Manter um estilo, ritmo e curvas de easing consistentes em todo o site para criar uma linguagem visual unificada.

- **Acessibilidade**: Oferecer opções para reduzir ou desativar animações para usuários com sensibilidade a movimentos, garantindo que o site seja inclusivo.

## Curvas de Easing Padrão

Para manter a consistência e a qualidade das animações, as seguintes curvas de easing devem ser utilizadas:

| Nome | Curva `cubic-bezier` | Uso |
| --- | --- | --- |
| **`easeOutExpo`** | `cubic-bezier(0.16, 1, 0.3, 1)` | Animações de entrada de elementos grandes ou transições impactantes. |
| **`easeOutQuad`** | `cubic-bezier(0.25, 0.46, 0.45, 0.94)` | Interações rápidas de UI, como hover de botões. |
| **`easeOutCubic`** | `cubic-bezier(0.215, 0.61, 0.355, 1)` | Animações de rolagem e entrada de seções. |
| **`easeOutBack`** | `cubic-bezier(0.34, 1.56, 0.64, 1)` | Animações de entrada com um leve "overshoot" (efeito elástico). |
| **`easeOutSine`** | `cubic-bezier(0.39, 0.575, 0.565, 1)` | Feedback de clique ou pequenas interações. |
| **`easeInOutSine`** | `cubic-bezier(0.445, 0.05, 0.55, 0.95)` | Animações de loop contínuo ou carregamento. |
| **`easeOutQuint`** | `cubic-bezier(0.23, 1, 0.32, 1)` | Transições de página e revelações de conteúdo mais longas. |
| **`Linear`** | `cubic-bezier(0, 0, 1, 1)` | Movimentos contínuos e previsíveis, como parallax de fundo. |

## Animações Detalhadas por Seção/Componente

### 1. Animação de Abertura (Opening Animation)

Esta sequência de animações ocorre na primeira carga da página, estabelecendo o tom futurista do site. Elementos como o logo, título principal e o herói urbano da seção Hero devem aparecer de forma coordenada e impactante.

- **Duração**: Aproximadamente 2-3 segundos para a sequência completa.

- **Easing**: Principalmente `easeOutQuint` para a maioria dos elementos, com `easeOutBack` para o herói.

- **Detalhes**: O fundo pode se revelar gradualmente (fade-in), seguido pela entrada animada do herói (slide-up e leve escala com `easeOutBack`). Por fim, o texto principal deve ser revelado utilizando o componente `TextReveal`.

- **Ferramentas**: `GSAP Timeline` para orquestração da sequência, `Framer Motion` para animações de elementos individuais e `TextReveal`.

### 2. Animação da Seção Hero (Hero Animation)

Animações complexas dentro da `HeroSection` (conforme `COMPONENT_LIST.md`), incluindo o movimento da cidade futurista, a entrada do herói urbano e a revelação do texto. A cidade pode ter um leve movimento parallax ou partículas flutuantes para adicionar dinamismo.

- **Duração**: Contínua para elementos de fundo (cidade, partículas), 1-2 segundos para entrada de elementos específicos.

- **Easing**: `easeOutQuint` para entradas, `Linear` para movimentos contínuos.

- **Detalhes**: O herói pode ter uma animação de entrada sutil (fade-in e slide-up) e um efeito de "idle" (respiração ou movimento sutil) enquanto visível. O texto deve utilizar o componente `TextReveal` para um efeito de digitação ou surgimento. O fundo da cidade deve usar o componente `ParallaxEffect`.

- **Ferramentas**: `GSAP` para a cidade e herói, `Framer Motion` para o texto e `ParallaxEffect`.

### 3. Animação da Contagem Regressiva (Countdown Animation)

Os números da contagem regressiva (`CountdownSection` em `COMPONENT_LIST.md`) devem ter uma animação de transição suave a cada mudança de dígito (e.g., flip card, fade-in/fade-out com leve escala). O fundo da seção pode ter um brilho sutil ou pulsação para enfatizar a proximidade do evento.

- **Duração**: 0.5 segundos por transição de número.

- **Easing**: `easeOutExpo`.

- **Detalhes**: Cada dígito da contagem regressiva deve ser um componente animado individualmente, permitindo um controle preciso sobre a transição. Um efeito de `flip` ou `fade-scale` é recomendado.

- **Ferramentas**: `Framer Motion` para animação dos dígitos.

### 4. Hover de Botão (Button Hover)

Efeitos de hover para botões (`Button` em `COMPONENT_LIST.md`) que adicionam um toque premium e feedback visual ao usuário. Estes efeitos devem ser sutis, mas impactantes.

- **Duração**: 0.2-0.3 segundos.

- **Easing**: `easeOutQuad`.

- **Detalhes**: Botões primários podem ter um `box-shadow` neon animado que se intensifica no hover. Botões secundários podem ter um preenchimento sutil ou uma mudança de cor de borda. Botões `ghost` podem ter uma mudança de cor de texto e uma leve escala.

- **Ferramentas**: `Framer Motion` para gerenciar os estados de hover e transições.

### 5. Animações de Rolagem (Scroll Animations)

Elementos que aparecem ou se transformam à medida que o usuário rola a página, criando uma experiência de descoberta. Isso inclui fade-ins, slide-ups e rotações sutis para seções inteiras ou componentes individuais.

- **Duração**: 0.8-1.2 segundos para a maioria das animações de entrada.

- **Easing**: `easeOutCubic`.

- **Detalhes**: Utilizar a `Intersection Observer API` para disparar animações quando os elementos entram na viewport. Pode ser aplicado a `Card`s, títulos de seção e blocos de conteúdo. O `GSAP ScrollTrigger` pode ser usado para orquestrar animações mais complexas baseadas na posição de rolagem.

- **Ferramentas**: `Framer Motion` (com `whileInView` ou `useInView` hook), `GSAP ScrollTrigger`.

### 6. Animações de Cartões (Cards Animations)

Além do hover, os cartões (`Card` e `GiftCard` em `COMPONENT_LIST.md`) devem ter uma animação de entrada (fade-in e slide-up) quando aparecem na tela. Ao clicar, podem ter uma animação de feedback (leve escala ou pulsação).

- **Duração**: Entrada: 0.5-0.7 segundos. Clique: 0.15 segundos.

- **Easing**: Entrada: `easeOutBack`. Clique: `easeOutSine`.

- **Detalhes**: Animações em cascata para múltiplos cartões na `GiftListSection` são recomendadas, onde cada cartão aparece com um pequeno atraso em relação ao anterior.

- **Ferramentas**: `Framer Motion`.

### 7. Parallax

Efeitos de rolagem parallax para elementos de fundo ou imagens específicas, criando uma sensação de profundidade e imersão. Este efeito é crucial para a `HeroSection`.

- **Duração**: Contínua, baseada na posição de rolagem.

- **Easing**: `Linear`.

- **Detalhes**: Aplicado à cidade futurista na `HeroSection` e, possivelmente, a imagens de fundo em outras seções para criar camadas visuais. O componente `ParallaxEffect` deve ser utilizado.

- **Ferramentas**: Componente `ParallaxEffect` customizado usando `GSAP`.

### 8. Animação de Fundo (Background Animation)

Um fundo dinâmico e sutil, como estrelas em movimento lento, partículas abstratas ou gradientes animados, para adicionar profundidade e futurismo ao ambiente geral do site.

- **Duração**: Contínua, em loop.

- **Easing**: `Linear` ou `easeInOutSine` para movimentos cíclicos.

- **Detalhes**: Pode ser implementado com CSS `keyframes` para gradientes ou movimentos simples, WebGL (se a performance permitir e for justificado) ou bibliotecas de partículas como `react-tsparticles` para efeitos mais complexos. Deve ser discreto para não competir com o conteúdo principal.

- **Ferramentas**: CSS, ou uma biblioteca como `react-tsparticles`.

### 9. Cursor Personalizado (Cursor Animation)

Um cursor personalizado (`CursorFollower` em `COMPONENT_LIST.md`) que reage a interações, como hover em links e botões, com um efeito de "blob" ou "dot" que se expande ou muda de cor. Adiciona um toque futurista e interativo à experiência.

- **Duração**: 0.1-0.2 segundos para transições de estado.

- **Easing**: `easeOutCirc`.

- **Detalhes**: O `CursorFollower` deve ser um componente global que reage a eventos de mouse em todo o documento, alterando sua aparência com base nos elementos sob o cursor (e.g., links, botões, áreas interativas).

- **Ferramentas**: `React` (para eventos de mouse), `Framer Motion` para animar o movimento e os efeitos visuais do cursor.

### 10. Animação de Carregamento (Loading Animation)

Uma tela de carregamento elegante que aparece antes do conteúdo principal ser renderizado, com um spinner futurista ou uma animação abstrata. Essencial para uma experiência de usuário premium, minimizando a percepção de espera.

- **Duração**: Variável, dependendo do tempo de carregamento dos recursos. A animação do spinner deve ser contínua.

- **Easing**: `easeInOutSine` para o spinner, `easeOutQuint` para o fade-out da tela de carregamento.

- **Detalhes**: A tela de carregamento deve ter um fade-out suave quando todos os recursos essenciais forem carregados. O spinner pode ser um elemento SVG animado ou um componente Framer Motion.

- **Ferramentas**: `Framer Motion`.

### 11. Transições de Página (Page Transitions)

Animações suaves ao navegar entre diferentes páginas ou seções, como um fade-out/fade-in ou um slide horizontal. Isso proporciona uma sensação de continuidade e fluidez na navegação.

- **Duração**: 0.5-0.8 segundos.

- **Easing**: `easeOutQuint`.

- **Detalhes**: Implementado com as funcionalidades de roteamento do Next.js e o componente `AnimatePresence` do Framer Motion, permitindo que as páginas de saída animem antes de serem removidas do DOM.

- **Ferramentas**: `Framer Motion` (`AnimatePresence`), `Next.js Router`.

## Recomendações de Performance

Para garantir que todas as animações rodem de forma suave e eficiente, as seguintes recomendações devem ser seguidas:

- **Hardware Acceleration**: Sempre que possível, utilizar `transform` (e.g., `translate`, `scale`, `rotate`) e `opacity` para animações CSS e JavaScript, pois são propriedades que podem ser aceleradas por hardware.

- **Debounce/Throttle**: Aplicar técnicas de `debounce` ou `throttle` para eventos de rolagem, redimensionamento e movimento do mouse para evitar a execução excessiva de funções e re-renderizações desnecessárias.

- **Lazy Loading**: Implementar lazy loading para imagens (`next/image`) e componentes que estão fora da viewport inicial, carregando-os apenas quando se tornam visíveis ou estão prestes a se tornar.

- **Otimização de Imagens e Ativos**: Usar formatos de imagem modernos (WebP, AVIF) e tamanhos adequados. Otimizar SVGs e outros ativos gráficos.

- **Minimizar Reflows e Repaints**: Evitar animações que alterem propriedades de layout (e.g., `width`, `height`, `margin`, `padding`) sempre que possível, pois elas forçam o navegador a recalcular o layout e repintar a página, impactando a performance.

- **Testar em Diferentes Dispositivos**: Realizar testes rigorosos em uma variedade de dispositivos (desktop, tablet, mobile) e navegadores para garantir que as animações funcionem bem em todas as plataformas.

- **Remover Listeners**: Garantir que os event listeners de animação e rolagem sejam removidos corretamente para evitar vazamentos de memória.

Este guia é um documento vivo e será atualizado conforme o projeto evolui. Aderir a estas diretrizes é fundamental para o sucesso visual e funcional do Thomas Birthday Website.

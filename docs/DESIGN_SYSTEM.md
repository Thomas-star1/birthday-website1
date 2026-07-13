# Design System: Thomas Birthday Website

Este documento define o sistema de design para o website de aniversário do Thomas, garantindo consistência visual e uma estética ultra-premium e futurista. As especificações aqui detalhadas devem ser rigorosamente seguidas pela equipe de desenvolvimento para manter a integridade do design.

## 1. Cores

A paleta de cores foca em um tema escuro sofisticado, com tons neon para destaques e contrastes. Todas as cores devem ser implementadas como variáveis CSS ou tokens de design no Tailwind CSS para facilitar a manutenção e a consistência.

| Nome | Hex | RGB | HSL | Uso |
| --- | --- | --- | --- | --- |
| **Background Base** | `#050505` | `rgb(5, 5, 5)` | `hsl(0, 0%, 2%)` | Fundo principal da aplicação, garantindo um ambiente escuro profundo. |
| **Background Surface** | `#111111` | `rgb(17, 17, 17)` | `hsl(0, 0%, 7%)` | Fundo de cartões, modais e elementos sobrepostos, criando uma leve distinção do fundo base. |
| **Primary Accent** | `#00F0FF` | `rgb(0, 240, 255)` | `hsl(183, 100%, 50%)` | Cor principal de destaque (Cyan Neon), utilizada em botões primários, links interativos e elementos que exigem atenção. |
| **Secondary Accent** | `#FF003C` | `rgb(255, 0, 60)` | `hsl(346, 100%, 50%)` | Cor secundária de destaque (Red Neon), reservada para alertas, mensagens de erro ou elementos de ação secundária de alto impacto. |
| **Text Primary** | `#FFFFFF` | `rgb(255, 255, 255)` | `hsl(0, 0%, 100%)` | Cor principal para títulos, textos de alta legibilidade e conteúdo de maior ênfase. |
| **Text Secondary** | `#A0A0A0` | `rgb(160, 160, 160)` | `hsl(0, 0%, 63%)` | Cor para textos secundários, descrições, legendas e conteúdo de média ênfase. |
| **Text Muted** | `#555555` | `rgb(85, 85, 85)` | `hsl(0, 0%, 33%)` | Cor para textos desativados, placeholders ou elementos de baixa ênfase, garantindo contraste mínimo. |
| **Border Color** | `#222222` | `rgb(34, 34, 34)` | `hsl(0, 0%, 13%)` | Cor para bordas de elementos, divisores e linhas sutis, complementando o tema escuro. |

## 2. Tipografia

A tipografia deve transmitir modernidade e clareza, utilizando fontes sem serifa geométricas que se alinhem à estética futurista. As fontes `Inter` e `SF Pro Display/Text` são as preferenciais, com `Inter` sendo a principal para compatibilidade web. Os tamanhos e pesos devem ser responsivos, adaptando-se a diferentes viewports.

| Elemento | Fonte | Peso | Tamanho (Desktop - `rem`/`px`) | Tamanho (Mobile - `rem`/`px`) | Line-height (Desktop) | Line-height (Mobile) |
| --- | --- | --- | --- | --- | --- | --- |
| **Display (Hero)** | `Inter` (fallback: `SF Pro Display`) | 800 (Extra Bold) | `5rem` (`80px`) | `3rem` (`48px`) | `1.1` | `1.2` |
| **H1** | `Inter` (fallback: `SF Pro Display`) | 700 (Bold) | `4rem` (`64px`) | `2.5rem` (`40px`) | `1.2` | `1.25` |
| **H2** | `Inter` (fallback: `SF Pro Display`) | 600 (Semi Bold) | `3rem` (`48px`) | `2rem` (`32px`) | `1.25` | `1.3` |
| **H3** | `Inter` (fallback: `SF Pro Display`) | 600 (Semi Bold) | `2rem` (`32px`) | `1.5rem` (`24px`) | `1.3` | `1.35` |
| **Body Large** | `Inter` (fallback: `SF Pro Text`) | 400 (Regular) | `1.25rem` (`20px`) | `1.125rem` (`18px`) | `1.5` | `1.5` |
| **Body Regular** | `Inter` (fallback: `SF Pro Text`) | 400 (Regular) | `1rem` (`16px`) | `1rem` (`16px`) | `1.6` | `1.6` |
| **Body Small** | `Inter` (fallback: `SF Pro Text`) | 400 (Regular) | `0.875rem` (`14px`) | `0.875rem` (`14px`) | `1.6` | `1.6` |

## 3. Espaçamento

O sistema de espaçamento baseia-se em uma escala de 4px, multiplicada para criar uma hierarquia visual consistente e garantir ritmo vertical e horizontal. Este sistema deve ser aplicado para `margin`, `padding` e `gap`.

| Nome (Tailwind) | Valor (px) | Valor (rem) | Uso |
| --- | --- | --- | --- |
| **`spacing-1`** | `4px` | `0.25rem` | Espaçamento mínimo entre ícones e texto, ou elementos muito próximos. |
| **`spacing-2`** | `8px` | `0.5rem` | Espaçamento padrão entre elementos relacionados próximos. |
| **`spacing-4`** | `16px` | `1rem` | Espaçamento padrão interno (padding) de botões e inputs, ou entre itens de lista. |
| **`spacing-6`** | `24px` | `1.5rem` | Espaçamento entre seções menores, margens internas de cartões ou entre grupos de elementos. |
| **`spacing-8`** | `32px` | `2rem` | Espaçamento padrão entre blocos de conteúdo ou seções de média importância. |
| **`spacing-12`** | `48px` | `3rem` | Espaçamento entre seções principais da página. |
| **`spacing-16`** | `64px` | `4rem` | Margens de página em desktop e espaçamento de grandes blocos de conteúdo. |
| **`spacing-24`** | `96px` | `6rem` | Espaçamento vertical entre seções de página (e.g., Hero para a próxima seção), para criar uma separação clara. |

## 4. Grid

O layout utiliza um sistema de grid flexível de 12 colunas, implementado com Tailwind CSS, para garantir alinhamento e responsividade em diferentes tamanhos de tela. As margens e gutters são ajustadas por breakpoint.

| Breakpoint | Colunas | Margem Lateral | Gutter (Espaçamento entre colunas) |
| --- | --- | --- | --- |
| **Desktop (****`lg`**** e acima)** | 12 | `64px` (`spacing-16`) | `24px` (`spacing-6`) |
| **Tablet (****`md`**** a ****`lg-1`****)** | 8 | `32px` (`spacing-8`) | `16px` (`spacing-4`) |
| **Mobile (****`sm`**** a ****`md-1`****)** | 4 | `16px` (`spacing-4`) | `16px` (`spacing-4`) |

## 5. Ícones

Utilizaremos a biblioteca **Lucide React** para todos os ícones. Os ícones devem manter um traço consistente (`stroke-width: 1.5` ou `2`) e seguir a paleta de cores definida no sistema de design. O componente `Icon` (conforme `COMPONENT_LIST.md`) deve ser usado para encapsular e padronizar o uso dos ícones.

## 6. Efeitos Glassmorphism

O efeito de vidro fosco é um elemento chave para a estética futurista do website. Serão definidos dois variantes principais, que devem ser aplicados através do componente `GlassPane` (conforme `COMPONENT_LIST.md`).

| Nome | Fundo (Background) | Blur (Desfoque) | Borda (Border) | Uso |
| --- | --- | --- | --- | --- |
| **Glass Light** | `rgba(255, 255, 255, 0.05)` | `12px` | `1px solid rgba(255, 255, 255, 0.1)` | Para elementos que exigem um efeito de vidro mais sutil e translúcido. |
| **Glass Dark** | `rgba(0, 0, 0, 0.4)` | `16px` | `1px solid rgba(255, 255, 255, 0.05)` | Para cartões e modais, proporcionando um efeito de profundidade mais pronunciado e escuro. |

## 7. Cartões (Cards)

Os cartões são contêineres versáteis que devem utilizar o efeito Glassmorphism (`Glass Dark`) e apresentar cantos arredondados para suavizar a estética futurista. O componente `Card` (conforme `COMPONENT_LIST.md`) deve ser a base para todos os cartões.

- **Border Radius**: `16px` (`rounded-lg` no Tailwind) ou `24px` (`rounded-xl` no Tailwind) dependendo do contexto e tamanho do cartão.

- **Padding**: `24px` (`p-6` no Tailwind) ou `32px` (`p-8` no Tailwind) para o espaçamento interno.

- **Hover State**: Um aumento sutil do brilho da borda e uma leve elevação (`transform: translateY(-4px)`) para indicar interatividade. Detalhes da animação no `ANIMATION_GUIDE.md`.

## 8. Botões

Os botões devem ser interativos, visualmente distintos e seguir os padrões de acessibilidade. Serão definidos três variantes principais, implementados através do componente `Button` (conforme `COMPONENT_LIST.md`).

| Variante | Fundo (Background) | Texto (Color) | Borda (Border) | Border Radius | Hover State |
| --- | --- | --- | --- | --- | --- |
| **Primary Button** | `Primary Accent` (`#00F0FF`) | `#000000` | Nenhuma | `9999px` (`rounded-full`) | Brilho intenso (`box-shadow` neon) e leve escala. |
| **Secondary Button** | Transparente | `#FFFFFF` | `1px solid #FFFFFF` | `9999px` (`rounded-full`) | Fundo `rgba(255, 255, 255, 0.1)` e texto `#00F0FF`. |
| **Ghost Button** | Nenhuma | `Text Secondary` (`#A0A0A0`) | Nenhuma | `0` | Texto `Text Primary` (`#FFFFFF`) e leve escala. |

## 9. Sombras (Shadows)

As sombras devem ser sutis e focadas em criar profundidade e destaque, sem poluir visualmente. Serão utilizadas sombras padrão do Tailwind e uma sombra neon customizada.

- **Shadow Sm**: `0 4px 6px -1px rgba(0, 0, 0, 0.5)` (Tailwind `shadow-sm` modificado para dark theme).

- **Shadow Md**: `0 10px 15px -3px rgba(0, 0, 0, 0.5)` (Tailwind `shadow-md` modificado).

- **Shadow Lg**: `0 20px 25px -5px rgba(0, 0, 0, 0.5)` (Tailwind `shadow-lg` modificado).

- **Neon Glow (Primary)**: `0 0 15px rgba(0, 240, 255, 0.5)` (Custom CSS/Tailwind utility para o brilho neon de elementos interativos).

## 10. Animações

As animações devem ser fluidas, utilizando curvas de easing personalizadas para uma experiência premium. Detalhes completos sobre cada animação estão no `ANIMATION_GUIDE.md`.

- **Duração Padrão**: `0.3s` (`300ms`) para interações de UI (hover, focus, clique).

- **Duração Longa**: `0.8s` a `1.2s` (`800ms` a `1200ms`) para transições de página e revelações de seção.

- **Easing Padrão**: `cubic-bezier(0.4, 0, 0.2, 1)` (equivalente a `ease-out` no CSS).

- **Easing Elástico**: `cubic-bezier(0.68, -0.55, 0.265, 1.55)` (para efeitos de "bounce" sutis e controlados).

## 11. Breakpoints Responsivos

Os breakpoints seguem o padrão do Tailwind CSS, garantindo que o design se adapte perfeitamente a uma ampla gama de dispositivos. A abordagem mobile-first deve ser utilizada.

| Breakpoint (Tailwind) | Largura Mínima | Descrição |
| --- | --- | --- |
| **`sm`** | `640px` | Dispositivos móveis em orientação paisagem (Mobile Landscape). |
| **`md`** | `768px` | Tablets em orientação retrato (Tablet Portrait). |
| **`lg`** | `1024px` | Tablets em orientação paisagem e desktops pequenos (Tablet Landscape / Small Desktop). |
| **`xl`** | `1280px` | Desktops padrão. |
| **`2xl`** | `1536px` | Desktops grandes e monitores de alta resolução. |

Este sistema de design é um documento vivo e será atualizado conforme o projeto evolui. Aderir a estas diretrizes é fundamental para o sucesso visual e funcional do Thomas Birthday Website.

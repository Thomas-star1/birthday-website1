# Lista de Componentes: Thomas Birthday Website

Este documento detalha todos os componentes que farão parte do website de aniversário do Thomas, fornecendo uma visão clara de sua funcionalidade, propriedades, estados, dependências e localização no projeto. O objetivo é garantir modularidade, reusabilidade e facilitar o desenvolvimento por uma equipe de desenvolvedores AI.

## Estrutura de Pastas de Componentes

Todos os componentes serão organizados na pasta `src/components/` e, quando apropriado, em subpastas para categorias específicas (e.g., `src/components/ui/`, `src/components/layout/`). Esta organização visa promover a separação de preocupações e a fácil localização dos arquivos.

## Definições de Tipos Essenciais

Para garantir a tipagem correta e a consistência dos dados, a interface `Gift` é definida como segue. Esta interface deve ser declarada em `src/types/gift.d.ts` ou similar.

```typescript
interface Gift {
  id: string;
  name: string;
  description: string;
  image: string; // URL da imagem do presente
  link: string; // URL para onde o presente pode ser comprado/visualizado
  category: string;
}
```

## Lista de Componentes Detalhada

### 1. Layout e Estrutura

#### `Layout`

- **Propósito**: Componente de layout principal que envolve todas as páginas da aplicação. Ele é responsável por integrar o cabeçalho, rodapé e o contêiner principal de conteúdo, além de gerenciar o estado global do modo escuro e a rolagem suave através da biblioteca Lenis.

- **Props**:
  - `children: React.ReactNode`: O conteúdo a ser renderizado dentro do layout.

- **States**:
  - `darkMode: boolean`: Um estado que indica se o modo escuro está ativo globalmente. Este estado deve ser gerenciado por um contexto ou hook global.

- **Dependencies**:
  - `Next.js`: Para a estrutura da aplicação.
  - `Tailwind CSS`: Para estilização base.
  - `Lenis`: Para proporcionar uma experiência de rolagem suave em todo o site.

- **Folder Location**: `src/components/layout/Layout.tsx`

#### `Header`

- **Propósito**: Componente da barra de navegação superior. Contém o logo ou título do site e, opcionalmente, links de navegação. Inclui um mecanismo para alternar o modo escuro.

- **Props**:
  - `onToggleDarkMode: () => void`: Função de callback para alternar o estado do modo escuro.

- **States**: Nenhum, o estado do modo escuro é gerenciado pelo componente `Layout` ou um contexto superior.

- **Dependencies**:
  - `Lucide React`: Para exibir ícones, como o de alternância de modo escuro.
  - `DarkModeToggle`: Componente filho para a funcionalidade de alternância.

- **Folder Location**: `src/components/layout/Header.tsx`

#### `Footer`

- **Propósito**: Componente do rodapé da página. Exibe informações de direitos autorais, links sociais e outras informações relevantes do site.

- **Props**: Nenhum.

- **States**: Nenhum.

- **Dependencies**:
  - `Lucide React`: Para exibir ícones sociais.

- **Folder Location**: `src/components/layout/Footer.tsx`

### 2. Seções da Página

#### `HeroSection`

- **Propósito**: A seção inicial cinematográfica do website. Inclui uma representação de uma cidade futurista, um herói urbano original e o texto de introdução do evento. Esta seção é rica em animações, conforme detalhado no `ANIMATION_GUIDE.md`.

- **Props**:
  - `title: string`: O título principal a ser exibido na seção Hero.
  - `subtitle: string`: Um subtítulo ou descrição complementar.

- **States**:
  - `animationComplete: boolean`: Um estado interno para controlar o fluxo das animações de entrada da seção.

- **Dependencies**:
  - `Framer Motion`: Para animações de elementos de UI e texto.
  - `GSAP`: Para orquestração de animações complexas e de fundo (e.g., cidade, herói).
  - `TextReveal`: Para a animação de revelação do texto.
  - `ParallaxEffect`: Para efeitos de profundidade na cidade futurista.

- **Folder Location**: `src/components/sections/HeroSection.tsx`

#### `CountdownSection`

- **Propósito**: Exibe uma contagem regressiva ao vivo para a data do aniversário. Os dígitos da contagem regressiva devem ser animados para uma transição suave, conforme especificado no `ANIMATION_GUIDE.md`.

- **Props**:
  - `targetDate: string`: A data alvo para a contagem regressiva, no formato ISO 8601 (e.g., `'2024-08-01T00:00:00-03:00'`).

- **States**:
  - `days: number`, `hours: number`, `minutes: number`, `seconds: number`: Estados internos que armazenam os valores atuais da contagem regressiva.

- **Dependencies**:
  - `React`: Para gerenciamento de estado (`useState`, `useEffect`) e lógica de temporização.
  - `Framer Motion`: Para animar a transição dos dígitos.

- **Folder Location**: `src/components/sections/CountdownSection.tsx`

#### `GiftListSection`

- **Propósito**: A seção principal para exibir a lista de presentes. Permite que os usuários filtrem os presentes por categorias, proporcionando uma experiência de navegação organizada.

- **Props**:
  - `gifts: Gift[]`: Um array de objetos `Gift` a serem exibidos na lista.

- **States**:
  - `selectedCategory: string`: O estado da categoria atualmente selecionada para filtragem.
  - `filteredGifts: Gift[]`: Um array de objetos `Gift` que reflete os presentes após a aplicação do filtro.

- **Dependencies**:
  - `GiftCard`: Para renderizar cada item individual da lista de presentes.
  - `CategoryFilter`: Para fornecer a interface de filtragem por categoria.

- **Folder Location**: `src/components/sections/GiftListSection.tsx`

### 3. Elementos de UI (UI Elements)

#### `Button`

- **Propósito**: Um componente de botão interativo e reutilizável com diferentes estilos visuais (primary, secondary, ghost). Incorpora efeitos de hover e clique, conforme detalhado no `DESIGN_SYSTEM.md` e `ANIMATION_GUIDE.md`.

- **Props**:
  - `variant: 'primary' | 'secondary' | 'ghost'`: Define o estilo visual do botão.
  - `children: React.ReactNode`: O conteúdo a ser exibido dentro do botão (texto, ícones, etc.).
  - `onClick: () => void`: Função de callback a ser executada quando o botão é clicado.
  - `className?: string`: Classes CSS adicionais para customização via Tailwind CSS.

- **States**: Nenhum, o estado de interação (hover, focus) é gerenciado via CSS ou Framer Motion.

- **Dependencies**:
  - `Tailwind CSS`: Para estilização base e variantes.
  - `Framer Motion`: Para animações de hover e clique.

- **Folder Location**: `src/components/ui/Button.tsx`

#### `Card`

- **Propósito**: Um contêiner genérico que aplica o efeito Glassmorphism, conforme especificado no `DESIGN_SYSTEM.md`. Usado para agrupar conteúdo de forma visualmente atraente e consistente.

- **Props**:
  - `children: React.ReactNode`: O conteúdo a ser renderizado dentro do cartão.
  - `className?: string`: Classes CSS adicionais para customização via Tailwind CSS.

- **States**: Nenhum.

- **Dependencies**:
  - `Tailwind CSS`: Para estilização base.
  - `GlassPane`: Para aplicar o efeito Glassmorphism.

- **Folder Location**: `src/components/ui/Card.tsx`

#### `GiftCard`

- **Propósito**: Exibe um item individual da lista de presentes. Inclui imagem, nome, descrição e um botão de ação (e.g.,"Ver Presente").

- **Props**:
  - `gift: Gift`: Um objeto do tipo `Gift` contendo todos os detalhes do presente (`id`, `name`, `description`, `image`, `link`, `category`).

- **States**: Nenhum.

- **Dependencies**:
  - `Button`: Para o botão de ação.
  - `Image` (Next.js): Para otimização e exibição da imagem do presente.
  - `Card`: Como contêiner base para o `GiftCard`.

- **Folder Location**: `src/components/gifts/GiftCard.tsx`

#### `CategoryFilter`

- **Propósito**: Componente de UI para filtrar a lista de presentes por categoria. Permite que o usuário selecione uma categoria para exibir apenas os presentes relacionados.

- **Props**:
  - `categories: string[]`: Um array de strings representando as categorias disponíveis.
  - `onSelectCategory: (category: string) => void`: Função de callback a ser chamada quando uma categoria é selecionada.
  - `selectedCategory: string`: A categoria atualmente selecionada.

- **States**: Nenhum.

- **Dependencies**:
  - `Button`: Para os botões de filtro de categoria.

- **Folder Location**: `src/components/gifts/CategoryFilter.tsx`

#### `Icon`

- **Propósito**: Um wrapper para os ícones da biblioteca Lucide React. Garante consistência no tamanho, cor e estilo dos ícones em toda a aplicação.

- **Props**:
  - `name: keyof typeof icons`: O nome do ícone a ser renderizado (deve corresponder aos nomes exportados pelo Lucide React).
  - `size?: number`: Tamanho do ícone em pixels (padrão: 24).
  - `color?: string`: Cor do ícone (padrão: `currentColor`).
  - `className?: string`: Classes CSS adicionais para customização.

- **States**: Nenhum.

- **Dependencies**:
  - `Lucide React`: A biblioteca de ícones.

- **Folder Location**: `src/components/ui/Icon.tsx`

#### `GlassPane`

- **Propósito**: Um componente utilitário que encapsula a lógica e os estilos para aplicar o efeito Glassmorphism de forma consistente em qualquer elemento filho. Utiliza as variantes `Glass Light` e `Glass Dark` definidas no `DESIGN_SYSTEM.md`.

- **Props**:
  - `children: React.ReactNode`: O conteúdo a ser renderizado dentro do painel de vidro.
  - `className?: string`: Classes CSS adicionais para customização.
  - `variant: 'light' | 'dark'`: Define qual variante do efeito Glassmorphism será aplicada.

- **States**: Nenhum.

- **Dependencies**:
  - `Tailwind CSS`: Para aplicar os estilos CSS do Glassmorphism.

- **Folder Location**: `src/components/ui/GlassPane.tsx`

### 4. Animações e Efeitos

#### `ParallaxEffect`

- **Propósito**: Aplica um efeito parallax a um elemento filho com base na rolagem da página, criando uma sensação de profundidade. Utiliza GSAP para controle preciso da animação.

- **Props**:
  - `children: React.ReactNode`: O elemento ao qual o efeito parallax será aplicado.
  - `speed: number`: A velocidade do efeito parallax (e.g., 0.5 para mover à metade da velocidade de rolagem).

- **States**: Nenhum.

- **Dependencies**:
  - `GSAP`: Para a implementação da lógica de animação parallax.

- **Folder Location**: `src/components/effects/ParallaxEffect.tsx`

#### `TextReveal`

- **Propósito**: Um componente de animação para revelar texto caractere por caractere ou palavra por palavra, criando um efeito de digitação ou surgimento. Ideal para títulos e subtítulos na seção Hero.

- **Props**:
  - `text: string`: O texto a ser animado.
  - `delay?: number`: Atraso antes do início da animação em segundos.
  - `duration?: number`: Duração da animação por caractere/palavra em segundos.

- **States**: Nenhum.

- **Dependencies**:
  - `Framer Motion`: Para orquestrar a animação de texto.

- **Folder Location**: `src/components/effects/TextReveal.tsx`

#### `CursorFollower`

- **Propósito**: Implementa um cursor personalizado que segue o ponteiro do mouse, com efeitos visuais que reagem à interação do usuário. Adiciona um toque futurista e interativo à experiência.

- **Props**: Nenhum.

- **States**:
  - `mouseX: number`, `mouseY: number`: Posições X e Y do cursor na tela.

- **Dependencies**:
  - `React`: Para capturar eventos de movimento do mouse (`mousemove`).
  - `Framer Motion`: Para animar o movimento e os efeitos visuais do cursor.

- **Folder Location**: `src/components/effects/CursorFollower.tsx`

### 5. Utilitários

#### `DarkModeToggle`

- **Propósito**: Um botão de UI para alternar entre o modo claro e escuro da aplicação. Deve ser visualmente intuitivo e animado.

- **Props**:
  - `onToggle: () => void`: Função de callback para ser executada quando o botão é clicado.
  - `isDarkMode: boolean`: Indica o estado atual do modo escuro para renderizar o ícone correto.

- **States**: Nenhum.

- **Dependencies**:
  - `Icon`: Para exibir os ícones de sol/lua.
  - `Button`: Como base para o estilo do botão.

- **Folder Location**: `src/components/ui/DarkModeToggle.tsx`

Esta lista serve como um guia abrangente para a equipe de desenvolvimento. Novas necessidades de componentes devem ser discutidas e adicionadas a este documento.

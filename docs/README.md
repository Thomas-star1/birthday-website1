# Thomas Birthday Website

## Visão Geral do Projeto

Bem-vindo ao repositório do **Thomas Birthday Website**! Este projeto visa criar uma experiência digital ultra-premium e futurista para celebrar o aniversário do Thomas. Inspirado em eventos de lançamento de produtos de alta tecnologia (Apple Event, Samsung Galaxy Unpacked, Tesla) e websites vencedores do Awwwards, o objetivo é entregar uma plataforma visualmente deslumbrante, interativa e imersiva.

O site contará com uma seção hero cinematográfica, uma contagem regressiva ao vivo para 1º de agosto, uma lista de presentes interativa com categorias, e uma série de animações premium, efeitos de glassmorphism e um design responsivo com modo escuro. Para uma visão detalhada dos requisitos e princípios de design, consulte `docs/PROJECT_RULES.md` e `docs/DESIGN_SYSTEM.md`.

## Tecnologias Principais (Tech Stack)

Este projeto é construído com as seguintes tecnologias de ponta, selecionadas para garantir performance, escalabilidade e uma experiência de desenvolvimento moderna:

- **Next.js 15**: Framework React para renderização do lado do servidor (SSR) e geração de sites estáticos (SSG), otimizado para performance e SEO.

- **React**: Biblioteca JavaScript líder para construção de interfaces de usuário dinâmicas e reativas.

- **TypeScript**: Superset do JavaScript que adiciona tipagem estática, melhorando a robustez, a manutenibilidade do código e a experiência do desenvolvedor.

- **Tailwind CSS**: Framework CSS utilitário altamente configurável, permitindo um desenvolvimento rápido de interfaces responsivas e modernas.

- **Framer Motion**: Biblioteca de animação para React, utilizada para criar transições e animações de UI fluidas e expressivas.

- **GSAP (GreenSock Animation Platform)**: Uma das bibliotecas de animação mais robustas e performáticas, ideal para animações complexas e cinematográficas.

- **Lenis**: Biblioteca para rolagem suave (smooth scrolling), proporcionando uma experiência de navegação mais agradável e fluida.

- **Lucide React**: Uma coleção de ícones modernos e consistentes, fácil de integrar e estilizar, garantindo a uniformidade visual.

## Instalação

Para configurar e executar o projeto localmente, siga os passos abaixo:

1. **Clone o repositório**:

   ```bash
   git clone https://github.com/thomas-birthday/website.git
   cd website
   ```

1. **Instale as dependências**:Utilize `npm` ou `yarn` para instalar as dependências do projeto. Recomenda-se o uso de `npm`.

   ```bash
   npm install
   # ou
   yarn install
   ```

1. **Configure as variáveis de ambiente**:Crie um arquivo `.env.local` na raiz do projeto, copiando o `.env.local.example`. Adicione as variáveis de ambiente necessárias. Por exemplo, a data do aniversário para a contagem regressiva:

   ```
   NEXT_PUBLIC_ANIVERSARY_DATE="2024-08-01T00:00:00-03:00" # Formato ISO 8601
   ```

1. **Inicie o servidor de desenvolvimento**:

   ```bash
   npm run dev
   # ou
   yarn dev
   ```

   O site estará disponível em `http://localhost:3000`.

## Estrutura de Pastas

A estrutura de pastas do projeto segue as convenções do Next.js e as diretrizes de modularidade e organização. Para detalhes completos sobre a finalidade de cada diretório e as convenções de nomenclatura, consulte `docs/DEVELOPMENT_RULES.md` e `docs/COMPONENT_LIST.md`.

```
. 
├── public/                    # Ativos estáticos (imagens, fontes, etc. )
├── src/                       # Código-fonte da aplicação
│   ├── app/                   # Páginas e layouts do Next.js (App Router)
│   ├── components/            # Componentes React reutilizáveis, subdivididos por categoria
│   │   ├── ui/                # Componentes de UI genéricos (Button, Card, Icon)
│   │   ├── layout/            # Componentes de layout (Header, Footer, Layout)
│   │   ├── sections/          # Componentes de seção de página (HeroSection, CountdownSection)
│   │   ├── gifts/             # Componentes específicos da lista de presentes (GiftCard, CategoryFilter)
│   │   └── effects/           # Componentes para efeitos visuais (ParallaxEffect, CursorFollower)
│   ├── hooks/                 # Custom React Hooks para lógica reutilizável
│   ├── styles/                # Arquivos CSS globais ou específicos do Tailwind
│   ├── utils/                 # Funções utilitárias e helpers
│   └── types/                 # Definições de tipos TypeScript globais
├── docs/                      # Documentação completa do projeto
├── .env.local.example         # Exemplo de variáveis de ambiente
├── next.config.mjs            # Configuração do Next.js
├── package.json               # Dependências e scripts do projeto
├── postcss.config.js          # Configuração do PostCSS
├── tailwind.config.ts         # Configuração do Tailwind CSS
├── tsconfig.json              # Configuração do TypeScript
└── README.md                  # Este arquivo
```

## Scripts

Os seguintes scripts estão disponíveis no `package.json` para auxiliar no desenvolvimento e manutenção do projeto:

- `dev`: Inicia o servidor de desenvolvimento do Next.js com hot-reloading.

- `build`: Cria uma build otimizada do projeto para produção.

- `start`: Inicia o servidor de produção após a execução do `build`.

- `lint`: Executa o ESLint para verificar problemas de código e garantir a qualidade.

- `format`: Formata o código automaticamente usando Prettier, seguindo as regras definidas.

## Build

Para criar uma versão otimizada do projeto para implantação em produção, execute o seguinte comando:

```bash
npm run build
# ou
yarn build
```

Este comando gerará os arquivos estáticos e o código otimizado na pasta `.next/`, prontos para serem servidos.

## Deploy

O projeto, sendo uma aplicação Next.js, pode ser facilmente implantado em plataformas como Vercel, Netlify, ou qualquer provedor de hospedagem que suporte aplicações Node.js e Next.js. Consulte a documentação da plataforma escolhida para instruções específicas de deploy. Recomenda-se a utilização de Vercel para uma integração contínua e deploy simplificado.

## Regras de Contribuição

Para contribuir com este projeto, é fundamental seguir as diretrizes e padrões estabelecidos para garantir a consistência e a qualidade do código. Por favor, leia atentamente o documento `docs/DEVELOPMENT_RULES.md` para obter todas as informações detalhadas sobre:

- Convenções de nomenclatura e estrutura de pastas.

- Estilo de código (TypeScript, ESLint, Prettier).

- Princípios de componentes reutilizáveis.

- Diretrizes de performance e acessibilidade.

- Estratégias para evitar duplicação de código.

- Requisitos para código "Production Ready" (testes, tratamento de erros, segurança).

Em resumo, todas as contribuições devem ser feitas em um novo branch, e um Pull Request deve ser aberto para revisão. O código deve ser limpo, legível, bem documentado e aderente a todas as regras de desenvolvimento.

---

**Desenvolvido com 💙 por Manus AI**

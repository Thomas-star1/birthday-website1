# Regras de Desenvolvimento: Thomas Birthday Website

Este documento estabelece as regras e diretrizes que todos os desenvolvedores AI devem seguir ao contribuir para o projeto "Thomas Birthday Website". O objetivo primordial é garantir a consistência do código, a manutenibilidade, a performance e a qualidade geral do produto final, que deve ser ultra-premium e futurista. A adesão rigorosa a estas regras é fundamental para o sucesso do projeto.

## 1. Convenções de Nomenclatura

A consistência na nomenclatura é vital para a legibilidade e manutenibilidade do código. As seguintes convenções devem ser estritamente seguidas:

- **Componentes React**: Utilizar `PascalCase` para nomes de arquivos e componentes (ex: `HeroSection.tsx`, `GiftCard.tsx`). Isso facilita a identificação de componentes no sistema de arquivos e no código.

- **Variáveis e Funções**: Adotar `camelCase` para variáveis, funções e métodos (ex: `userName`, `handleButtonClick`, `fetchData`).

- **Constantes Globais**: Utilizar `SCREAMING_SNAKE_CASE` para constantes que representam valores imutáveis e globais (ex: `API_BASE_URL`, `MAX_ITEMS_PER_PAGE`).

- **Classes CSS (Tailwind)**: Seguir as convenções utilitárias do Tailwind CSS. Para classes customizadas que complementam o Tailwind, utilizar `kebab-case` (ex: `custom-glass-effect`).

- **Pastas**: Utilizar `kebab-case` para nomes de diretórios (ex: `components`, `utils`, `hooks`). A estrutura de pastas detalhada pode ser encontrada em `README.md` e `COMPONENT_LIST.md`.

## 2. Convenções de Pastas

A organização do projeto segue uma estrutura lógica para facilitar a navegação e a localização de arquivos. A estrutura raiz do projeto é a seguinte:

- `public/`: Destinado a ativos estáticos como imagens, fontes e arquivos de manifesto.

- `src/`: Contém todo o código-fonte da aplicação.
  - `app/`: Estrutura de roteamento e páginas do Next.js.
    - `components/`: Abriga todos os componentes React reutilizáveis, subdivididos para melhor organização:
      - `ui/`: Componentes de interface de usuário genéricos (e.g., `Button`, `Card`, `Icon`).
      - `layout/`: Componentes que definem a estrutura do layout da página (e.g., `Header`, `Footer`, `Layout`).
      - `sections/`: Componentes que representam seções maiores da página (e.g., `HeroSection`, `CountdownSection`).
      - `gifts/`: Componentes específicos relacionados à funcionalidade da lista de presentes (e.g., `GiftCard`, `CategoryFilter`).
      - `effects/`: Componentes que encapsulam efeitos visuais e animações (e.g., `ParallaxEffect`, `CursorFollower`).
  - `hooks/`: Contém custom React Hooks para lógica reutilizável.
  - `styles/`: Arquivos CSS globais ou configurações específicas do Tailwind.
  - `utils/`: Funções utilitárias e helpers de propósito geral.
  - `types/`: Definições de tipos TypeScript globais ou compartilhadas.

Componentes pequenos e altamente acoplados a uma página ou seção específica podem ser co-localizados na pasta da página/seção para maior clareza, mas a preferência geral é por centralizar componentes reutilizáveis em `src/components/`.

## 3. Estilo de Código

O estilo de código é fundamental para a colaboração e manutenibilidade. As seguintes diretrizes devem ser observadas:

- **TypeScript First**: Todo o código deve ser escrito em TypeScript. A tipagem explícita é obrigatória sempre que possível para garantir a segurança e clareza do código.

- **ESLint e Prettier**: As configurações padrão do projeto para ESLint e Prettier devem ser seguidas rigorosamente. O código deve ser formatado automaticamente antes de cada commit para garantir a consistência.

- **Funções Puras e Componentes Funcionais**: Priorizar a criação de funções puras e componentes funcionais sempre que a lógica permitir, promovendo a previsibilidade e a facilidade de teste.

- **React Hooks**: Utilizar React Hooks para gerenciamento de estado, lógica de efeitos e reutilização de lógica com estado. Evitar o uso de classes para componentes.

- **Comentários e Documentação**: Escrever comentários claros e concisos para explicar lógicas complexas, decisões de design não óbvias ou qualquer parte do código que possa gerar dúvidas. Utilizar JSDoc para documentar props de componentes, funções e interfaces, facilitando a compreensão e o uso por outros desenvolvedores.

- **Importações**: Organizar as importações de forma consistente, agrupando-as por tipo (bibliotecas externas, componentes do projeto, arquivos locais) e ordenando-as alfabeticamente.

## 4. Componentes Reutilizáveis

A reusabilidade é um pilar deste projeto para evitar duplicação de código e promover a consistência. Os desenvolvedores devem:

- **Princípio DRY (Don't Repeat Yourself)**: Sempre buscar oportunidades para criar componentes, hooks ou funções utilitárias reutilizáveis em vez de duplicar código.

- **Separação de Preocupações**: Garantir que cada componente tenha uma única responsabilidade bem definida. A lógica de negócios deve ser claramente separada da lógica de apresentação.

- **Props e Children**: Utilizar `props` para passar dados e configurações para os componentes e `children` para compor componentes de forma flexível.

- **Storybook (Opcional)**: Embora não seja um requisito obrigatório, a utilização de Storybook para documentar e testar componentes isoladamente é altamente encorajada, se o escopo do projeto permitir e a equipe decidir por sua implementação.

## 5. Performance

A performance é um requisito não negociável para um website ultra-premium. As seguintes práticas devem ser adotadas:

- **Otimização de Imagens**: Utilizar o componente `next/image` para otimização automática de imagens. Formatos modernos como WebP e AVIF devem ser preferidos, e as imagens devem ser dimensionadas adequadamente para evitar carregamento desnecessário.

- **Lazy Loading**: Implementar lazy loading para componentes e imagens que estão fora da viewport inicial, carregando-os apenas quando se tornam visíveis ou estão prestes a se tornar.

- **Minimizar Re-renderizações**: Utilizar `React.memo`, `useCallback` e `useMemo` quando apropriado para evitar re-renderizações desnecessárias de componentes e otimizar o desempenho.

- **Animações Otimizadas**: Priorizar animações baseadas em `transform` e `opacity` para aproveitar a aceleração de hardware. Para animações complexas, utilizar `requestAnimationFrame` e seguir as `Recomendações de Performance` detalhadas no `ANIMATION_GUIDE.md`.

- **Remoção de Código Morto**: Garantir que o bundle final de produção não contenha código não utilizado ou bibliotecas desnecessárias.

## 6. Acessibilidade (A11y)

A acessibilidade é um aspecto crucial para garantir que o website seja utilizável por todos. Os desenvolvedores devem:

- **Semântica HTML**: Utilizar tags HTML semânticas apropriadas (e.g., `header`, `nav`, `main`, `footer`, `button`, `a`) para estruturar o conteúdo.

- **Atributos ARIA**: Aplicar atributos ARIA quando a semântica HTML nativa não for suficiente para descrever a funcionalidade ou o estado de elementos interativos da UI.

- **Contraste de Cores**: Garantir que o contraste de cores para texto e elementos interativos atenda aos padrões WCAG 2.1 (nível AA), especialmente no modo escuro, conforme especificado no `DESIGN_SYSTEM.md`.

- **Navegação por Teclado**: Todos os elementos interativos devem ser navegáveis e operáveis exclusivamente via teclado.

- **Foco Visível**: Fornecer um indicador de foco claro e visível para elementos interativos quando navegados via teclado.

- **Textos Alternativos**: Todas as imagens (`<img>`) devem ter atributos `alt` descritivos para usuários de leitores de tela.

## 7. Sem Código Duplicado

A duplicação de código deve ser ativamente evitada para manter a base de código limpa e eficiente:

- **Refatoração Constante**: Revisar o código regularmente para identificar e remover duplicações. A refatoração deve ser uma prática contínua.

- **Funções Utilitárias**: Criar funções utilitárias e helpers para encapsular lógicas repetitivas que não se encaixam em componentes ou hooks.

- **Componentes Abstratos**: Desenvolver componentes mais abstratos que possam ser configurados via props para diferentes usos, em vez de criar componentes ligeiramente diferentes para cada variação.

## 8. Apenas Produção Pronta (Production Ready Only)

Todo o código entregue deve estar pronto para ser implantado em produção, o que implica:

- **Testes**: Escrever testes unitários e de integração para garantir a robustez e a correção do código. A cobertura de testes deve ser um objetivo contínuo.

- **Tratamento de Erros**: Implementar tratamento de erros robusto em toda a aplicação para evitar falhas inesperadas e fornecer feedback adequado ao usuário.

- **Validação**: Validar todas as entradas de usuário e dados recebidos de APIs para prevenir comportamentos inesperados e vulnerabilidades.

- **Segurança**: Estar ciente de vulnerabilidades comuns (e.g., XSS, CSRF) e implementar medidas de proteção adequadas. Assegurar que nenhuma informação sensível seja exposta no cliente.

- **Documentação**: Manter a documentação atualizada e precisa, refletindo o estado atual do código e as funcionalidades implementadas. A documentação é parte integrante do entregável "Production Ready".

Seguir estas regras garantirá um projeto de alta qualidade, fácil de manter e escalar, e que atenda às expectativas de um website ultra-premium e futurista. A colaboração e a adesão a estas diretrizes são essenciais para o sucesso coletivo.

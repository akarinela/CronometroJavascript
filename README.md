# Cronômetro Simples

- **Disciplina:** Desenvolvimento Web II
- **Projeto Escolhido:** Cronômetro Simples
- **Integrantes:** [Ana Karine de Freitas Oliveiera](https://github.com/akarinela) e [Humberto Wagner de Sousa](https://github.com/1bertoW)

---

## 1. Descrição do Projeto

Este trabalho é um mini-projeto da disciplina de Desenvolvimento Web II, que consiste na criação de uma pequena aplicação web interativa utilizando HTML, CSS e JavaScript.

O objetivo do nosso projeto foi implementar um **cronômetro funcional**, que permitisse ao usuário iniciar, pausar e resetar a contagem de tempo.

---

## 2. Projeto Proposto

A proposta original, conforme o documento de orientação, era:

> "Implemente um cronômetro que começa ao clicar em "Iniciar", pode ser pausado e resetado. O tempo deve ser exibido em segundos na tela, atualizando a cada segundo."

O projeto deveria seguir uma estrutura de arquivos específica e ser publicado no GitHub Pages.

---

## 3. Como Foi Feito (Estruturas, Lógica e Implementação)

Para desenvolver o cronômetro, seguimos a estrutura de pastas solicitada e utilizamos as três tecnologias web fundamentais: HTML para a estrutura, CSS para a estilização e JavaScript para toda a lógica e interatividade.

### 3.1. Estrutura de Arquivos

A organização do projeto seguiu o modelo definido nas orientações:

```
meu-projeto/
|
├── index.html
├── css/
│   └── estilo.css
├── js/
│   └── script.js
└── README.md
```

### 3.2. Estrutura HTML (`index.html`)

O corpo da página (`<body>`) foi estruturado de forma simples e semântica. Criamos:

-   Um contêiner principal (`div`) para centralizar os elementos na tela.
-   Um elemento `<h1>` para o título "Cronômetro".
-   Um elemento `p` ou `div` com um `id` específico (ex: `id="timer"`) para exibir o tempo. Este é o elemento que o JavaScript atualizará a cada segundo.
-   Três botões (`<button>`) com seus respectivos `ids` (ex: `id="startBtn"`, `id="pauseBtn"`, `id="resetBtn"`), um para cada ação: Iniciar, Pausar e Resetar.

### 3.3. Estilização CSS (`estilo.css`)

A folha de estilos foi utilizada para tornar a interface mais agradável e funcional. As principais decisões de estilo foram:

-   **Centralização:** Utilizamos Flexbox no `body` para alinhar o contêiner do cronômetro vertical e horizontalmente no centro da página.
-   **Display do Tempo:** A fonte para o contador de tempo foi aumentada e estilizada para dar destaque ao número.
-   **Botões:** Os botões foram estilizados para terem uma aparência uniforme, com cores distintas e um efeito `hover` para melhorar a experiência do usuário, indicando que são clicáveis.

### 3.4. Lógica JavaScript (`script.js`)

Esta é a parte central do projeto. A lógica foi implementada da seguinte forma:

1.  **Mapeamento dos Elementos do DOM:** Primeiro, criamos variáveis no JavaScript para "capturar" os elementos HTML com os quais precisamos interagir (o display do tempo e os três botões), utilizando `document.getElementById()`.

2.  **Variáveis de Controle:** Definimos três variáveis principais para controlar o estado do cronômetro:
    -   `segundos`: Uma variável numérica que armazena a contagem atual do tempo. Iniciada em `0`.
    -   `intervalo`: Uma variável para armazenar o ID retornado pela função `setInterval()`. Isso é crucial para podermos pausar e resetar o cronômetro.
    -   `rodando`: Uma variável booleana (`true`/`false`) para verificar se o cronômetro já está em execução. Isso evita que o usuário clique em "Iniciar" várias vezes e acelere o cronômetro.

3.  **Funções Principais:**
    -   **`iniciar()`:**
        -   Verifica se o cronômetro não está `rodando`.
        -   Se não estiver, ela inicia a função `setInterval()`. O `setInterval` foi configurado para executar uma função a cada 1000 milissegundos (1 segundo).
        -   A função executada pelo `setInterval` incrementa a variável `segundos` e atualiza o texto do display na tela.
        -   Por fim, define a variável `rodando` como `true`.
    -   **`pausar()`:**
        -   Esta função utiliza `clearInterval(intervalo)` para parar a execução repetida que foi iniciada pelo `setInterval`.
        -   Define a variável `rodando` como `false`.
    -   **`resetar()`:**
        -   Primeiro, ela chama `clearInterval(intervalo)` para garantir que o cronômetro pare.
        -   Em seguida, redefine a variável `segundos` para `0`.
        -   Atualiza o display na tela para mostrar `0`.
        -   Define `rodando` como `false`.

4.  **Event Listeners:**
    -   Para cada botão, adicionamos um "ouvinte de evento" (`addEventListener`) que espera por um clique.
    -   Ao clicar no botão "Iniciar", a função `iniciar()` é chamada.
    -   Ao clicar no botão "Pausar", a função `pausar()` é chamada.
    -   Ao clicar no botão "Resetar", a função `resetar()` é chamada.

---

## 4. Projeto Publicado

O resultado final do projeto pode ser visualizado através do link do GitHub Pages abaixo:

[Cronômetro Simples](https://akarinela.github.io/CronometroSimples/)

---

## 5. Prévia do Projeto
<img width="540" height="620" alt="image" src="https://github.com/user-attachments/assets/2621c3dc-b8c4-452a-92d2-5f211ce07855" />

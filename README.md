# Programação visual 1 Unidade

## 1. O que é HTML?

**HTML** (HyperText Markup Language) é a linguagem usada para estruturar o conteúdo de páginas web. Ele organiza textos, imagens, links, vídeos e outros elementos, permitindo que navegadores exibam páginas de forma compreensível para os usuários.

- **Não é programação**, mas sim marcação.
- Cada elemento é representado por uma **tag** (palavra-chave entre `<` e `>`).
- Geralmente possui uma tag de abertura e uma tag de fechamento e seu conteúdo vai entre a tag de abertura e de fechamento. Ex:.
```html
<p>Esse é um parágrafo.</p>
```
- `<p>` → Tag de abertura
- Esse é um parágrafo. → Conteúdo
- `</p>` → Tag de fechamento

### Exemplo de HTML simples

```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8">
    <title>Exemplo de HTML</title>
  </head>
  <body>
    <h1>Bem-vindo ao HTML!</h1>
    <p>HTML é a linguagem de marcação da web.</p>
  </body>
</html>
```


---

## 2. Estrutura básica de um documento HTML

```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8">
    <title>Minha Página</title>
    <meta name="description" content="Exemplo de estrutura HTML">
  </head>
  <body>
    <!-- Conteúdo visível -->
  </body>
</html>
```


### Explicação dos elementos

- `<!DOCTYPE html>`: Declara que o documento está em HTML5.
- `<html lang="pt-br">`: Elemento raiz, define o idioma da página.
- `<head>`: Metadados (informações sobre a página, não visíveis).
- `<meta charset="UTF-8">`: Define a codificação dos caracteres.
- `<title>`: Título da aba do navegador.
- `<body>`: Onde fica o conteúdo visível.

---

## 3. Primeiras tags: título, parágrafo, imagem

### Título

```html
<h1>Este é um título principal</h1>
<h2>Subtítulo</h2>
```

- `<h1>` a `<h6>`: Títulos de diferentes níveis, do mais importante ao menos importante.


### Parágrafo

```html
<p>Este é um parágrafo de texto. Parágrafos são usados para blocos de texto.</p>
```


### Imagem

```html
<img src="https://www.exemplo.com/imagem.jpg" alt="Descrição da imagem" width="300" height="200">
```

- `src`: Caminho da imagem.
- `alt`: Texto alternativo (acessibilidade).
- `width` e `height`: Dimensões da imagem.


### Exemplo visual

```
---------------------------
|        <h1>             |
|  Meu Site Incrível      |
|-------------------------|
| <img src="foto.jpg">    |
|-------------------------|
| <p>Bem-vindo!</p>       |
---------------------------
```


---

## 4. Comentário em HTML

Comentários são ignorados pelo navegador e servem para anotações no código.

```html
<!-- Este é um comentário -->
<p>Texto visível</p>
<!-- <p>Este texto não aparece</p> -->
```


---

## 5. O que é CSS?

**CSS** (Cascading Style Sheets) é a linguagem usada para definir o estilo dos elementos HTML. Com CSS, você pode alterar cores, fontes, tamanhos, posicionamentos, criar animações e muito mais.

- **Separa o conteúdo (HTML) da apresentação (CSS)**
- **Cascading**: Estilos podem ser sobrepostos e herdados.

---

## 6. Estilos: inline, incorporados, externos

### Inline

Estilo aplicado diretamente na tag HTML.

```html
<p style="color: blue; font-size: 20px;">Texto azul e grande</p>
```

Vantagens:

- Aplicação rápida para alterações pequenas.
- Útil para testes rápidos ou estilos únicos.

Desvantagens:

- Mistura HTML e CSS (dificulta a organização).
- Repetitivo se precisar aplicar o mesmo estilo em vários lugares.
- Difícil de manter em projetos grandes.


### Incorporado (Interno)

CSS dentro da tag `<style>` no `<head>`.

```html
<head>
  <style>
    body { background: #f0f0f0; }
    p { color: green; }
  </style>
</head>
```

Vantagens:

- Melhor que o inline para organizar o CSS.
- Evita repetição: um seletor controla vários elementos.

Desvantagens:

- Mistura estrutura (HTML) com estilo (CSS) ainda.
- Se o site crescer, fica difícil de encontrar e editar estilos.
- Prejudica o reaproveitamento: outro HTML não pode usar esse CSS facilmente.


### Externo

CSS em arquivo separado (ex: `estilo.css`).

```html
<link rel="stylesheet" href="estilo.css">
```

**estilo.css:**

```css
h1 { color: purple; }
p { font-family: Arial, sans-serif; }
```

Vantagens:

- Organização máxima: separa conteúdo (HTML) e estilo (CSS).
- Facilidade de manutenção: muda o CSS num só lugar, afeta o site todo.
- Reaproveitável: pode usar o mesmo CSS em várias páginas.
- Melhor desempenho: o navegador cachê (guarda o CSS) e carrega mais rápido.

Desvantagens:

- Depende de um arquivo externo: se o CSS não carregar, o site pode ficar sem estilo.
- Para páginas muito pequenas, pode ser exagerado criar um arquivo separado.

---

## 7. Seletores: elemento, classe, id

### Elemento

Aplica o estilo a todas as tags do mesmo tipo.

```css
p { color: orange; }
```


### Classe

Aplica o estilo a qualquer elemento com a classe especificada.

```css
.destaque { background: yellow; }
```

```html
<p class="destaque">Texto destacado</p>
```


### ID

Aplica o estilo a um elemento único com o atributo `id`.

```css
#principal { border: 2px solid red; }
```

```html
<div id="principal">Conteúdo principal</div>
```


---

## 8. Agrupamento de seletores

Permite aplicar o mesmo estilo a vários seletores.

```css
h1, h2, h3 {
  font-family: Verdana, sans-serif;
  color: #333;
}
```


---

## 9. Seletores descendentes

Seleciona elementos que estão dentro de outros.

```css
article p {
  color: teal;
}
```

Aplica a todos os `<p>` dentro de `<article>`.

---

## 10. Seletores de filhos diretos

Seleciona apenas filhos diretos.

```css
ul > li {
  list-style-type: square;
}
```

Só `<li>` diretamente dentro de `<ul>`.

---

## 11. Cores

### Formas de definir cores:

- **Nomes**: `red`, `blue`, `green`.

    Você escreve diretamente o nome em inglês da cor.

  
- **Hexadecimal**: `#ff5733`

    Um código que representa a mistura de vermelho (R), verde (G) e azul (B).
    Cada cor vai de 00 a FF (0 a 255 em hexadecimal).
- **RGB**: `rgb(255, 87, 51)`



```css
body { background: #e0e0e0; }
h1 { color: rgb(40, 150, 255); }
p { color: red; }
```


---

## 12. Formatação de textos

```css
p {
  font-family: 'Arial', sans-serif;
  font-size: 18px;
  font-style: italic;
  font-weight: bold;
  text-align: justify;
  text-decoration: underline;
  text-transform: uppercase;
  letter-spacing: 2px;
  line-height: 1.5;
}
```


---

## 13. Inspecionamento com Chrome DevTools

### Como usar:

- Clique com o botão direito em qualquer elemento da página e escolha **"Inspecionar"**.
- Ou pressione `F12` no Chrome.
- Você pode ver o HTML, CSS aplicado, modificar valores em tempo real, depurar JavaScript e analisar o desempenho.

**Exemplo visual do DevTools:**

```
------------------------------
| <div class="caixa">        |
|   <p>Texto</p>             |
| </div>                     |
------------------------------
[DevTools]
  Elements | Styles | Console
  <div class="caixa">
    <p>Texto</p>
  </div>
  .caixa {
    border: 1px solid #000;
    padding: 10px;
  }
```


---

## 14. Propriedade display

Controla como o elemento se comporta no layout.

- **block**: Ocupa toda a linha. Ex: `<div>`, `<p>`
- **inline**: Só ocupa o espaço do conteúdo. Ex: `<span>`, `<a>`
- **inline-block**: Mistura, fica em linha mas aceita tamanho.
- **none**: Elemento não aparece.

```css
span { display: block; }
div { display: inline; }
```


---

## 15. Border (Borda)

Define bordas ao redor dos elementos.

```css
.box {
  border: 3px dashed #f00; /* 3px, tracejada, vermelha */
  border-radius: 8px;       /* Bordas arredondadas */
}
```


---

## 16. Espaçamento interno (Padding)

Espaço **dentro** da borda, entre o conteúdo e a borda.

```css
.box {
  padding: 20px;           /* Todos os lados */
  padding-top: 10px;       /* Apenas em cima */
  padding: 10px 20px 5px 0; /* Topo, Direita, Baixo, Esquerda */
}
```


---

## 17. Margens

Espaço **fora** da borda, separando elementos.

```css
.box {
  margin: 15px;            /* Todos os lados */
  margin-bottom: 30px;     /* Apenas embaixo */
  margin: 10px 5px;        /* Vertical, Horizontal */
}
```


---

## 18. Box Model e box-sizing

### Box Model

```
+---------------------------+
|        margin             |
|  +---------------------+  |
|  |      border         |  |
|  |  +---------------+  |  |
|  |  |   padding     |  |  |
|  |  | +----------+  |  |  |
|  |  | | content  |  |  |  |
|  |  | +----------+  |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```

- **content**: Conteúdo (texto, imagem)
- **padding**: Espaço interno
- **border**: Borda
- **margin**: Espaço externo


### box-sizing

- **content-box** (padrão): largura/altura só do conteúdo.
- **border-box**: largura/altura inclui padding e borda.

```css
.box {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: border-box;
}
```

Com `border-box`, a caixa terá exatamente 200px de largura, **incluindo** padding e borda.

---

## 19. O que é o GitHub?

**GitHub** é uma plataforma de hospedagem de código-fonte que usa o sistema de controle de versão **Git**. Ele permite:

- **Versionar** projetos (salvar histórico de alterações)
- **Colaborar** com outros desenvolvedores
- **Compartilhar** código com o mundo
- **Documentar** projetos (README, Wiki)
- **Hospedar sites estáticos** gratuitamente (GitHub Pages)


### Fluxo básico de uso

1. Crie um repositório no GitHub.
2. Clone o repositório para seu computador.
3. Faça alterações no código.
4. Use comandos Git para versionar:
    - `git add .`
    - `git commit -m "Mensagem"`
    - `git push`
5. As alterações aparecem no GitHub.

### Exemplo visual

```
[Seu Computador] ----(git push)---> [GitHub]
       ^                                 |
       |----(git pull)-------------------|
```


---

## Recursos visuais e extras

- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)
- [W3Schools CSS Tutorial](https://www.w3schools.com/css/)
- [MDN Web Docs: HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [MDN Web Docs: CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [Guia GitHub para iniciantes (em português)](https://rogerdudler.github.io/git-guide/index.pt_BR.html)

---

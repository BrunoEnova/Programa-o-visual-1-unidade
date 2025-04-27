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

Seletor é a parte do código CSS que escolhe (ou "seleciona") quais elementos do HTML vão receber o estilo que você está definindo.

Exemplo básico:

````css
Copiar
Editar
p {
  color: blue;
}
````
Aqui, o seletor é p.
Isso quer dizer: ➔ "Pegue todos os parágrafos <p> da página e pinte o texto de azul."

Tipos de seletores mais comuns:

|Tipo	| Exemplo|	O que faz|
|-----|--------|-----------|
|Por tag	|p, h1, div	|Estiliza todos os elementos dessa tag
|Por classe|	.minha-classe|	Estiliza elementos que têm o atributo class="minha-classe"
|Por ID|	#meu-id|	Estiliza o elemento que tem o atributo id="meu-id"


### Tag

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
  color: green;
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

    Especifica a cor usando três valores entre 0 e 255, para vermelho, verde e azul, rgb(vermelho, verde, azul).

   Como ler rgb(40, 150, 255):

   - Pouco vermelho (40).

   - Médio verde (150).

   - Azul forte (255).
  


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
| Propriedade         | O que faz                                             | Exemplos                              |
|:--------------------|:-----------------------------------------------------|:--------------------------------------|
| `font-family`        | Define qual fonte será usada no texto.               | `'Arial', sans-serif`                 |
| `font-size`          | Define o tamanho da fonte.                           | `18px`, `2em`, `100%`                 |
| `font-style`         | Define o estilo da fonte.                            | `normal`, `italic`, `oblique`         |
| `font-weight`        | Define a grossura da fonte.                          | `normal`, `bold`, `100`, `700`        |
| `text-align`         | Define o alinhamento horizontal do texto.            | `left`, `center`, `right`, `justify`  |
| `text-decoration`    | Adiciona decorações no texto.                        | `none`, `underline`, `line-through`   |
| `text-transform`     | Transforma as letras do texto.                       | `none`, `uppercase`, `lowercase`      |
| `letter-spacing`     | Controla o espaçamento entre as letras.              | `2px`, `0.1em`                        |
| `line-height`        | Controla a altura da linha (espaço entre as linhas). | `normal`, `1.5`, `1.2em`              |


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

## 18. **Box Model e box-sizing**

O **Box Model** é um conceito fundamental do CSS que define como cada elemento HTML é representado visualmente na página: como uma caixa retangular composta por diferentes áreas. Entender o Box Model é essencial para controlar o tamanho, o espaçamento e o posicionamento dos elementos em um layout web.

### **Componentes do Box Model**

Cada caixa (box) é composta por quatro áreas, de dentro para fora:

1. **Conteúdo (content)**
    - É onde fica o conteúdo real do elemento, como texto ou imagem.
    - O tamanho é definido pelas propriedades `width` e `height`.
    - Exemplo:

```css
.caixa {
  width: 200px;
  height: 100px;
}
```

2. **Preenchimento (padding)**
    - Espaço entre o conteúdo e a borda.
    - Pode ser definido individualmente para cada lado (`padding-top`, `padding-right`, etc.) ou para todos de uma vez (`padding`).
    - O fundo do elemento (background) se estende até o final do padding.
    - Exemplo:

```css
.caixa {
  padding: 20px;
}
```

3. **Borda (border)**
    - Linha que envolve o conteúdo e o padding.
    - Pode ter cor, largura e estilo diferentes para cada lado.
    - Exemplo:

```css
.caixa {
  border: 2px solid #333;
}
```

4. **Margem (margin)**
    - Espaço externo que separa o elemento dos outros ao redor.
    - Também pode ser definido individualmente ou em conjunto.
    - Exemplo:

```css
.caixa {
  margin: 10px;
}
```

**Como o tamanho final do elemento é calculado?**

Por padrão, **width** e **height** definem apenas o tamanho do conteúdo. O tamanho total do elemento é a soma do conteúdo, padding, borda e margem:

```
Largura total = width + padding esquerdo + padding direito + border esquerdo + border direito + margin esquerdo + margin direito
Altura total  = height + padding topo + padding base + border topo + border base + margin topo + margin base
```

**Exemplo prático:**

```css
.caixa {
  width: 100px;
  padding: 10px;
  border: 5px solid;
  margin: 20px;
}
```

- Largura total: 100 (conteúdo) + 10*2 (padding) + 5*2 (border) + 20*2 (margin) = 170px


## **A Propriedade `box-sizing`**

A propriedade `box-sizing` define como o navegador calcula o tamanho de um elemento:

- **`box-sizing: content-box` (padrão):**
    - `width` e `height` se aplicam apenas ao conteúdo.
    - Padding e border são somados ao tamanho final.
    - Exemplo:

```css
.caixa {
  width: 200px;
  padding: 20px;
  border: 5px solid;
  box-sizing: content-box;
}
```

    Largura total: 200 + 20*2 + 5*2 = 250px
- **`box-sizing: border-box`:**
    - `width` e `height` incluem conteúdo, padding e border.
    - O tamanho total do elemento é exatamente o valor definido.
    - Exemplo:

```css
.caixa {
  width: 200px;
  padding: 20px;
  border: 5px solid;
  box-sizing: border-box;
}
```

      Largura total: 200px (já inclui padding e border)

---

## 19. O que é o GitHub?

**GitHub** é uma plataforma de hospedagem de código-fonte que usa o sistema de controle de versão **Git**. Ele permite:

- **Versionar** projetos (salvar histórico de alterações)
- **Colaborar** com outros desenvolvedores
- **Compartilhar** código com o mundo
- **Documentar** projetos (README, Wiki)
- **Hospedar sites estáticos** gratuitamente (GitHub Pages)


## Recursos visuais e extras

- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)
- [W3Schools CSS Tutorial](https://www.w3schools.com/css/)
- [MDN Web Docs: HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [MDN Web Docs: CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [Guia GitHub para iniciantes (em português)](https://rogerdudler.github.io/git-guide/index.pt_BR.html)

---

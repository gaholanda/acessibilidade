# Imagens

A acessibilidade das imagens na web é crucial para garantir que todos os usuários, incluindo aqueles com deficiências visuais, possam acessar o conteúdo visual. Aqui estão as melhores práticas, juntamente com exemplos de código HTML, CSS e JavaScript

## Uso do atributo `alt`

O texto alternativo deve ser breve, mas descritivo o suficiente para transmitir o conteúdo e a função da imagem.

```html
<img src="imagem.jpg" alt="Descrição da imagem">
```

## Imagens Decorativas

Para imagens que não transmitem informação essencial (apenas decorativas), use um `alt` vazio.

```html
<img src="decorativa.jpg" alt="">
```

## Uso de `aria-labelledby` e `aria-describedby`

Para imagens complexas ou gráficos, você pode usar ARIA para associar a imagem a um rótulo ou descrição detalhada.

```html
<img src="grafico.png" aria-labelledby="titulo-grafico" aria-describedby="descricao-grafico">
    <h2 id="titulo-grafico">Gráfico de Vendas Anuais</h2>
    <p id="descricao-grafico">
        Este gráfico mostra as vendas anuais de 2020 a 2023, com um aumento constante ano após ano.
    </p>
```

## Imagens de Fundo em CSS

Não use imagens de fundo para conteúdo essencial, pois elas não são acessíveis para leitores de tela. Se precisar usar, forneça uma alternativa textual.


```css
.hero {
    background-image: url('imagem-de-fundo.jpg');
    background-size: cover;
    background-position: center;
    position: relative;
    width: 100%;
    height: 400px;
}

.hero::before {
    content: "Texto alternativo para imagem de fundo";
    position: absolute;
    top: -9999px;
    left: -9999px;
}
```

## Uso de figcaption para Imagens dentro de <figure>

Utilize `<figure>` e `<figcaption>` para agrupar a imagem e sua descrição.

```html
<figure>
    <img src="paisagem.jpg" alt="Paisagem montanhosa durante o pôr do sol">
    <figcaption>Paisagem montanhosa durante o pôr do sol</figcaption>
</figure>
```

## Imagens Responsivas

Para garantir que a imagem correta seja carregada em diferentes dispositivos, use `srcset` e `sizes`.

```html
<img src="imagem-pequena.jpg" srcset="imagem-grande.jpg 1024w, imagem-media.jpg 640w, imagem-pequena.jpg 320w" sizes="(max-width: 600px) 480px, (max-width: 1200px) 800px, 1000px" alt="Descrição da imagem responsiva">
```

## Alternativa Textual com `noscript`

Caso use imagens carregadas dinamicamente com JavaScript, forneça uma alternativa textual com `<noscript>`.

```html
<script>
    document.write('<img src="imagem-dinamica.jpg" alt="Descrição da imagem carregada dinamicamente">');
</script>
<noscript>
    <img src="imagem-dinamica.jpg" alt="Descrição da imagem carregada dinamicamente">
</noscript>
```

##  Legenda de Imagens em Sliders/Carrosséis

Em carrosséis de imagens, certifique-se de que as legendas estejam associadas e sejam visíveis.

```html
<div class="carousel">
    <div class="slide" aria-labelledby="slide1-caption">
        <img src="slide1.jpg" alt="Descrição da primeira imagem">
        <p id="slide1-caption">Legenda da primeira imagem</p>
    </div>
    <div class="slide" aria-labelledby="slide2-caption">
        <img src="slide2.jpg" alt="Descrição da segunda imagem">
        <p id="slide2-caption">Legenda da segunda imagem</p>
    </div>
</div>
```

## Scripts de Imagens Carregadas Dinamicamente

Ao carregar imagens dinamicamente, inclua descrições no objeto de imagem.

```ts
const imagens = [
    { src: 'imagem1.jpg', alt: 'Descrição da primeira imagem' },
    { src: 'imagem2.jpg', alt: 'Descrição da segunda imagem' }
];

const container = document.getElementById('image-container');

imagens.forEach(imagem => {
    const img = document.createElement('img');
    img.src = imagem.src;
    img.alt = imagem.alt;
    container.appendChild(img);
});
```

## Ferramentas de Teste de Acessibilidade

Use ferramentas como Axe, WAVE, e Lighthouse para validar a acessibilidade das imagens.
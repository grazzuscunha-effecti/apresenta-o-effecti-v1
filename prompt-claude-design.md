# Prompt Padrão — Claude Design · Effecti

Use este prompt como instrução base ao iniciar qualquer apresentação no Claude Design. Cole o conteúdo abaixo como contexto inicial antes de descrever o conteúdo da apresentação.

---

## Instrução para o Claude Design

Você está criando uma apresentação para a Effecti. Siga rigorosamente o sistema visual e estrutural definido abaixo, independentemente do conteúdo. O design não improvisa — ele governa.

---

## Dimensões e base

- Formato fixo: **1920 × 1080px** por slide
- Background da página: `#EDEEF0`
- Fonte: **Inter** (Google Fonts) — pesos 400, 500, 600, 700, 800, 900
- Cada slide é um arquivo HTML independente com `overflow: hidden`

---

## Estrutura de cada slide

### Topbar
- Altura: `80px` · Background: `#FFFFFF` · Border-radius: `0 0 12px 12px`
- Padding interno: `0 40px` · Padding lateral externo (wrapper): `0 64px`
- **Esquerda:** logo Effecti (`assets/marca-effecti.svg`, altura 32px)
- **Centro:** título do programa — `font-size: 14px`, `color: #BFC0C8`, `border: 1px solid #BFC0C8`, `border-radius: 8px`, `padding: 8px 28px`, uppercase
- **Direita:** URL — `font-size: 14px`, `color: #081128`

> Na capa e contra-capa o centro da topbar é omitido.

### Área de conteúdo
- Padding: `48px 64px 64px`
- Flex column · Gap: `40px` · Overflow: hidden

---

## Sistema de cores

| Token | Background | Texto | Uso |
|---|---|---|---|
| warm | `#DCD4BA` | `#242007` | Badge/tag 01 |
| blue | `#A7EAFB` | `#002738` | Badge/tag 02 |
| green | `#C2E0B1` | `#092800` | Badge/tag 03 |
| orange | `#FFCBAE` | `#441500` | Badge/tag 04 |
| yellow | `#F6E4AF` | `#3F3607` | Badge/tag 05 |
| — | `#EDEEF0` | — | Background da página |
| — | `#FFFFFF` | — | Topbar |
| — | `#D9DADC` | — | Container de imagem placeholder |
| — | — | `#081128` | Texto principal |

---

## Tipografia

| Elemento | Tamanho | Peso | Detalhe |
|---|---|---|---|
| Headline principal | `56px` | 700 | uppercase · letter-spacing `-0.03em` · line-height `1.05` |
| Título de coluna | `18px` | 700 | letter-spacing `-0.01em` |
| Corpo de texto | `16px` | 400 | line-height `1.75` · letter-spacing `-0.01em` |
| Badge de seção | `12px` | 700 | uppercase · padding `14px 20px` · border-radius `100px` |
| Tag inline | `12px` | 700 | letter-spacing `0.06em` · padding `2px 8px` · border-radius `3px` |

---

## Componentes

### Badges de seção
Sempre cinco badges no topo do conteúdo, antes do headline. Identificam o capítulo ou tema da apresentação. Usam as cinco cores do sistema em sequência.

```html
<div style="display: flex; gap: 8px; align-items: center;">
  <div class="section-tag">01 | TEXTO 01</div>
  <div class="section-tag" style="background: #A7EAFB; color: #002738;">02 | TEXTO 02</div>
  <div class="section-tag" style="background: #C2E0B1; color: #092800;">03 | TEXTO 03</div>
  <div class="section-tag" style="background: #FFCBAE; color: #441500;">04 | TEXTO 04</div>
  <div class="section-tag" style="background: #F6E4AF; color: #3F3607;">05 | TEXTO 05</div>
</div>
```

### Tags filosóficas (inline)
Pílulas dentro dos parágrafos para destacar conceitos-chave da marca. Utilizam as mesmas cores das badges.

```html
<span class="token token-warm">Clareza acima de tudo</span>
<span class="token token-blue">Crescer com liberdade</span>
<span class="token token-green">O nome nunca muda</span>
<span class="token token-orange">Calor humano como antídoto</span>
<span class="token token-yellow">Autonomia Inteligente</span>
```

```css
.token { display: inline-block; font-size: 12px; font-weight: 700; letter-spacing: 0.06em; padding: 2px 8px; border-radius: 3px; margin: 0 2px; vertical-align: middle; }
.token-warm   { background: #DCD4BA; color: #242007; }
.token-blue   { background: #A7EAFB; color: #002738; }
.token-green  { background: #C2E0B1; color: #092800; }
.token-orange { background: #FFCBAE; color: #441500; }
.token-yellow { background: #F6E4AF; color: #3F3607; }
```

### Container de imagem
Placeholder para imagens. Sempre `border-radius: 12px`, background `#D9DADC`, label centralizado.

```html
<div class="col-image">
  <span class="col-image-label">Imagem</span>
</div>
```

---

## Layouts disponíveis

| Slide | Estrutura | Quando usar |
|---|---|---|
| **Capa** | Hero card azul (`#A7EAFB`) com ilustração overflow à esquerda e título à direita | Abertura |
| **Slide 01** | Duas colunas de texto em proporção igual, gap `80px` | Conteúdo denso em dois blocos |
| **Slide 02** | Texto à esquerda + container de imagem à direita | Conteúdo com visual de apoio |
| **Slide 03** | Duas colunas de texto acima + imagem em largura total abaixo | Conteúdo com imagem de contexto |
| **Slide 04** | Duas colunas, cada uma com texto + imagem própria empilhados | Comparação visual entre dois temas |
| **Slide 05** | Headline + container de imagem em largura total | Destaque visual, dado único |
| **Contra-capa** | Hero card com ilustração overflow e mensagem de encerramento | Encerramento |

---

## Comportamento responsivo

Todos os slides (exceto capa e contra-capa) incluem este script para se ajustar ao viewport:

```javascript
(function () {
  var slide = document.querySelector('.slide');
  function fit() {
    var s = Math.min(window.innerWidth / 1920, window.innerHeight / 1080);
    slide.style.transform = 'scale(' + s + ')';
    slide.style.transformOrigin = '0 0';
    slide.style.position = 'absolute';
    slide.style.left = Math.max(0, (window.innerWidth - 1920 * s) / 2) + 'px';
    slide.style.top = Math.max(0, (window.innerHeight - 1080 * s) / 2) + 'px';
  }
  fit();
  window.addEventListener('resize', fit);
})();
```

---

## Tom e filosofia dos textos

Os textos da Effecti têm um tom filosófico e assertivo. Evite linguagem técnica fria.

- Frases curtas com peso semântico
- Conceitos recorrentes: governança, identidade, decisão, semântica, autonomia
- Oposições que criam tensão positiva — *"não se improvisa, se governa"*
- Headlines em uppercase que funcionam como manifestos
- Tags inline para destacar princípios e conceitos dentro dos parágrafos

---

*Effecti — Programa de Governança de Design System · effecti.com.br*

# Apresentação Effecti — Template V1

Template base de apresentação da Effecti em HTML. Desenvolvido para ser utilizado no **Claude Design** como estrutura de referência para a montagem de apresentações com padrões visuais consistentes da marca.

**Preview:** [grazzuscunha-effecti.github.io/apresenta-o-effecti-v1](https://grazzuscunha-effecti.github.io/apresenta-o-effecti-v1/)

---

## Prompt para o Claude Design

Para criar novas apresentações mantendo o mesmo design e estrutura, use o prompt padrão disponível em:

**[`prompt-claude-design.md`](prompt-claude-design.md)**

Cole o conteúdo desse arquivo como instrução inicial no Claude Design antes de descrever o conteúdo da sua apresentação. O prompt descreve o sistema visual completo — dimensões, tipografia, cores, componentes e layouts — garantindo consistência em qualquer apresentação gerada.

---

## O que é

Um conjunto de slides HTML em formato fixo **1920×1080px** que serve como fundação para apresentações da Effecti. Cada slide é um arquivo independente, pronto para ser aberto no browser ou importado como base no Claude Design.

O template não é uma apresentação finalizada — é uma estrutura. Os textos, imagens e conteúdo são placeholders que devem ser substituídos conforme o contexto de cada apresentação.

---

## Estrutura do projeto

```
apresentação-effecti-v1/
├── assets/
│   ├── marca-effecti.svg
│   ├── ilustra-somos-tecnológicos-effecti.svg
│   └── ilustra-01-freemium-effecti.svg
├── capa-apresentação-effecti.html
├── contra-capa-apresentação-effecti.html
├── slide-01-apresentação-effecti.html
├── slide-02-apresentação-effecti.html
├── slide-03-apresentação-effecti.html
├── slide-04-apresentação-effecti.html
└── slide-05-apresentação-effecti.html
```

---

## Slides disponíveis

| Arquivo | Layout |
|---|---|
| `capa` | Hero card azul com ilustração e título principal |
| `slide-01` | Dois blocos de texto em colunas iguais |
| `slide-02` | Bloco de texto à esquerda + container de imagem à direita |
| `slide-03` | Dois blocos de texto acima + imagem em largura total abaixo |
| `slide-04` | Dois blocos de texto, cada um com imagem própria abaixo |
| `slide-05` | Título + imagem em largura total (sem colunas de texto) |
| `contra-capa` | Hero card com ilustração e mensagem de encerramento |

---

## Padrões do template

### Topbar
Presente em todos os slides. Contém logo Effecti à esquerda, título do programa ao centro e URL à direita. Altura fixa de 80px com bordas arredondadas inferiores.

### Grid e espaçamento
- Padding lateral da página: `64px`
- Padding superior do conteúdo: `48px`
- Padding inferior do conteúdo: `64px`
- Gap entre colunas: `80px`

### Badges de seção
Cinco badges coloridas no topo do conteúdo, usadas para identificar o capítulo ou tema da apresentação. Cores definidas pelo sistema de tokens da Effecti.

### Tags filosóficas
Pílulas inline dentro dos textos que destacam conceitos-chave da marca. Utilizam as mesmas cores das badges de seção.

### Tipografia
Família **Inter**. Títulos em 56px bold uppercase, subtítulos em 18px bold, corpo em 16px com line-height 1.75.

### Cores base
| Uso | Cor |
|---|---|
| Background da página | `#EDEEF0` |
| Texto principal | `#081128` |
| Topbar | `#FFFFFF` |
| Container de imagem | `#D9DADC` |

---

## Como usar

1. Clone o repositório
2. Abra qualquer arquivo `.html` diretamente no browser
3. Use os slides como referência estrutural no Claude Design
4. Substitua textos, imagens e badges pelo conteúdo da apresentação desejada

---

*Effecti — Programa de Governança de Design System*  
*effecti.com.br*

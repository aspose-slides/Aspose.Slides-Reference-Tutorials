---
"date": "2025-04-23"
"description": "Aprenda a personalizar as cores dos hiperlinks em apresentações do PowerPoint usando o Aspose.Slides para Python. Aprimore seus slides com estilos de links personalizados de forma eficiente."
"title": "Como definir cores de hiperlinks no PowerPoint usando Aspose.Slides para Python"
"url": "/pt/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como definir cores de hiperlinks no PowerPoint usando Aspose.Slides para Python

## Introdução

Melhorar o apelo visual das suas apresentações do PowerPoint personalizando as cores dos hiperlinks é simples com o Aspose.Slides para Python. Este guia mostrará como definir hiperlinks com cores específicas nos seus slides usando Python.

**O que você aprenderá:**
- Como definir uma cor de hiperlink em formas de texto no PowerPoint.
- Etapas envolvidas na criação de uma apresentação visualmente atraente.
- Principais recursos do Aspose.Slides para Python que facilitam essa personalização.

Vamos analisar os pré-requisitos necessários antes de começar.

## Pré-requisitos

Antes de começar, certifique-se de que seu ambiente esteja pronto com o seguinte:
- **Bibliotecas e Versões:** Instalar `aspose.slides` biblioteca. Certifique-se de que o Python esteja instalado na sua máquina.
- **Requisitos de configuração do ambiente:** Este tutorial pressupõe uma configuração básica do Python no Windows, Mac ou Linux.
- **Pré-requisitos de conhecimento:** A familiaridade com a programação Python será benéfica.

## Configurando Aspose.Slides para Python

Para começar a usar o Aspose.Slides para Python, instale o pacote via pip:

```bash
pip install aspose.slides
```

**Etapas de aquisição de licença:**
- **Teste gratuito:** Baixe uma versão de teste em [Página de lançamento da Aspose](https://releases.aspose.com/slides/python-net/).
- **Licença temporária:** Solicitar uma licença temporária no [página de compra](https://purchase.aspose.com/temporary-license/) para acesso estendido.
- **Comprar:** Para desbloquear totalmente os recursos sem limitações, considere comprar uma licença da [Página de compras da Aspose](https://purchase.aspose.com/buy).

**Inicialização básica:**
Depois de instalado e licenciado, importe o Aspose.Slides no seu script:

```python
import aspose.slides as slides
```

## Guia de Implementação

Esta seção orienta você na configuração de cores de hiperlinks em uma apresentação do PowerPoint.

### Definir recurso de cor do hiperlink

#### Visão geral

Personalize a cor dos hiperlinks incorporados em formas de texto usando o Aspose.Slides para Python. Isso melhora a legibilidade e o apelo visual.

##### Etapa 1: Crie uma nova apresentação

Crie uma instância de uma apresentação:

```python
with slides.Presentation() as presentation:
    # Seu código aqui
```

##### Etapa 2: adicione uma forma com texto

Adicione um retângulo ao primeiro slide e insira um texto que inclua um hiperlink.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Etapa 3: definir propriedades do hiperlink

Atribua o hiperlink e defina sua cor. O `hyperlink_click` propriedade especifica para onde o link deve navegar ao clicar.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Defina a origem da cor do hiperlink para o formato da parte e defina o tipo de preenchimento e a cor.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Etapa 4: Salve a apresentação

Salve sua apresentação em um diretório especificado:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
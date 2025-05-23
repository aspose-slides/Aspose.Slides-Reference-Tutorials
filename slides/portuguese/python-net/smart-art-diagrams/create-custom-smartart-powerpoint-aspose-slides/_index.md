---
"date": "2025-04-23"
"description": "Aprenda a criar e personalizar gráficos SmartArt no PowerPoint usando o Aspose.Slides para Python, aprimorando suas apresentações com organogramas dinâmicos."
"title": "Como criar e personalizar SmartArt no PowerPoint usando Aspose.Slides para Python"
"url": "/pt/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar e personalizar SmartArt no PowerPoint usando Aspose.Slides para Python

## Introdução

Apresentações são uma ferramenta essencial para representar visualmente estruturas organizacionais ou sessões de brainstorming. Com o Aspose.Slides para Python, você pode criar e personalizar gráficos SmartArt sem esforço. Este tutorial guiará você na adição de um organograma SmartArt aos seus slides do PowerPoint.

**O que você aprenderá:**
- Adicionando um gráfico SmartArt no PowerPoint usando Aspose.Slides para Python.
- Personalizando o layout do seu nó SmartArt.
- Salvando e exportando apresentações com eficiência.

Vamos começar a configurar seu ambiente!

## Pré-requisitos

Antes de começar a criar gráficos SmartArt, certifique-se de ter os seguintes pré-requisitos:

### Bibliotecas necessárias
- **Aspose.Slides para Python**: Instale esta biblioteca usando pip se ainda não o fez.

### Requisitos de configuração do ambiente
- Uma instalação funcional do Python (3.x recomendado).
- Noções básicas de programação em Python.
- A familiaridade com o Microsoft PowerPoint é útil, mas não necessária.

## Configurando Aspose.Slides para Python

Para começar, configure a biblioteca Aspose.Slides no seu ambiente Python:

**Instalação de Pip:**
```bash
pip install aspose.slides
```

### Etapas de aquisição de licença
A Aspose oferece várias opções de licenciamento:
- **Teste grátis**: Baixe uma licença temporária para avaliar todos os recursos.
- **Licença Temporária**: Obtenha uma licença temporária gratuita para uso de curto prazo.
- **Comprar**: Considere adquirir uma assinatura para projetos de longo prazo.

### Inicialização e configuração básicas

Após a instalação, inicialize seu script Python com Aspose.Slides assim:

```python
import aspose.slides as slides

# Inicialize a classe Presentation com slides.Presentation() como apresentação:
    # Seu código para adicionar SmartArt ficará aqui
```

## Guia de Implementação

Agora vamos detalhar o processo de adição e personalização do SmartArt no PowerPoint usando o Aspose.Slides para Python.

### Adicionar um gráfico SmartArt

#### Visão geral
Crie um novo slide e adicione um gráfico SmartArt do tipo organograma a ele:

```python
import aspose.slides as slides

# Crie uma instância de apresentação com slides.Presentation() como apresentação:
    # Adicionar SmartArt com dimensões especificadas na posição (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parâmetros e Objetivo do Método
- **x, y**: Posição do gráfico SmartArt no slide.
- **largura, altura**: Dimensões para visibilidade adequada.
- **tipo_de_layout**: Especifica o tipo de layout SmartArt, neste caso, um organograma.

### Personalizando o layout do organograma

#### Visão geral
Personalize o primeiro nó em nosso gráfico SmartArt definindo seu layout como LEFT_HANGING:

```python
# Defina o primeiro nó para o layout pendurado à esquerda
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Explicação das principais opções de configuração
- **Tipo de Layout de Organograma**Determina como os nós são exibidos, melhorando a legibilidade e o apelo estético.

### Salvando a apresentação

Por fim, salve sua apresentação em um diretório especificado:

```python
# Salve a apresentação com SmartArt\presentation.save("SEU_DIRETÓRIO_DE_SAÍDA/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
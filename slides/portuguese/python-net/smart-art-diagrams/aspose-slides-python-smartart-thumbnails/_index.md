---
"date": "2025-04-23"
"description": "Aprenda a automatizar a criação de gráficos SmartArt em apresentações do PowerPoint usando o Aspose.Slides para Python, incluindo como extrair e salvar miniaturas com eficiência."
"title": "Como criar e recuperar miniaturas SmartArt usando Aspose.Slides para Python"
"url": "/pt/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar e recuperar miniaturas SmartArt usando Aspose.Slides para Python

## Introdução

Criar apresentações visualmente atraentes é essencial para capturar a atenção do seu público. Uma maneira eficaz de aprimorar apresentações de slides é incorporar gráficos dinâmicos como SmartArt em apresentações do PowerPoint. Se você busca um método automatizado para gerar esses visuais e extrair miniaturas deles, este guia sobre "Aspose.Slides Python" será inestimável.

Usando o Aspose.Slides para Python, você pode criar gráficos SmartArt sem esforço, acessar nós específicos dentro do gráfico, recuperar miniaturas de imagem desses nós e salvá-las para seus projetos. Este tutorial o guiará por cada etapa detalhadamente.

**O que você aprenderá:**
- Como instalar e configurar o Aspose.Slides para Python.
- Criando um gráfico SmartArt em uma apresentação do PowerPoint.
- Acessando nós dentro de um gráfico SmartArt.
- Extrair e salvar uma miniatura de imagem de um nó específico.

Vamos nos aprofundar nos pré-requisitos antes de começar.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte pronto:

- **Bibliotecas necessárias:** Você precisará do Aspose.Slides para Python. Certifique-se de que seu ambiente seja compatível com Python 3.x.
- **Requisitos de configuração do ambiente:** Uma instalação funcional do Python e um IDE ou editor de texto adequado, como VSCode ou PyCharm.
- **Pré-requisitos de conhecimento:** Conhecimento básico de programação Python, incluindo definições de funções e operações de arquivo.

## Configurando Aspose.Slides para Python

Primeiro, você precisa instalar a biblioteca Aspose.Slides. Isso pode ser feito facilmente usando o pip:

```bash
pip install aspose.slides
```

Após a instalação, obtenha uma licença se desejar explorar todos os recursos sem limitações. Você pode começar com um teste gratuito, solicitar uma licença temporária ou comprá-la para uso de longo prazo.

Para inicializar o Aspose.Slides no seu ambiente Python, importe a biblioteca no início do seu script:

```python
import aspose.slides as slides
```

## Guia de Implementação

Vamos dividir o processo em etapas claras para criar e recuperar uma miniatura SmartArt.

### Etapa 1: Criar uma nova instância de apresentação

Comece criando uma instância de apresentação. Este será o contêiner onde você adicionará seu gráfico SmartArt.

```python
with slides.Presentation() as pres:
```

Usando `with` garante que os recursos sejam gerenciados adequadamente, salvando e fechando o arquivo automaticamente ao sair.

### Etapa 2: adicione SmartArt ao primeiro slide

Em seguida, adicionaremos um elemento gráfico SmartArt ao nosso primeiro slide. Veja como fazer isso:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Isso adiciona um layout de ciclo básico para o gráfico SmartArt na posição (10, 10) com dimensões de 400x300 pixels.

### Etapa 3: Acesse o segundo nó

Acesse nós específicos dentro do seu SmartArt. Neste exemplo, acessamos o segundo nó:

```python
node = smart.nodes[1]
```

Os nós são indexados a partir do zero; portanto, `nodes[1]` refere-se ao segundo nó na lista.

### Etapa 4: recuperar a miniatura da imagem

Para obter uma miniatura da imagem da forma dentro do nó selecionado:

```python
image = node.shapes[0].get_image()
```

Isso recupera a imagem da primeira forma como uma miniatura do nó SmartArt especificado.

### Etapa 5: Salve a imagem recuperada

Por fim, salve esta miniatura no local desejado no formato JPEG:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
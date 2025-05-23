---
"description": "Aprenda a ajustar a altura das fontes em apresentações do PowerPoint usando Java com o Aspose.Slides. Aprimore a formatação de texto dos seus slides sem esforço."
"linktitle": "Definir valores de altura de fonte local no PowerPoint usando Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir valores de altura de fonte local no PowerPoint usando Java"
"url": "/pt/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir valores de altura de fonte local no PowerPoint usando Java

## Introdução
Neste tutorial, você aprenderá a manipular a altura das fontes em vários níveis em apresentações do PowerPoint usando o Aspose.Slides para Java. Controlar o tamanho das fontes é crucial para criar apresentações visualmente atraentes e estruturadas. Apresentaremos exemplos passo a passo para ilustrar como definir a altura das fontes para diferentes elementos de texto.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
- Java Development Kit (JDK) instalado no seu sistema
- Biblioteca Aspose.Slides para Java. Você pode baixá-la [aqui](https://releases.aspose.com/slides/java/).
- Uma compreensão básica de programação Java e apresentações em PowerPoint
## Pacotes de importação
Certifique-se de incluir os pacotes Aspose.Slides necessários no seu arquivo Java:
```java
import com.aspose.slides.*;
```
## Etapa 1: inicializar um objeto de apresentação
Primeiro, crie um novo objeto de apresentação do PowerPoint:
```java
Presentation pres = new Presentation();
```
## Etapa 2: adicione uma forma e uma moldura de texto
Adicione uma forma automática com uma moldura de texto ao primeiro slide:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Etapa 3: Crie partes de texto
Defina partes do texto com diferentes alturas de fonte:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Etapa 4: definir alturas de fonte
Defina alturas de fonte em diferentes níveis:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Etapa 5: Salve a apresentação
Salve a apresentação modificada em um arquivo:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusão
Este tutorial demonstrou como ajustar a altura das fontes em slides do PowerPoint programaticamente usando o Aspose.Slides para Java. Ao manipular os tamanhos de fonte em diferentes níveis (em toda a apresentação, parágrafo e parte), você pode obter controle preciso sobre a formatação do texto em suas apresentações.
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides para Java é uma API poderosa para manipular apresentações do PowerPoint programaticamente.
### Onde posso encontrar documentação do Aspose.Slides para Java?
Você pode encontrar a documentação [aqui](https://reference.aspose.com/slides/java/).
### Posso testar o Aspose.Slides para Java antes de comprar?
Sim, você pode obter um teste gratuito [aqui](https://releases.aspose.com/).
### Como posso obter suporte para o Aspose.Slides para Java?
Para obter suporte, visite o [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Onde posso comprar uma licença para o Aspose.Slides para Java?
Você pode comprar uma licença [aqui](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
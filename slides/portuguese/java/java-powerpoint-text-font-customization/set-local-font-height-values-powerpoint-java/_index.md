---
title: Defina valores locais de altura da fonte no PowerPoint usando Java
linktitle: Defina valores locais de altura da fonte no PowerPoint usando Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como ajustar a altura das fontes em apresentações do PowerPoint usando Java com Aspose.Slides. Melhore a formatação de texto em seus slides sem esforço.
weight: 17
url: /pt/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
Neste tutorial, você aprenderá como manipular alturas de fontes em vários níveis em apresentações do PowerPoint usando Aspose.Slides para Java. Controlar o tamanho das fontes é crucial para criar apresentações estruturadas e visualmente atraentes. Examinaremos exemplos passo a passo para ilustrar como definir alturas de fonte para diferentes elementos de texto.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
- Kit de desenvolvimento Java (JDK) instalado em seu sistema
-  Aspose.Slides para biblioteca Java. Você pode baixá-lo[aqui](https://releases.aspose.com/slides/java/).
- Uma compreensão básica de programação Java e apresentações em PowerPoint
## Importar pacotes
Certifique-se de incluir os pacotes Aspose.Slides necessários em seu arquivo Java:
```java
import com.aspose.slides.*;
```
## Etapa 1: inicializar um objeto de apresentação
Primeiro, crie um novo objeto de apresentação do PowerPoint:
```java
Presentation pres = new Presentation();
```
## Etapa 2: adicionar uma forma e um quadro de texto
Adicione uma forma automática com uma moldura de texto ao primeiro slide:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Etapa 3: crie porções de texto
Defina porções de texto com diferentes alturas de fonte:
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
## Etapa 5: salve a apresentação
Salve a apresentação modificada em um arquivo:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusão
Este tutorial demonstrou como ajustar a altura das fontes em slides do PowerPoint de forma programática usando Aspose.Slides para Java. Ao manipular os tamanhos das fontes em diferentes níveis (toda a apresentação, parágrafo e parte), você pode obter controle preciso sobre a formatação do texto em suas apresentações.
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma API poderosa para manipular apresentações do PowerPoint de forma programática.
### Onde posso encontrar documentação para Aspose.Slides for Java?
 Você pode encontrar a documentação[aqui](https://reference.aspose.com/slides/java/).
### Posso experimentar o Aspose.Slides para Java antes de comprar?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).
### Como posso obter suporte para Aspose.Slides para Java?
 Para suporte, visite o[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Onde posso comprar uma licença do Aspose.Slides for Java?
 Você pode comprar uma licença[aqui](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

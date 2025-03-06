---
title: Adicionar texto sobrescrito e subscrito em Java PowerPoint
linktitle: Adicionar texto sobrescrito e subscrito em Java PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como adicionar texto sobrescrito e subscrito em apresentações Java PowerPoint usando Aspose.Slides para Java. Perfeito para aprimorar seus slides.
weight: 13
url: /pt/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
A criação de apresentações em PowerPoint envolventes e informativas geralmente requer o uso de recursos de formatação, como texto sobrescrito e subscrito. Este tutorial irá guiá-lo através do processo de incorporação de texto sobrescrito e subscrito em suas apresentações Java PowerPoint usando Aspose.Slides for Java.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
- Java Development Kit (JDK) instalado em seu sistema.
-  Aspose.Slides para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).
- Um ambiente de desenvolvimento integrado (IDE), como IntelliJ IDEA ou Eclipse configurado para desenvolvimento Java.
- Familiaridade básica com programação Java e apresentações em PowerPoint.

## Importar pacotes
Primeiro, importe os pacotes necessários do Aspose.Slides for Java:
```java
import com.aspose.slides.*;
```
## Etapa 1: configurar a apresentação
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Etapa 2: acesse o slide
```java
// Obtenha o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
```
## Etapa 3: crie uma caixa de texto
```java
// Crie uma AutoForma para servir como caixa de texto
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Etapa 4: adicionar texto sobrescrito
```java
// Crie um parágrafo para o texto principal
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Crie uma parte para o texto sobrescrito
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Definir escape para sobrescrito
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Adicione o parágrafo principal com sobrescrito à caixa de texto
textFrame.getParagraphs().add(mainParagraph);
```
## Etapa 5: adicionar texto subscrito
```java
// Crie outro parágrafo para texto subscrito
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Crie uma parte para o texto subscrito
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Definir escape para subscrito
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Adicione o parágrafo subscrito à caixa de texto
textFrame.getParagraphs().add(subscriptParagraph);
```
## Etapa 6: salve a apresentação
```java
// Salve a apresentação
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusão
Neste tutorial, exploramos como aprimorar suas apresentações Java PowerPoint com texto sobrescrito e subscrito usando Aspose.Slides para Java. Seguindo essas etapas, você pode criar slides visualmente mais atraentes e informativos que comunicam seu conteúdo de maneira eficaz.

## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma biblioteca robusta que permite aos desenvolvedores criar, manipular e converter apresentações do PowerPoint programaticamente.
### Onde posso encontrar mais documentação sobre Aspose.Slides for Java?
 Documentação detalhada pode ser encontrada[aqui](https://reference.aspose.com/slides/java/).
### Como posso obter uma licença temporária do Aspose.Slides for Java?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Posso experimentar o Aspose.Slides para Java gratuitamente?
 Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
### Onde posso obter suporte para Aspose.Slides for Java?
 Para suporte e discussões, visite o[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

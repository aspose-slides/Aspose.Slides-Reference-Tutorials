---
"description": "Aprenda a adicionar texto sobrescrito e subscrito em apresentações do PowerPoint em Java usando o Aspose.Slides para Java. Perfeito para aprimorar seus slides."
"linktitle": "Adicionar texto sobrescrito e subscrito no PowerPoint Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar texto sobrescrito e subscrito no PowerPoint Java"
"url": "/pt/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar texto sobrescrito e subscrito no PowerPoint Java

## Introdução
Criar apresentações envolventes e informativas em PowerPoint geralmente requer o uso de recursos de formatação, como texto sobrescrito e subscrito. Este tutorial guiará você pelo processo de incorporação de texto sobrescrito e subscrito em suas apresentações em PowerPoint Java usando o Aspose.Slides para Java.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
- Java Development Kit (JDK) instalado no seu sistema.
- Biblioteca Aspose.Slides para Java. Você pode baixá-la em [aqui](https://releases.aspose.com/slides/java/).
- Um Ambiente de Desenvolvimento Integrado (IDE), como IntelliJ IDEA ou Eclipse, configurado para desenvolvimento Java.
- Familiaridade básica com programação Java e apresentações em PowerPoint.

## Pacotes de importação
Primeiro, importe os pacotes necessários do Aspose.Slides para Java:
```java
import com.aspose.slides.*;
```
## Etapa 1: Configurar a apresentação
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Etapa 2: Acesse o Slide
```java
// Obtenha o primeiro slide
ISlide slide = presentation.getSlides().get_Item(0);
```
## Etapa 3: Crie uma caixa de texto
```java
// Crie uma AutoForma para servir como uma caixa de texto
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Etapa 4: Adicionar texto sobrescrito
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
// Adicione o parágrafo principal com sobrescrito à caixa de texto
textFrame.getParagraphs().add(mainParagraph);
```
## Etapa 5: Adicionar texto subscrito
```java
// Crie outro parágrafo para o texto subscrito
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Crie uma parte para o texto do subscrito
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Definir escape para subscrito
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Adicione o parágrafo subscrito à caixa de texto
textFrame.getParagraphs().add(subscriptParagraph);
```
## Etapa 6: Salve a apresentação
```java
// Salvar a apresentação
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusão
Neste tutorial, exploramos como aprimorar suas apresentações do PowerPoint em Java com texto sobrescrito e subscrito usando o Aspose.Slides para Java. Seguindo esses passos, você poderá criar slides visualmente mais atraentes e informativos, que comunicarão seu conteúdo de forma eficaz.

## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides para Java é uma biblioteca robusta que permite aos desenvolvedores criar, manipular e converter apresentações do PowerPoint programaticamente.
### Onde posso encontrar mais documentação sobre o Aspose.Slides para Java?
Documentação detalhada pode ser encontrada [aqui](https://reference.aspose.com/slides/java/).
### Como posso obter uma licença temporária para o Aspose.Slides para Java?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).
### Posso testar o Aspose.Slides para Java gratuitamente?
Sim, você pode baixar uma versão de teste gratuita em [aqui](https://releases.aspose.com/).
### Onde posso obter suporte para o Aspose.Slides para Java?
Para suporte e discussões, visite o [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
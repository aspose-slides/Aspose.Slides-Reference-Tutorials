---
title: Obtenha o retângulo da porção no PowerPoint com Java
linktitle: Obtenha o retângulo da porção no PowerPoint com Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como obter o retângulo da parte no PowerPoint usando Aspose.Slides for Java com este tutorial passo a passo detalhado. Perfeito para desenvolvedores Java.
weight: 12
url: /pt/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
Criar apresentações dinâmicas em Java é muito fácil com Aspose.Slides for Java. Neste tutorial, mergulharemos nos detalhes de como obter o retângulo da parte no PowerPoint usando Aspose.Slides. Abordaremos tudo, desde a configuração do seu ambiente até a divisão do código passo a passo. Então vamos começar!
## Pré-requisitos
Antes de passarmos para o código, vamos garantir que você tenha tudo o que precisa para prosseguir sem problemas:
1. Java Development Kit (JDK): Certifique-se de ter o JDK 8 ou superior instalado em sua máquina.
2.  Aspose.Slides para Java: Baixe a versão mais recente em[aqui](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Eclipse, IntelliJ IDEA ou qualquer outro IDE Java de sua escolha.
4. Conhecimento básico de Java: A compreensão da programação Java é essencial.
## Importar pacotes
Primeiramente, vamos importar os pacotes necessários. Isso incluirá Aspose.Slides e alguns outros para lidar com nossa tarefa com eficiência.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Etapa 1: configurando a apresentação
primeiro passo é criar uma nova apresentação. Esta será a nossa tela para trabalhar.
```java
Presentation pres = new Presentation();
```
## Etapa 2: Criando uma Tabela
Agora, vamos adicionar uma tabela ao primeiro slide da nossa apresentação. Esta tabela conterá as células onde adicionaremos nosso texto.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Etapa 3: adicionar parágrafos às células
A seguir, criaremos parágrafos e os adicionaremos a uma célula específica da tabela. Isso envolve limpar qualquer texto existente e adicionar novos parágrafos.
```java
// Crie parágrafos
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Adicione texto na célula da tabela
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Etapa 4: adicionar um quadro de texto a uma forma automática
Para tornar nossa apresentação mais dinâmica, adicionaremos um quadro de texto a uma AutoForma e definiremos seu alinhamento.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Etapa 5: Calculando Coordenadas
Precisamos obter as coordenadas do canto superior esquerdo da célula da tabela. Isso nos ajudará a posicionar as formas com precisão.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Etapa 6: adicionar molduras a parágrafos e partes
 Usando o`IParagraph.getRect()` e`IPortion.getRect()`métodos, podemos adicionar molduras aos nossos parágrafos e porções. Isso envolve iterar pelos parágrafos e partes, criar formas em torno deles e personalizar sua aparência.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Etapa 7: adicionar molduras aos parágrafos do AutoShape
Da mesma forma, adicionaremos molduras aos parágrafos da nossa AutoForma, melhorando o apelo visual da apresentação.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Etapa 8: salvando a apresentação
Finalmente, salvaremos nossa apresentação em um caminho especificado.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Etapa 9: Limpeza
É uma boa prática descartar o objeto de apresentação para liberar recursos.
```java
if (pres != null) pres.dispose();
```
## Conclusão
Parabéns! Você aprendeu com sucesso como obter o retângulo da parte no PowerPoint usando Aspose.Slides para Java. Esta poderosa biblioteca abre um mundo de possibilidades para a criação programática de apresentações dinâmicas e visualmente atraentes. Mergulhe mais fundo no Aspose.Slides e explore mais recursos para aprimorar ainda mais suas apresentações.
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar e manipular apresentações do PowerPoint de forma programática.
### Posso usar Aspose.Slides for Java em projetos comerciais?
 Sim, Aspose.Slides for Java pode ser usado em projetos comerciais. Você pode comprar uma licença de[aqui](https://purchase.aspose.com/buy).
### Existe um teste gratuito disponível para Aspose.Slides for Java?
 Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### Onde posso encontrar a documentação do Aspose.Slides for Java?
 A documentação está disponível[aqui](https://reference.aspose.com/slides/java/).
### Como posso obter suporte para Aspose.Slides para Java?
 Você pode obter suporte no fórum Aspose[aqui](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

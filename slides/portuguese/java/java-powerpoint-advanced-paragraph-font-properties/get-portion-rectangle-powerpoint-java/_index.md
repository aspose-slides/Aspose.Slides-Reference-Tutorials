---
"description": "Aprenda como obter o retângulo de porção no PowerPoint usando o Aspose.Slides para Java com este tutorial detalhado e passo a passo. Perfeito para desenvolvedores Java."
"linktitle": "Obtenha retângulo de porção no PowerPoint com Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Obtenha retângulo de porção no PowerPoint com Java"
"url": "/pt/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Obtenha retângulo de porção no PowerPoint com Java

## Introdução
Criar apresentações dinâmicas em Java é muito fácil com o Aspose.Slides para Java. Neste tutorial, vamos nos aprofundar nos detalhes de como criar o retângulo de porção no PowerPoint usando o Aspose.Slides. Abordaremos tudo, desde a configuração do seu ambiente até a análise passo a passo do código. Então, vamos começar!
## Pré-requisitos
Antes de começarmos a trabalhar no código, vamos garantir que você tenha tudo o que precisa para seguir adiante sem problemas:
1. Java Development Kit (JDK): certifique-se de ter o JDK 8 ou superior instalado em sua máquina.
2. Aspose.Slides para Java: Baixe a versão mais recente em [aqui](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Eclipse, IntelliJ IDEA ou qualquer outro IDE Java de sua escolha.
4. Conhecimento básico de Java: É essencial entender a programação em Java.
## Pacotes de importação
Antes de mais nada, vamos importar os pacotes necessários. Isso inclui o Aspose.Slides e alguns outros para executar nossa tarefa com eficiência.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Etapa 1: Configurando a apresentação
O primeiro passo é criar uma nova apresentação. Esta será a nossa tela de trabalho.
```java
Presentation pres = new Presentation();
```
## Etapa 2: Criando uma tabela
Agora, vamos adicionar uma tabela ao primeiro slide da nossa apresentação. Essa tabela conterá as células onde adicionaremos o texto.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Etapa 3: Adicionando parágrafos às células
Em seguida, criaremos parágrafos e os adicionaremos a uma célula específica da tabela. Isso envolve limpar todo o texto existente e adicionar novos parágrafos.
```java
// Criar parágrafos
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Adicionar texto na célula da tabela
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Etapa 4: Adicionar um quadro de texto a uma AutoForma
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
## Etapa 6: Adicionando quadros a parágrafos e partes
Usando o `IParagraph.getRect()` e `IPortion.getRect()` Com os métodos, podemos adicionar molduras aos nossos parágrafos e partes. Isso envolve iterar pelos parágrafos e partes, criar formas ao redor deles e personalizar sua aparência.
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
## Etapa 7: Adicionando quadros aos parágrafos de AutoForma
Da mesma forma, adicionaremos quadros aos parágrafos em nossa AutoForma, aprimorando o apelo visual da apresentação.
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
## Etapa 8: Salvando a apresentação
Por fim, salvaremos nossa apresentação em um caminho especificado.
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
Parabéns! Você aprendeu com sucesso como obter o retângulo de porção no PowerPoint usando o Aspose.Slides para Java. Esta poderosa biblioteca abre um mundo de possibilidades para a criação de apresentações dinâmicas e visualmente atraentes por meio de programação. Explore mais recursos do Aspose.Slides para aprimorar ainda mais suas apresentações.
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides para Java é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar e manipular apresentações do PowerPoint programaticamente.
### Posso usar o Aspose.Slides para Java em projetos comerciais?
Sim, o Aspose.Slides para Java pode ser usado em projetos comerciais. Você pode adquirir uma licença em [aqui](https://purchase.aspose.com/buy).
### Existe uma avaliação gratuita disponível do Aspose.Slides para Java?
Sim, você pode baixar uma versão de teste gratuita em [aqui](https://releases.aspose.com/).
### Onde posso encontrar a documentação do Aspose.Slides para Java?
A documentação está disponível [aqui](https://reference.aspose.com/slides/java/).
### Como posso obter suporte para o Aspose.Slides para Java?
Você pode obter suporte no fórum Aspose [aqui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
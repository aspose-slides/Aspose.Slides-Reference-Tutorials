---
date: '2026-02-09'
description: Aprenda a desenhar molduras ao redor do texto e a adicionar texto às
  células de tabelas no PowerPoint usando Aspose.Slides for Java. Este tutorial aborda
  a criação de tabelas, o ajuste do alinhamento de texto e a gravação da apresentação
  como pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Como desenhar quadros e adicionar texto a uma tabela com Aspose.Slides para
  Java
url: /pt/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como desenhar quadros e adicionar texto a tabelas em apresentações com Aspose.Slides para Java

## Introduction

Apresentar dados de forma clara no PowerPoint pode ser um verdadeiro obstáculo, especialmente quando você precisa **adicionar texto a tabelas** e destacar valores importantes com recursos visuais. Neste guia você aprenderá **como desenhar quadros** ao redor de parágrafos específicos, definir o alinhamento de texto dentro de formas e, finalmente, **salvar a apresentação como pptx** — tudo usando Aspose.Slides para Java. Ao final, você terá um conjunto de slides polido que direciona o olhar da audiência exatamente onde você deseja.

Pronto para fazer seus slides se destacarem? Vamos percorrer o processo passo a passo.

## Quick Answers
- **O que significa “add text to table”?** Significa inserir ou atualizar o conteúdo textual de células individuais de tabela programaticamente.  
- **Qual método salva o arquivo?** `pres.save("output.pptx", SaveFormat.Pptx)` – esta etapa de **save presentation as pptx** finaliza suas alterações.  
- **Como posso alinhar texto dentro de uma forma?** Use `TextAlignment.Left` (ou Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Posso desenhar um retângulo ao redor de um parágrafo?** Sim – itere sobre os parágrafos, obtenha seu retângulo delimitador e adicione um `IAutoShape` sem preenchimento e com linha preta.  
- **Preciso de uma licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para uso em produção.  

## Why draw frames around text?

Desenhar um quadro (ou retângulo) ao redor de um parágrafo ou de uma porção específica (por exemplo, qualquer texto contendo o caractere **'0'**) chama imediatamente a atenção. Esta técnica é ideal para:

- Destacar números financeiros chave em uma tabela.  
- Enfatizar avisos ou notas importantes em um slide.  
- Criar separadores visuais sem adicionar formas extras manualmente.

## Prerequisites

Antes de mergulhar no código, certifique-se de que você tem o seguinte:

### Required Libraries
Você precisará do Aspose.Slides para Java. Veja como incluí-lo usando Maven ou Gradle:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Environment Setup
Certifique-se de ter um Java Development Kit (JDK) instalado, de preferência JDK 16 ou superior, pois este exemplo usa o classificador `jdk16`.

### Knowledge Prerequisites
- Compreensão básica de programação Java.  
- Familiaridade com softwares de apresentação como PowerPoint.  
- Experiência usando um Ambiente de Desenvolvimento Integrado (IDE) como IntelliJ IDEA ou Eclipse.

## Setting Up Aspose.Slides for Java

Para começar a usar o Aspose.Slides, siga estas etapas:

1. **Instalar a Biblioteca**: Use Maven ou Gradle para gerenciar dependências, ou faça o download diretamente de [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Comece com um teste gratuito baixando uma licença temporária em [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Para acesso total, considere adquirir uma licença em [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Inicialização Básica**:
Inicialize seu ambiente de apresentação com o trecho de código a seguir:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## How to Add Text to Table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
Este recurso demonstra como **criar tabela**, então **adicionar texto a tabelas** nas células e, posteriormente, **salvar a apresentação como pptx**.

#### Steps

**1. Criar uma Tabela**  
Primeiro, inicialize sua apresentação e adicione uma tabela na posição (50, 50) com larguras de coluna e alturas de linha especificadas.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Adicionar Texto às Células**  
Crie parágrafos com porções de texto e adicione-os a uma célula específica.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Salvar a Apresentação**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 2: Add TextFrame to AutoShape and Set Alignment

#### Overview
Aprenda como adicionar um quadro de texto com alinhamento específico a uma forma automática — um exemplo de **set text alignment java**.

#### Steps

**1. Adicionar um AutoShape**  
Adicione um retângulo como AutoShape na posição (400, 100) com dimensões especificadas.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Definir Alinhamento de Texto**  
Defina o texto para “Text in shape” e alinhe-o à esquerda.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Salvar a Apresentação**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 3: Draw Frames around Paragraphs and Portions in Table Cells

#### Overview
Este recurso foca em **draw frames around text** e até mesmo **draw rectangle around paragraph** para porções contendo o caractere ‘0’.

#### Steps

**1. Criar uma Tabela**  
Reutilize o código de “Create Table and Add Text to Cells” para a configuração inicial.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Adicionar Parágrafos**  
Reutilize o código de criação de parágrafos do recurso anterior.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Desenhar Quadros**  
Itere sobre os parágrafos e porções para desenhar quadros ao redor deles.
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```

**4. Salvar a Apresentação**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Common Pitfalls & Tips

- **Verificações de null** – Sempre envolva o uso de `Presentation` em um bloco try‑finally para garantir que `pres.dispose()` seja executado e libere recursos nativos.  
- **Precisão do retângulo delimitador** – O retângulo retornado por `para.getRect()` reflete o layout atual; se você alterar o tamanho da fonte ou margens, recalcule o retângulo antes de desenhar o quadro.  
- **Desempenho** – Ao trabalhar com tabelas muito grandes, considere agrupar adições de formas ou reutilizar uma única instância de `IAutoShape` com geometria atualizada para reduzir o consumo de memória.

## Frequently Asked Questions

**P: Posso usar essas APIs com versões mais antigas do JDK?**  
R: A biblioteca suporta JDK 8 em diante, mas o classificador `jdk16` oferece o melhor desempenho em runtimes mais recentes.

**P: Como altero a cor do quadro?**  
R: Modifique a cor de preenchimento do formato de linha, por exemplo, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**P: É possível exportar o slide final como imagem?**  
R: Sim—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` e então salve o array de bytes.

**P: E se eu precisar destacar apenas a palavra “Total” dentro de uma célula?**  
R: Itere através de `cell.getTextFrame().getParagraphs()`, localize a porção que contém “Total” e desenhe um retângulo ao redor da caixa delimitadora dessa porção.

**P: O Aspose.Slides lida eficientemente com apresentações grandes?**  
R: A API transmite dados em fluxo e libera recursos quando `pres.dispose()` é chamado, o que ajuda no gerenciamento de memória para arquivos grandes.

---

**Última atualização:** 2026-02-09  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

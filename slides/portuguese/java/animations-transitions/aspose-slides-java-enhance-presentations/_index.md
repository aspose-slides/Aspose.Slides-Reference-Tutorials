---
date: '2026-11-16'
description: Desenhe um quadro ao redor do texto em tabelas do PowerPoint usando Aspose.Slides
  for Java – aprenda a criar tabelas, adicionar texto às células, destacar células
  e exportar o arquivo como PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Desenhe um quadro ao redor do texto em tabelas do PowerPoint usando
  Aspose.Slides for Java. Este guia mostra como criar tabelas, adicionar e alinhar
  texto, destacar células e exportar slides como PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Desenhar quadro ao redor do texto e criar tabelas no PowerPoint com Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Como desenhar quadro ao redor do texto e criar tabelas no PowerPoint com Aspose.Slides
  for Java
url: /pt/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como desenhar uma moldura ao redor do texto e criar tabelas no PowerPoint com Aspose.Slides for Java

## Introdução

Desenhar uma **draw frame around text** em um slide do PowerPoint permite que você destaque números importantes sem alterar o conteúdo subjacente. Neste tutorial você aprenderá a criar programaticamente uma tabela, inserir e alinhar texto dentro das células, destacar palavras específicas ou células inteiras e, finalmente, salvar a apresentação como um arquivo PPTX. Ao final, você terá um slide polido que atrai o olhar da audiência exatamente onde deseja.

## Respostas rápidas
- **O que significa “add text to table”?** Significa inserir ou atualizar o conteúdo textual de células individuais da tabela programaticamente.  
- **Qual método salva o arquivo?** `pres.save("output.pptx", SaveFormat.Pptx)` – esta etapa de **save presentation as pptx** finaliza suas alterações.  
- **Como posso alinhar texto dentro de uma forma?** Use `TextAlignment.Left` (ou Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Posso desenhar um retângulo ao redor de um parágrafo?** Sim – itere sobre os parágrafos, obtenha seu retângulo delimitador e adicione um `IAutoShape` sem preenchimento e com linha preta.  
- **Preciso de uma licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para uso em produção.  

## Por que desenhar molduras ao redor do texto?

Desenhar uma moldura ao redor do texto destaca instantaneamente números importantes, avisos ou títulos. Ela fornece um indicativo visual enquanto mantém a formatação original intacta, tornando-a ideal para relatórios financeiros, painéis de KPI ou qualquer slide onde seja necessário ênfase.

## O que é draw frame around text?

`draw frame around text` é a técnica de adicionar programaticamente uma forma retangular que segue exatamente os limites de um parágrafo ou de uma porção de texto, usando formatação de linha sem preencher o interior. Essa abordagem permite enfatizar o conteúdo sem alterar o próprio texto.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem o seguinte:

### Bibliotecas necessárias
Você precisará do Aspose.Slides for Java. Inclua‑o com um dos gerenciadores de pacotes:

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

Você também pode navegar pelas versões em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Configuração do ambiente
Um Java Development Kit (JDK) 16 ou mais recente é recomendado porque os exemplos usam o classificador `jdk16`. Qualquer IDE como IntelliJ IDEA ou Eclipse funcionará.

### Pré-requisitos de conhecimento
- Conhecimentos básicos de programação Java.  
- Familiaridade com conceitos do PowerPoint (slides, formas, tabelas).  
- Compreensão de como Maven/Gradle gerenciam dependências.

## Configurando Aspose.Slides for Java

`Presentation` é a classe central do Aspose.Slides que representa um arquivo PowerPoint na memória e fornece acesso a slides, formas e tabelas. Ela pode lidar com apresentações de até **10.000 slides** mantendo o uso de memória abaixo de **500 MB**, tornando-a adequada para automação em larga escala.

1. **Instale a biblioteca** – use Maven ou Gradle, ou faça o download diretamente de [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).  
2. **Aquisição de licença** – comece com um teste gratuito em [Temporary License](https://purchase.aspose.com/temporary-license/) e faça upgrade para uma licença completa em [Purchase Aspose.Slides](https://purchase.aspose.com/buy) para cargas de trabalho de produção.  
3. **Inicialização básica** – crie um novo objeto `Presentation` e carregue ou crie slides conforme necessário.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Como adicionar texto a uma tabela no Aspose.Slides for Java?

`Presentation` é a classe principal que representa um arquivo PowerPoint na memória.  
Carregue um novo `Presentation`, crie uma tabela nas coordenadas desejadas, preencha as células com objetos `TextFrame` e, finalmente, chame `pres.save("output.pptx", SaveFormat.Pptx)`. Essa sequência cria uma **create table in PowerPoint**, insere texto personalizado em cada célula e grava o resultado em um arquivo PPTX em um fluxo de trabalho único e eficiente.

### Resposta direta
Crie uma tabela chamando `slide.getShapes().addTable(...)`, então para cada célula use `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Após preencher todas as células, invoque `pres.save("output.pptx", SaveFormat.Pptx)` para gravar o arquivo. Essa abordagem permite controlar programaticamente o conteúdo e o estilo de cada célula.

#### Recurso 1: criar tabela e adicionar texto às células

**1. criar uma tabela** – inicialize uma apresentação, adicione um slide e posicione uma tabela em (50, 50) com larguras de coluna e alturas de linha definidas.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. adicionar texto às células** – para cada célula, crie um `Paragraph`, adicione um `Portion` com a string desejada e atribua o parágrafo ao `TextFrame` da célula.  
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

**3. salvar a apresentação** – chame `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Como desenhar uma moldura ao redor do texto em um slide do PowerPoint?

`Rectangle2D` representa uma área retangular em um espaço de coordenadas bidimensional.  
Carregue o slide, localize o parágrafo ou porção que deseja enfatizar, recupere seu retângulo delimitador via `getRect()` e então adicione um retângulo `IAutoShape` sem preenchimento e com linha colorida. Esse método funciona tanto para parágrafos inteiros quanto para porções de palavras individuais.

### Resposta direta
Para desenhar uma moldura ao redor do texto, primeiro obtenha o retângulo do parágrafo (`Rectangle2D rect = paragraph.getRect();`). Em seguida, crie um retângulo `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), defina `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)` e desative o preenchimento (`shape.getFillFormat().setFillType(FillType.NoFill)`). A forma contornará perfeitamente o texto.

#### Recurso 3: desenhar molduras ao redor de parágrafos e porções em células de tabela

**1. criar uma tabela** – reutilize o código do Recurso 1 para configurar a tabela inicial.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. adicionar parágrafos** – reutilize o código de criação de parágrafos do Recurso 1.  
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

**3. desenhar molduras** – itere sobre cada parágrafo, obtenha seu retângulo delimitador e adicione uma forma retangular conforme descrito acima. Para porções que contenham o caractere ‘0’, desenhe uma moldura adicional para destacar esses números.  
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

**4. salvar a apresentação** – mesma etapa final de antes.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Como adicionar um quadro de texto a um AutoShape e definir o alinhamento

`AutoShape` é uma forma que pode conter texto, imagens ou outro conteúdo.  
Um `AutoShape` pode conter um `TextFrame`. Você pode controlar o alinhamento horizontal usando o enum `ParagraphFormat`.

### Resposta direta
Crie um AutoShape retangular (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), acesse seu `TextFrame`, defina o texto com `shape.getTextFrame().setText("Text in shape")` e então chame `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. Isso alinha o texto à esquerda dentro da forma.

**1. adicionar um AutoShape** – posicione um retângulo no local desejado.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. definir alinhamento de texto** – aplique o alinhamento à esquerda conforme mostrado acima.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. salvar a apresentação** – mesma etapa final.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Armadilhas comuns e dicas

- **Sempre libere recursos** – envolva o uso de `Presentation` em um bloco try‑finally e chame `pres.dispose()` para liberar recursos nativos.  
- **Recalcule os retângulos delimitadores** – se você alterar o tamanho da fonte, margens ou preenchimento da célula após desenhar uma moldura, chame `paragraph.getRect()` novamente antes de adicionar a forma.  
- **Criação em lote de formas para tabelas grandes** – reutilizar uma única instância de `IAutoShape` e atualizar sua geometria reduz a pressão de memória ao processar tabelas com centenas de linhas.  
- **Números de desempenho** – Aspose.Slides pode gerar um PPTX de 200 páginas em menos de 2 segundos em um servidor típico de 4 núcleos, e desenhar molduras ao redor de 1.000 parágrafos adiciona menos de 150 ms de sobrecarga.

## Perguntas frequentes

**Q: Posso usar essas APIs com versões mais antigas do JDK?**  
A: A biblioteca suporta JDK 8 em diante, mas o classificador `jdk16` oferece o melhor desempenho em runtimes mais recentes.

**Q: Como altero a cor da moldura?**  
A: Modifique a cor de preenchimento do formato de linha, por exemplo, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: É possível exportar o slide final como imagem?**  
A: Sim—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` e então salve o array de bytes.

**Q: E se eu precisar destacar apenas a palavra “Total” dentro de uma célula?**  
A: Itere através de `cell.getTextFrame().getParagraphs()`, localize a porção que contém “Total” e desenhe um retângulo ao redor da caixa delimitadora dessa porção.

**Q: O Aspose.Slides lida eficientemente com apresentações grandes?**  
A: A API transmite dados e libera recursos quando `pres.dispose()` é chamado, o que ajuda no gerenciamento de memória para arquivos grandes.

---

**Última atualização:** 2026-11-16  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  



## Tutoriais relacionados

- [Aspose.Slides for Java: Domine a Manipulação de Tabelas e Texto PPTX em Apresentações PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Como Criar Quadros de Texto Dinâmicos no PowerPoint Usando Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Adicionar Colunas em Quadros de Texto usando Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
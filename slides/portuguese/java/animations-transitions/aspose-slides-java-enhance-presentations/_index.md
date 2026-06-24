---
date: '2026-06-23'
description: Aprenda como criar tabela no PowerPoint, adicionar texto às células da
  tabela, desenhar quadros ao redor do texto e salvar a apresentação como pptx usando
  Aspose.Slides for Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: Como criar tabela no PowerPoint e desenhar quadros com Aspose.Slides for Java
url: /pt/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar tabela no PowerPoint e desenhar quadros com Aspose.Slides para Java

## Introdução

Criar uma **create table in PowerPoint** programaticamente pode economizar horas de formatação manual, especialmente quando você precisa destacar números-chave ou adicionar notas explicativas. Neste tutorial você descobrirá como adicionar texto a células de tabela, desenhar quadros ao redor de parágrafos específicos, definir alinhamento preciso do texto e, finalmente, **save presentation as pptx** – tudo com a poderosa API Aspose.Slides para Java. Ao final, você terá um slide com aparência polida, fácil de ler e que atrai instantaneamente a atenção do público para os dados mais importantes.

## Respostas rápidas
- **O que significa “add text to table”?** Significa inserir ou atualizar o conteúdo textual de células individuais da tabela programaticamente.  
- **Qual método salva o arquivo?** `pres.save("output.pptx", SaveFormat.Pptx)` – esta etapa de **save presentation as pptx** finaliza suas alterações.  
- **Como posso alinhar texto dentro de uma forma?** Use `TextAlignment.Left` (ou Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Posso desenhar um retângulo ao redor de um parágrafo?** Sim – itere sobre os parágrafos, obtenha seu retângulo delimitador e adicione um `IAutoShape` sem preenchimento e com linha preta.  
- **Preciso de uma licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para uso em produção.  

## Por que desenhar quadros ao redor do texto?

Desenhar um quadro (ou retângulo) ao redor de um parágrafo ou de uma parte específica — como qualquer texto contendo o caractere **'0'** — atrai instantaneamente a atenção do público para esse conteúdo. Ele fornece um indicativo visual claro sem alterar o texto subjacente, sendo ideal para destacar números-chave, avisos ou separar seções dentro de um slide.

## Pré-requisitos

Antes de mergulhar no código, certifique‑se de que você tem o seguinte:

### Bibliotecas necessárias
Você precisará do Aspose.Slides para Java. Veja como incluí‑lo usando Maven ou Gradle:

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

### Configuração do ambiente
Certifique‑se de que o Java Development Kit (JDK) está instalado, preferencialmente JDK 16 ou superior, pois este exemplo usa o classificador `jdk16`.

### Pré-requisitos de conhecimento
- Compreensão básica de programação Java.  
- Familiaridade com softwares de apresentação como PowerPoint.  
- Experiência usando um Ambiente de Desenvolvimento Integrado (IDE) como IntelliJ IDEA ou Eclipse.

## Configurando Aspose.Slides para Java

`Presentation` é a classe central do Aspose.Slides que representa um arquivo PowerPoint na memória e fornece acesso a slides, formas e tabelas. Para começar a usar o Aspose.Slides, siga estas etapas:

1. **Instalar a biblioteca**: Use Maven ou Gradle para gerenciar dependências, ou faça o download direto em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **Aquisição de licença**:
   - Comece com um teste gratuito baixando uma licença temporária em [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Para acesso total, considere comprar uma licença em [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Inicialização básica**:  
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

## Como adicionar texto a uma tabela no Aspose.Slides para Java?

Carregue uma nova `Presentation`, crie uma tabela nas coordenadas desejadas, preencha as células com objetos `TextFrame` e, finalmente, chame `pres.save("output.pptx", SaveFormat.Pptx)`. Essa sequência cria uma **create table in PowerPoint**, injeta texto personalizado em cada célula e grava o resultado em um arquivo PPTX em um fluxo de trabalho único e eficiente.

### Recurso 1: Criar tabela e adicionar texto às células

#### Visão geral
Este recurso demonstra como **create table**, depois **add text to table** nas células e, por fim, **save presentation as pptx**.

#### Etapas

**1. Criar uma tabela**  
Primeiro, inicialize sua apresentação e adicione uma tabela na posição (50, 50) com larguras de coluna e alturas de linha especificadas.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Adicionar texto às células**  
Crie parágrafos com trechos de texto e adicione‑os a uma célula específica.  
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

**3. Salvar a apresentação**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Recurso 2: Adicionar TextFrame a AutoShape e definir alinhamento

#### Visão geral
Aprenda a adicionar um quadro de texto com alinhamento específico a uma auto shape — um exemplo de **set text alignment java**.

#### Etapas

Um AutoShape é uma forma que pode conter texto e gráficos.

**1. Adicionar um AutoShape**  
Adicione um retângulo como AutoShape na posição (400, 100) com dimensões especificadas.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

O enum `TextAlignment` define opções de alinhamento horizontal para texto dentro de uma forma.

**2. Definir alinhamento do texto**  
Defina o texto para “Text in shape” e alinhe‑o à esquerda.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Salvar a apresentação**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Recurso 3: Desenhar quadros ao redor de parágrafos e trechos em células de tabela

#### Visão geral
Este recurso foca em **draw frames around text** e até mesmo **draw rectangle around paragraph** para trechos que contenham o caractere ‘0’.

#### Etapas

`IAutoShape` representa um objeto de forma que pode ser desenhado em um slide, como retângulos usados para quadros.

**1. Criar uma tabela**  
Reutilize o código de “Criar tabela e adicionar texto às células” para a configuração inicial.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Adicionar parágrafos**  
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

**3. Desenhar quadros**  
Itere sobre os parágrafos e trechos para desenhar quadros ao redor deles.  
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

**4. Salvar a apresentação**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Armadilhas comuns e dicas

- **Verificações de nulidade** – Sempre envolva o uso de `Presentation` em um bloco try‑finally para garantir que `pres.dispose()` seja executado e libere recursos nativos.  
- **Precisão do retângulo delimitador** – O retângulo retornado por `para.getRect()` reflete o layout atual; se você alterar o tamanho da fonte ou margens, recalcule o retângulo antes de desenhar o quadro.  
- **Desempenho** – Ao trabalhar com tabelas muito grandes, considere agrupar adições de formas ou reutilizar uma única instância de `IAutoShape` com geometria atualizada para reduzir a sobrecarga de memória.  

## Perguntas frequentes

**Q: Posso usar essas APIs com versões mais antigas do JDK?**  
A: A biblioteca suporta JDK 8 em diante, mas o classificador `jdk16` oferece o melhor desempenho em runtimes mais recentes.

**Q: Como altero a cor do quadro?**  
A: Modifique a cor de preenchimento do formato de linha, por exemplo, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: É possível exportar o slide final como imagem?**  
A: Sim — use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` e então salve o array de bytes.

**Q: E se eu precisar destacar apenas a palavra “Total” dentro de uma célula?**  
A: Itere através de `cell.getTextFrame().getParagraphs()`, localize o trecho que contém “Total” e desenhe um retângulo ao redor da caixa delimitadora desse trecho.

**Q: O Aspose.Slides lida eficientemente com apresentações grandes?**  
A: A API faz streaming de dados e libera recursos quando `pres.dispose()` é chamado, o que ajuda no gerenciamento de memória para arquivos volumosos.

---

**Última atualização:** 2026-06-23  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais relacionados

- [Aspose.Slides para Java: Domine a manipulação de tabelas e texto em PPTX nas apresentações PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Como criar quadros de texto dinâmicos no PowerPoint usando Aspose.Slides para Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Adicionar colunas em Text Frame usando Aspose.Slides para Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
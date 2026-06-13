---
date: '2026-03-07'
description: Aprenda a criar gráficos de rosca em Java usando Aspose.Slides. Este
  guia passo a passo cobre a configuração da dependência Maven do Aspose Slides, a
  configuração do gráfico e a gravação de apresentações.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Criar Gráfico de Rosca Java com Guia Aspose.Slides
url: /pt/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criar Gráfico de Rosca Java com o Guia Aspose.Slides

## Introdução

Criar um **doughnut chart** programaticamente pode transformar números brutos em um visual atraente que conta uma história instantaneamente. Em Java, **Aspose.Slides** torna esse processo simples, permitindo gerar gráficos prontos para apresentação sem nunca abrir o PowerPoint. Neste tutorial você aprenderá como **create doughnut chart java** passo a passo — desde a configuração da dependência Maven Aspose Slides até a personalização de séries, categorias e, finalmente, salvar a apresentação.

Ao final deste guia, você poderá incorporar gráficos de rosca dinâmicos em qualquer arquivo PPTX, perfeito para relatórios, painéis ou decks de slides automatizados.

### Respostas Rápidas
- **Qual biblioteca é usada?** Aspose.Slides for Java  
- **Tarefa principal?** Create doughnut chart java in a PPTX file  
- **Como adicionar a biblioteca?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Versão mínima do Java?** JDK 16 or higher  
- **Posso personalizar cores e rótulos?** Yes, the API provides full formatting control  

## O que é um Gráfico de Rosca e Por que Usá‑lo?

Um doughnut chart é uma variação de um gráfico de pizza com um centro vazio, permitindo exibir várias séries de dados em anéis concêntricos. Isso o torna ideal para comparar partes de um todo em várias categorias — pense em vendas por região ao longo de vários trimestres ou alocações de orçamento entre departamentos.

## Por que usar Aspose.Slides para Java?

- **Nenhuma instalação do Office necessária** – gerar arquivos PPTX em qualquer servidor.  
- **API rica** – controle total sobre tipos de gráfico, pontos de dados e estilo.  
- **Alto desempenho** – otimizado para apresentações grandes.  
- **Multiplataforma** – funciona no Windows, Linux e macOS.

## Pré‑requisitos

- **Bibliotecas necessárias:**  
  - Aspose.Slides for Java versão 25.4 ou posterior.  

- **Configuração do ambiente:**  
  - JDK 16 ou superior.  
  - Seu IDE favorito (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Pré‑requisitos de conhecimento:**  
  - Programação Java básica.  
  - Familiaridade com Maven ou Gradle para gerenciamento de dependências.

## Dependência Maven Aspose Slides

Adicione a seguinte dependência Maven ao seu `pom.xml`. Esta é a **maven aspose slides dependency** que você precisa para incluir a biblioteca em seu projeto.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Se preferir Gradle, use o trecho equivalente abaixo.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Você também pode baixar o JAR diretamente da página oficial de lançamentos:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Obtendo uma Licença

Para remover a marca d'água de avaliação e desbloquear o conjunto completo de recursos:

- **Teste gratuito** – comece com uma licença temporária.  
- **Licença temporária** – solicite uma no [site da Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licença comercial** – compre para uso em produção.

Aplique a licença no seu código:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guia de Implementação

### Inicializando a Apresentação e Adicionando um Gráfico de Rosca

Primeiro, crie ou carregue uma apresentação e adicione um doughnut chart ao primeiro slide.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configurando a Planilha de Dados do Gráfico e Limpando Dados Existentes

Em seguida, obtenha a planilha que suporta o gráfico e limpe quaisquer séries ou categorias padrão.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Adicionando Séries ao Gráfico

Agora adicionaremos até 15 séries. Cada série pode ser personalizada — aqui definimos a explosão, o tamanho do buraco da rosca e o ângulo da primeira fatia.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Adicionando Categorias e Pontos de Dados

Criaremos 15 categorias e preencheremos cada série com um ponto de dados. A última série recebe formatação especial de rótulo.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Salvando a Apresentação

Finalmente, grave a apresentação atualizada no disco.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Problemas Comuns e Soluções

- **Licença não encontrada** – Verifique se o caminho para `license.lic` está correto e o arquivo é legível.  
- **Gráfico aparece em branco** – Certifique-se de que limpou as séries/categorias existentes antes de adicionar novas.  
- **Cores incorretas** – Verifique se `FillType.Solid` está definido tanto para o preenchimento quanto para o formato da linha.  
- **Desempenho com muitas séries** – Limite o número de séries/categorias ou reutilize as células da planilha.

## Perguntas Frequentes

**Q: Posso gerar um doughnut chart sem um arquivo PPTX pré‑existente?**  
A: Sim, instancie `new Presentation()` para começar a partir de um deck de slides em branco.

**Q: O Aspose.Slides suporta exportação para PDF?**  
A: Absolutamente. Após criar o gráfico, chame `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: Como altero o tamanho do buraco da rosca?**  
A: Use `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` onde value é 0‑100.

**Q: É possível adicionar rótulos de dados a todas as séries, não apenas à última?**  
A: Sim, mova o bloco de formatação de rótulo para fora da condição `if (i == ...)` e aplique-o a cada `dataPoint`.

**Q: Quais versões do Java são suportadas?**  
A: Aspose.Slides 25.4 suporta JDK 16 e superiores. JDKs mais antigos requerem o classificador apropriado.

---

**Última atualização:** 2026-03-07  
**Testado com:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-17"
"description": "Aprenda a criar gráficos de rosca impressionantes em Java com o Aspose.Slides. Este guia completo aborda inicialização, configuração de dados e salvamento de apresentações."
"title": "Crie gráficos de rosca em Java usando Aspose.Slides - Um guia completo"
"url": "/pt/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crie gráficos de rosca em Java usando Aspose.Slides: um guia passo a passo

## Introdução

No ambiente atual, baseado em dados, visualizar informações de forma eficaz é fundamental para aumentar a compreensão e o engajamento. Embora criar gráficos profissionais programaticamente possa parecer desafiador, especialmente com Java, este guia o guiará pelo uso do Aspose.Slides para Java para criar gráficos de rosca sem esforço.

Seguindo essas etapas, os desenvolvedores ganharão experiência prática na manipulação de slides de apresentação e na integração perfeita da visualização de dados.

**Principais conclusões:**
- Inicialize um objeto Presentation usando Aspose.Slides Java.
- Configure dados do gráfico e gerencie séries ou categorias existentes.
- Adicione e personalize séries e categorias para seus gráficos.
- Formate e exiba pontos de dados de forma eficaz.
- Salve sua apresentação em vários formatos com facilidade.

Antes de começar a implementação, certifique-se de ter tudo o que é necessário para começar.

## Pré-requisitos

Para seguir este tutorial, certifique-se de ter:

- **Bibliotecas necessárias:**
  - Aspose.Slides para Java versão 25.4 ou posterior.
  
- **Configuração do ambiente:**
  - JDK 16 ou superior instalado no seu sistema.
  - Um IDE como IntelliJ IDEA, Eclipse ou NetBeans.

- **Pré-requisitos de conhecimento:**
  - Compreensão básica dos conceitos de programação Java.
  - Familiaridade com o gerenciamento de dependências em projetos Maven ou Gradle.

## Configurando o Aspose.Slides para Java

Para integrar o Aspose.Slides ao seu projeto, siga estas etapas com base na sua ferramenta de construção:

**Configuração do Maven:**
Adicione a seguinte dependência ao seu `pom.xml` arquivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Configuração do Gradle:**
Inclua o seguinte em seu `build.gradle` arquivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download direto:**
Alternativamente, baixe a versão mais recente diretamente de [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Obtenção de uma licença

Para usar o Aspose.Slides sem limitações de avaliação:
- **Teste gratuito:** Comece com uma licença temporária para explorar todos os recursos.
- **Licença temporária:** Obtenha um através do [Site Aspose](https://purchase.aspose.com/temporary-license/).
- **Comprar:** Considere comprar para uso contínuo.

Aplique sua licença em seu aplicativo Java usando:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guia de Implementação

### Inicializando Apresentação e Gráfico

#### Visão geral
Comece inicializando um objeto de apresentação e adicionando um gráfico de rosca ao primeiro slide.

**Etapa 1: Inicializar a apresentação**
Carregue um arquivo PPTX existente ou crie um novo:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Etapa 2: Adicionar gráfico de rosca**
Crie um gráfico no primeiro slide nas coordenadas especificadas:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configurando a pasta de trabalho de dados do gráfico e limpando séries/categorias existentes

#### Visão geral
Configure a pasta de trabalho de dados do gráfico e remova quaisquer séries ou categorias pré-existentes.

**Etapa 1: Acesse a pasta de trabalho de dados do gráfico**
Recupere a pasta de trabalho vinculada ao seu gráfico:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Etapa 2: limpar séries e categorias existentes**
Certifique-se de que não haja pontos de dados residuais:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Adicionando séries ao gráfico

#### Visão geral
Preencha seu gráfico com várias séries, cada uma personalizada em termos de aparência e comportamento.

**Etapa 1: Adicionar séries iterativamente**
Percorra os índices para adicionar séries:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Personalize a série
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Adicionando categorias e pontos de dados ao gráfico

#### Visão geral
Configure categorias e adicione pontos de dados com formatação específica para rótulos.

**Etapa 1: adicionar categorias**
Percorrer os índices de cada categoria:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Etapa 2: Adicionar pontos de dados a cada série**
Iterar por cada série para a categoria atual:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Configurações de formato de ponto de dados
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Formatação de rótulos para a última série
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

        // Ajustar opções de exibição
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Ajustar a posição da etiqueta
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Salvando a apresentação

#### Visão geral
Depois de configurar seu gráfico, salve a apresentação em um diretório especificado.

**Etapa 1: Salve a apresentação**
Use o `save` método para escrever alterações:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Conclusão

Agora você aprendeu a criar e personalizar gráficos de rosca em Java usando o Aspose.Slides. Estes passos fornecem uma base para integrar visualizações de dados sofisticadas às suas apresentações.

**Próximos passos:**
- Experimente diferentes tipos de gráficos disponíveis no Aspose.Slides.
- Explore opções adicionais de personalização, como cores, fontes e estilos para atender às suas necessidades de marca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
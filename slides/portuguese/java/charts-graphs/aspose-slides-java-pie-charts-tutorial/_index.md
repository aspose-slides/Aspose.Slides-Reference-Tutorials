---
"date": "2025-04-17"
"description": "Aprenda a criar e personalizar gráficos de pizza usando o Aspose.Slides para Java. Este tutorial aborda tudo, desde a configuração até a personalização avançada."
"title": "Criando gráficos de pizza em Java com Aspose.Slides&#58; um guia completo"
"url": "/pt/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criando gráficos de pizza com Aspose.Slides para Java: um tutorial completo

## Introdução
Criar apresentações dinâmicas e visualmente atraentes é crucial para transmitir informações impactantes. Com o Aspose.Slides para Java, você pode integrar gráficos complexos, como gráficos de pizza, aos seus slides, aprimorando a visualização de dados sem esforço. Este guia completo guiará você pelo processo de criação e personalização de um gráfico de pizza usando o Aspose.Slides Java, resolvendo desafios comuns de apresentação com facilidade.

**O que você aprenderá:**
- Inicializando uma apresentação e adicionando slides.
- Criando e configurando um gráfico de pizza no seu slide.
- Definir títulos de gráficos, rótulos de dados e cores.
- Otimizando o desempenho e gerenciando recursos de forma eficaz.
- Integrando Aspose.Slides em projetos Java usando Maven ou Gradle.

Vamos começar garantindo que você tenha todas as ferramentas e o conhecimento necessários para acompanhar!

## Pré-requisitos
Antes de começar este tutorial, certifique-se de ter a seguinte configuração pronta:

### Bibliotecas, versões e dependências necessárias
- **Aspose.Slides para Java**: Certifique-se de ter a versão 25.4 ou posterior.
- **Kit de Desenvolvimento Java (JDK)**: É necessária a versão 16 ou superior.

### Requisitos de configuração do ambiente
- Um ambiente de desenvolvimento com Java instalado e configurado.
- Um Ambiente de Desenvolvimento Integrado (IDE) como IntelliJ IDEA, Eclipse ou NetBeans.

### Pré-requisitos de conhecimento
- Noções básicas de programação Java.
- Familiaridade com Maven ou Gradle para gerenciamento de dependências.

## Configurando o Aspose.Slides para Java
Para começar a usar o Aspose.Slides em seus projetos Java, você precisa adicionar a biblioteca como dependência. Veja como fazer isso usando diferentes ferramentas de compilação:

**Especialista**
Adicione este trecho ao seu `pom.xml` arquivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Inclua o seguinte em seu `build.gradle` arquivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download direto**
Se preferir não usar uma ferramenta de construção, baixe a versão mais recente em [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Etapas de aquisição de licença
- **Teste grátis**: Comece com um teste gratuito para explorar os recursos do Aspose.Slides.
- **Licença Temporária**: Obtenha uma licença temporária para uso estendido sem limitações.
- **Comprar**: Considere comprar se precisar de acesso de longo prazo.

**Inicialização e configuração básicas**
Para começar a usar o Aspose.Slides, inicialize seu projeto criando um novo objeto de apresentação:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guia de Implementação
Agora vamos dividir o processo de adição e personalização de um gráfico de pizza em etapas gerenciáveis.

### Inicializar apresentação e slide
Comece configurando uma nova apresentação e acessando o primeiro slide. Esta é a sua tela para criar gráficos:
```java
import com.aspose.slides.*;

// Crie uma nova instância de apresentação.
Presentation presentation = new Presentation();
// Acesse o primeiro slide da apresentação.
islide slides = presentation.getSlides().get_Item(0);
```

### Adicionar gráfico de pizza ao slide
Insira um gráfico de pizza na posição especificada com um conjunto de dados padrão:
```java
import com.aspose.slides.*;

// Adicione um gráfico de pizza na posição (100, 100) com tamanho (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Definir título do gráfico
Personalize seu gráfico definindo e centralizando o título:
```java
import com.aspose.slides.*;

// Adicione um título ao gráfico de pizza.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurar rótulos de dados para séries
Certifique-se de que os rótulos de dados exibam valores para maior clareza:
```java
import com.aspose.slides.*;

// Mostrar valores de dados na primeira série.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Preparar planilha de dados do gráfico
Configure a planilha de dados do seu gráfico limpando séries e categorias existentes:
```java
import com.aspose.slides.*;

// Prepare a pasta de trabalho de dados do gráfico.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Adicionar categorias ao gráfico
Defina categorias para seu gráfico de pizza:
```java
import com.aspose.slides.*;

// Adicione novas categorias.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Adicionar séries e preencher pontos de dados
Crie uma série e preencha-a com pontos de dados:
```java
import com.aspose.slides.*;

// Adicione uma nova série e defina seu nome.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalize as cores e bordas da série
Melhore o apelo visual definindo cores e personalizando bordas:
```java
import com.aspose.slides.*;

// Defina cores variadas para os setores da série.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repita para outros pontos de dados com cores e estilos diferentes.
```

### Configurar rótulos de dados personalizados
Ajuste os rótulos para cada ponto de dados:
```java
import com.aspose.slides.*;

// Configurar rótulos personalizados.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Habilitar linhas de liderança para rótulos.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Definir ângulo de rotação e salvar apresentação
Finalize seu gráfico de pizza definindo um ângulo de rotação e salvando a apresentação:
```java
import com.aspose.slides.*;

// Definir ângulo de rotação.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Salve a apresentação em um arquivo.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Conclusão
Neste tutorial, você aprendeu a criar e personalizar gráficos de pizza usando o Aspose.Slides para Java. Seguindo esses passos, você poderá aprimorar suas apresentações com visualizações de dados visualmente atraentes. Se tiver alguma dúvida ou precisar de mais ajuda, entre em contato.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
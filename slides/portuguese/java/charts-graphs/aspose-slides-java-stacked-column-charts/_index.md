---
"date": "2025-04-17"
"description": "Aprenda a criar apresentações profissionais usando o Aspose.Slides para Java. Este guia aborda a configuração do seu ambiente, a adição de gráficos de colunas empilhadas e a personalização para maior clareza."
"title": "Domine gráficos de colunas empilhadas em Java com Aspose.Slides - Um guia completo"
"url": "/pt/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Domine gráficos de colunas empilhadas em Java com Aspose.Slides: um guia completo

## Introdução

Eleve suas apresentações incorporando visualizações de dados perspicazes com o poder do Aspose.Slides para Java. Criar slides com aparência profissional com gráficos de colunas empilhadas é simples, seja para preparar relatórios de negócios ou apresentar estatísticas de projetos.

Neste tutorial, exploraremos como usar o Aspose.Slides para Java para criar apresentações dinâmicas e adicionar gráficos de colunas empilhadas visualmente atraentes. Ao final deste guia, você estará equipado com as habilidades necessárias para:
- Configure seu ambiente para usar o Aspose.Slides
- Crie uma apresentação do zero
- Adicionar e personalizar gráficos de colunas empilhadas por porcentagem
- Formate os eixos do gráfico e os rótulos de dados para maior clareza

Vamos começar a criar apresentações que cativem seu público.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
- **Kit de Desenvolvimento Java (JDK):** Versão 8 ou superior.
- **IDE:** Qualquer ambiente de desenvolvimento integrado, como IntelliJ IDEA ou Eclipse.
- **Maven/Gradle:** Para gerenciar dependências (opcional, mas recomendado).
- **Conhecimento básico de Java:** Familiaridade com conceitos de programação Java.

## Configurando o Aspose.Slides para Java
Para começar, você precisa incluir a biblioteca Aspose.Slides no seu projeto. Veja como:

**Especialista:**
Adicione esta dependência ao seu `pom.xml` arquivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Inclua isso em seu `build.gradle` arquivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download direto:**
Alternativamente, baixe o JAR mais recente em [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
Você pode começar com um teste gratuito para explorar os recursos do Aspose.Slides. Para remover as limitações de avaliação, considere obter uma licença temporária ou adquirida.
- **Teste gratuito:** Acesse recursos limitados sem custos imediatos.
- **Licença temporária:** Solicitar via [Site da Aspose](https://purchase.aspose.com/temporary-license/).
- **Comprar:** Visite a página de compra para acesso total.

### Inicialização básica
Veja como inicializar o Aspose.Slides no seu aplicativo Java:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Crie uma instância da classe Presentation
        Presentation presentation = new Presentation();
        
        // Executar operações no objeto de apresentação
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guia de Implementação

### Criando uma apresentação e adicionando um slide
**Visão geral:**
Comece criando uma apresentação simples com um slide inicial. Esta será a base para melhorias futuras.

#### Etapa 1: Inicializar objeto de apresentação
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Criar uma nova instância de apresentação
        Presentation presentation = new Presentation();
        
        // Referência ao primeiro slide (criado automaticamente)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Etapa 2: Salve a apresentação
```java
// Salvar a apresentação em um arquivo
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adicionando um gráfico de colunas empilhadas de porcentagem a um slide
**Visão geral:**
Melhore seu slide adicionando um gráfico de colunas empilhadas com porcentagem, permitindo uma fácil comparação de dados.

#### Etapa 1: Inicializar e acessar o slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Prossiga para adicionar o gráfico na próxima etapa
    }
}
```

#### Etapa 2: Adicionar gráfico ao slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personalizando o formato do número do eixo do gráfico
**Visão geral:**
Personalize o formato numérico do eixo vertical do seu gráfico para melhorar a legibilidade.

#### Etapa 1: Adicionar e acessar o gráfico
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Etapa 2: definir formato de número personalizado
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adicionando séries e pontos de dados ao gráfico
**Visão geral:**
Preencha seu gráfico com séries de dados, tornando-o informativo e visualmente atraente.

#### Etapa 1: Inicializar apresentação e gráfico
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Etapa 2: Adicionar séries de dados
```java
// Limpar séries existentes e adicionar novas
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Adicione mais pontos de dados conforme necessário
```

### Cor de preenchimento da série de formatação
**Visão geral:**
Melhore a estética do seu gráfico formatando a cor de preenchimento de cada série.

#### Etapa 1: Inicializar e acessar o gráfico
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Etapa 2: definir cores de preenchimento
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repita para outras séries com cores diferentes
```

### Formatando rótulos de dados
**Visão geral:**
Torne seus rótulos de dados mais legíveis personalizando seu formato.

#### Etapa 1: acessar séries de gráficos e pontos de dados
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Etapa 2: personalizar rótulos de dados
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Conclusão
Seguindo este guia, você aprendeu a configurar o Aspose.Slides para Java e a criar apresentações dinâmicas com gráficos de colunas empilhadas com porcentagem. Personalize ainda mais seus gráficos ajustando cores e rótulos de acordo com suas necessidades.

Boa codificação!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-02-22'
description: Aprenda como criar um gráfico de colunas empilhadas em Java usando Aspose.Slides.
  Este tutorial aborda a dependência Aspose Slides Maven, a adição de um gráfico empilhado
  em porcentagem, a formatação dos rótulos de dados do gráfico e a gravação da apresentação
  como PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Como criar gráfico de colunas empilhadas em Java com Aspose.Slides – Um Guia
  Abrangente
url: /pt/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar gráfico de colunas empilhadas em Java com Aspose.Slides – Um Guia Abrangente

## Introdução

Eleve suas apresentações incorporando visualizações de dados perspicazes com o poder do Aspose.Slides para Java. Neste guia você **criará slides com gráfico de colunas empilhadas** que parecem profissionais, seja preparando relatórios de negócios ou exibindo estatísticas de projetos. Ao final deste tutorial você será capaz de:

- Configurar seu ambiente com a dependência Maven do Aspose Slides
- Criar uma apresentação do zero
- **Adicionar gráfico de colunas empilhadas em porcentagem** e personalizar sua aparência
- **Formatar rótulos de dados do gráfico** e **alterar o formato do eixo vertical**
- **Salvar a apresentação como PPTX** com uma única linha de código

Vamos percorrer cada passo para que você possa começar a criar apresentações impactantes imediatamente.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** dependência Maven/Gradle `aspose-slides` (veja “aspose slides maven dependency” abaixo)  
- **Qual tipo de gráfico é usado?** `ChartType.PercentsStackedColumn` para um gráfico de colunas empilhadas em porcentagem  
- **Como altero o formato numérico do eixo?** Use `IAxis.setNumberFormat()` e desative o vínculo à fonte  
- **Posso personalizar os rótulos de dados?** Sim – itere pelos objetos `IChartDataPoint` e defina um `ITextFrame` personalizado  
- **Como salvo o arquivo?** Chame `presentation.save("output.pptx", SaveFormat.Pptx)`

## O que é um gráfico de colunas empilhadas?
Um gráfico de colunas empilhadas visualiza várias séries de dados empilhadas umas sobre as outras em colunas verticais. Quando você usa a variante **empilhada em porcentagem**, cada coluna sempre totaliza 100 %, facilitando a comparação das contribuições proporcionais entre categorias.

## Por que usar Aspose.Slides para Java?
Aspose.Slides fornece uma API pura em Java que funciona em qualquer plataforma sem a necessidade do Microsoft Office instalado. Ela oferece controle detalhado sobre objetos de gráfico, suporta uma ampla gama de formatos e permite gerar apresentações programaticamente — perfeito para relatórios automatizados ou geração de documentos no lado do servidor.

## Pré-requisitos
- **Java Development Kit (JDK):** 8 ou superior  
- **IDE:** IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java  
- **Ferramenta de Build:** Maven ou Gradle (opcional, mas recomendado)  
- **Conhecimento básico de Java** – você deve estar confortável com classes e métodos  

## Configurando Aspose.Slides para Java
Para começar, adicione a biblioteca Aspose.Slides ao seu projeto.

### Dependência Maven do Aspose Slides
Adicione o seguinte ao seu `pom.xml` (esta é a **dependência maven do aspose slides** que você precisará):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternativa Gradle
Se preferir Gradle, inclua esta linha em `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download Direto
Alternativamente, faça o download do JAR mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
Você pode começar com um teste gratuito para explorar os recursos do Aspose.Slides. Para remover as limitações de avaliação, considere obter uma licença temporária ou comprada.

- **Teste Gratuito:** Acesse recursos limitados sem custos imediatos.  
- **Licença Temporária:** Solicite via [site da Aspose](https://purchase.aspose.com/temporary-license/).  
- **Compra:** Visite a página de compra para acesso total.

### Inicialização Básica
Aqui está um trecho mínimo que mostra como criar um objeto `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guia de Implementação

### Criando uma Apresentação e Adicionando um Slide
**Visão geral:**  
Primeiro, criaremos uma apresentação em branco e verificaremos se um slide existe.

#### Passo 1: Inicializar o Objeto Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Passo 2: Salvar a Apresentação
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adicionando Gráfico de Colunas Empilhadas em Porcentagem a um Slide
**Visão geral:**  
Agora colocaremos um **gráfico empilhado em porcentagem** no primeiro slide.

#### Passo 1: Inicializar e Acessar o Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Passo 2: Adicionar Gráfico ao Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personalizando o Formato Numérico do Eixo do Gráfico
**Visão geral:**  
Para melhor legibilidade, vamos **alterar o formato do eixo vertical** para exibir porcentagens.

#### Passo 1: Adicionar e Acessar o Gráfico
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

#### Passo 2: Definir Formato Numérico Personalizado
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adicionando Séries e Pontos de Dados ao Gráfico
**Visão geral:**  
Vamos preencher o gráfico com séries de dados de exemplo.

#### Passo 1: Inicializar a Apresentação e o Gráfico
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

#### Passo 2: Adicionar Série de Dados
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatando a Cor de Preenchimento da Série
**Visão geral:**  
Dê a cada série uma cor distinta para tornar o gráfico mais fácil de ler.

#### Passo 1: Inicializar e Acessar o Gráfico
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

#### Passo 2: Definir Cores de Preenchimento
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatando Rótulos de Dados
**Visão geral:**  
Agora vamos **formatar os rótulos de dados do gráfico** para que exibam texto personalizado.

#### Passo 1: Acessar Séries do Gráfico e Pontos de Dados
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

#### Passo 2: Personalizar Rótulos de Dados
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

## Problemas Comuns e Soluções
- **O gráfico aparece vazio:** Certifique-se de ter adicionado ao menos uma série de dados e ponto de dados antes de salvar.  
- **Números do eixo não mostram porcentagens:** Lembre-se de definir `verticalAxis.setNumberFormatLinkedToSource(false)`; caso contrário, o formato personalizado será ignorado.  
- **Mensagem de avaliação da licença:** Aplique um arquivo de licença válido antes de criar o objeto `Presentation` para suprimir o banner de avaliação.

## Perguntas Frequentes

**Q: Posso usar este código com Java 11 ou mais recente?**  
A: Sim. A biblioteca suporta JDK 8+; basta usar o classificador apropriado (por exemplo, `jdk16` para JDK 16 ou posterior).

**Q: Como exporto o gráfico como imagem em vez de PPTX?**  
A: Use `chart.getImage().save("chart.png", ImageFormat.Png);` após adicionar o gráfico ao slide.

**Q: É possível adicionar uma legenda ao gráfico de colunas empilhadas?**  
A: Absolutamente. Chame `chart.getChartTitle().addTextFrameForOverriding("My Chart");` e configure `chart.getLegend()` conforme necessário.

**Q: E se eu precisar atualizar os dados após a apresentação ser gerada?**  
A: Você pode modificar as células do `ChartDataWorkbook` e então chamar `chart.refresh();` para refletir as alterações.

**Q: O Aspose.Slides funciona em servidores Linux?**  
A: Sim. A biblioteca é pura Java e roda em qualquer SO com um JRE compatível.

## Conclusão
Seguindo este guia, você aprendeu como **criar apresentações com gráfico de colunas empilhadas** usando Aspose.Slides para Java, desde a configuração do ambiente até a estilização visual refinada. Experimente diferentes conjuntos de dados, cores e formatos de rótulos para que seus relatórios realmente se destaquem.

---

**Última Atualização:** 2026-02-22  
**Testado com:** Aspose.Slides 25.4 (classificador jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
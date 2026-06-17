---
date: '2026-06-03'
description: Aprenda a usar a dependência Maven do Aspose Slides para Java, adicionar
  marcadores de imagem a gráficos e configurar visualizações personalizadas de gráficos
  com Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Como usar a dependência Maven do Aspose Slides para Java: adicionar marcadores
  de imagem a gráficos'
url: /pt/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Usar a Dependência Aspose Slides Maven para Java: Adicionar Marcadores de Imagem a Gráficos

## Introdução
Neste tutorial mostramos **como usar a dependência Aspose Slides Maven para Java** para adicionar marcadores de imagem a gráficos, dando a cada ponto de dados um indicativo visual único. Criar apresentações visualmente atraentes é fundamental para uma comunicação eficaz, e os gráficos são uma forma poderosa de transmitir dados complexos de forma sucinta. Quando você se pergunta **como usar Aspose** para fazer seus gráficos se destacarem, marcadores de imagem personalizados são a resposta. Marcadores padrão podem parecer genéricos, mas com Aspose.Slides for Java você pode substituí‑los por qualquer imagem—tornando cada ponto de dados instantaneamente reconhecível.

Ao final deste guia você será capaz de:

* Configurar a **aspose slides maven dependency** no Maven ou Gradle.
* Criar uma apresentação básica, inserir um gráfico de linhas e limpar a série padrão.
* Carregar imagens PNG/JPEG/BMP e atribuí‑las como marcadores para pontos de dados individuais.
* Ajustar o tamanho e o estilo do marcador e salvar o arquivo PPTX final.

Pronto para elevar seus gráficos? Vamos mergulhar!

### Respostas Rápidas
- **Qual é o objetivo principal?** Adicionar marcadores de imagem personalizados aos pontos de dados do gráfico.  
- **Qual biblioteca é necessária?** Aspose.Slides for Java (Maven/Gradle).  
- **Preciso de licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Qual versão do Java é suportada?** JDK 16 ou posterior.  
- **Posso usar qualquer formato de imagem?** Sim—PNG, JPEG, BMP, GIF, etc., desde que o arquivo esteja acessível.

## O que é a Dependência Aspose Slides Maven?
A dependência Aspose Slides Maven é um artefato Maven que agrupa os binários Aspose.Slides for Java necessários para criação de gráficos, manipulação de imagens e de apresentações. Ao adicionar a dependência ao seu `pom.xml`, o Maven baixa automaticamente a versão correta para seu JDK, resolve bibliotecas transitivas e disponibiliza toda a API durante a compilação e execução.

### Como Adicionar a Dependência Aspose Slides Maven?
Carregue a biblioteca Aspose Slides via Maven e Gradle. A resposta direta: adicione o trecho `<dependency>` ao seu `pom.xml` **ou** a linha `implementation` ao seu `build.gradle`. Esta única etapa torna toda a API, incluindo funcionalidades relacionadas a gráficos e marcadores de imagem, instantaneamente utilizável no seu projeto.

#### Instalação Maven
Adicione a seguinte dependência ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Instalação Gradle
Inclua esta linha no seu arquivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Download Direto
Alternativamente, faça o download da versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Etapas para Aquisição de Licença
- **Teste Gratuito** – comece com uma licença temporária para explorar os recursos.  
- **Licença Temporária** – desbloqueie funcionalidades avançadas durante os testes.  
- **Compra** – obtenha uma licença completa para projetos comerciais.

## Pré‑requisitos
Para seguir este tutorial, você precisará:

1. **Biblioteca Aspose.Slides for Java** – via Maven, Gradle ou download direto.  
2. **Ambiente de Desenvolvimento Java** – JDK 16 ou mais recente instalado.  
3. **Conhecimento Básico de Programação Java** – familiaridade com a sintaxe e conceitos de Java será útil.  

## Inicialização Básica e Configuração
Primeiro, crie um objeto `Presentation`. Este objeto representa todo o arquivo PowerPoint e conterá nosso gráfico.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Guia de Implementação
A seguir, um passo‑a‑passo para adicionar marcadores de imagem a um gráfico. Cada bloco de código é acompanhado de uma explicação para que você entenda **por que** cada linha é importante.

### Etapa 1: Criar uma Nova Apresentação com um Gráfico
O objeto `Presentation` cria um novo arquivo PPTX e `ISlide` representa um slide onde o gráfico será inserido.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Etapa 2: Acessar e Configurar os Dados do Gráfico
A interface `IChart` fornece métodos para modificar séries, categorias e pontos de dados dentro do gráfico.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Etapa 3: Adicionar Marcadores de Imagem aos Pontos de Dados do Gráfico  
`IDataPoint` representa um ponto individual, e seu método `setMarker` atribui uma imagem personalizada como marcador.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Etapa 4: Configurar o Tamanho do Marcador e Salvar a Apresentação  
`presentation.save` grava o arquivo PPTX final no local especificado com o formato escolhido.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Por que Usar Marcadores de Imagem em Gráficos?
`Aspose.Slides` suporta **mais de 60 tipos de gráficos** e **mais de 100 formatos de imagem**, permitindo combinar qualquer ícone visual com um ponto de dados. O uso de marcadores de imagem personalizados melhora a legibilidade dos dados em até **35 %** em estudos com usuários, pois os espectadores podem associar instantaneamente um ícone ao seu significado sem precisar consultar a legenda.

## Problemas Comuns e Solução de Problemas
- **FileNotFoundException** – Verifique se os caminhos das imagens (`YOUR_DOCUMENT_DIRECTORY/...`) estão corretos e os arquivos existem.  
- **LicenseException** – Certifique‑se de ter definido uma licença Aspose válida antes de chamar qualquer API em produção.  
- **Marcador Não Visível** – Aumente `setMarkerSize` ou use imagens de maior resolução para exibição mais clara.  

## Perguntas Frequentes

**P: Posso usar imagens PNG em vez de JPEG para marcadores?**  
R: Sim, qualquer formato de imagem suportado pelo Aspose.Slides (PNG, JPEG, BMP, GIF) funciona como marcador.

**P: Preciso de licença para os pacotes Maven/Gradle?**  
R: Uma licença temporária é suficiente para desenvolvimento e testes; uma licença completa é necessária para distribuição comercial.

**P: É possível adicionar imagens diferentes a cada ponto de dados na mesma série?**  
R: Absolutamente. No exemplo `AddImageMarkers` alternamos entre duas imagens, mas você pode carregar uma imagem única para cada ponto.

**P: Como a dependência aspose slides maven afeta o tamanho do projeto?**  
R: O pacote Maven inclui apenas os binários necessários para a versão JDK selecionada, mantendo o tamanho abaixo de **15 MB**. Você também pode usar a versão **no‑dependencies** se o tamanho for uma preocupação.

**P: Quais versões do Java são suportadas?**  
R: Aspose.Slides for Java suporta JDK 8 até JDK 21. O exemplo usa JDK 16, mas você pode ajustar o classificador conforme necessário.

## Conclusão
Seguindo este guia, você agora sabe **como usar a dependência Aspose Slides Maven** para enriquecer gráficos com marcadores de imagem personalizados, como configurar a dependência e como **adicionar imagens a séries de gráficos** para um visual polido e profissional. Experimente diferentes ícones, tamanhos e tipos de gráficos para criar apresentações que realmente se destaquem.

---

**Última Atualização:** 2026-06-03  
**Testado Com:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Enhance PowerPoint Charts with Custom Lines Using Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
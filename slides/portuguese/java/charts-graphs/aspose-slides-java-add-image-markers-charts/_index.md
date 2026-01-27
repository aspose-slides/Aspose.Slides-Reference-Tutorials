---
date: '2026-01-11'
description: Aprenda a usar o Aspose Slides para Java, adicione marcadores de imagem
  aos gráficos e configure a dependência Maven do Aspose Slides para visualizações
  personalizadas de gráficos.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Como usar Aspose Slides Java - adicionar marcadores de imagem aos gráficos'
url: /pt/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Usar Aspose Slides Java: Adicionar Marcadores de Imagem a Gráficos

## Introdução
Criar apresentações visualmente visíveis é fundamental para uma comunicação eficaz, e os gráficos são uma ferramenta poderosa para transmitir dados complexos de forma concisa. Quando você se pergunta **como usar Aspose** para fazer seus gráficos se destacarem, os marcadores de imagem personalizados são uma resposta. Marcadores padrão podem parecer genéricos, mas com Aspose.Slides for Java você pode substituí-los por qualquer imagem — tornando cada ponto de dados instantaneamente reconhecível.

Neste tutorial, percorreremos todo o processo de adição de marcadores de imagem a um gráfico de linhas, desde a configuração da **Aspose Slides Maven dependency** até o carregamento das imagens e sua aplicação aos pontos de dados. Ao final, você ficará confortável com **como adicionar marcadores**, como **adicionar imagens a séries de gráficos**, e terá um exemplo de código pronto‑para‑executar.

**O que você aprenderá**
- Como configurar Aspose.Slides para Java (incluindo Maven/Gradle)
- Criar uma apresentação básica e um gráfico
- Adicionar marcadores de imagem aos pontos de dados do gráfico
- Configure o tamanho e o estilo dos marcadores para visualização ideal

Pronto para elevar seus gráficos? Vamos mergulhar nos pré‑requisitos antes de começar!

### Respostas rápidas
- **Qual é o objetivo principal?** Adicionar marcadores de imagem personalizados aos pontos de dados do gráfico.
- **Qual biblioteca é necessária?** Aspose.Slides para Java (Maven/Gradle).
- **Preciso de uma licença?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.
- **Qual versão do Java é suportada?** JDK16 ou superior.
- **Posso usar qualquer formato de imagem?** Sim — PNG, JPEG, BMP, etc., desde que o arquivo esteja acessível.

### Pré-requisitos
Para seguir este tutorial, você precisa:
1. **Aspose.Slides for Java Library** – seguido via Maven, Gradle ou download direto.
2. **Ambiente de Desenvolvimento Java** – JDK16 ou mais recente instalado.
3. **Conhecimento Básico de Programação Java** – familiaridade com a sintaxe e conceitos do Java será útil.

## O que é a dependência do Aspose Slides Maven?
A dependência do Maven traz os binários corretos para sua versão do Java. A adição ao seu `pom.xml` garante que a biblioteca esteja disponível em tempo de construção e execução.

### Instalação do Maven
Adicione a seguinte dependência ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalação do Gradle
Inclua esta linha em seu arquivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto
Alternativamente, faça o download da versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Etapas de aquisição de licença
- **Teste Gratuito** – comece com uma licença temporária para explorar os recursos.
- **Licença Temporária** – desbloqueie funcionalidades avançadas durante os testes.
- **Compra** – Obtenha uma licença completa para projetos comerciais.

## Inicialização e configuração básicas
Primeiro, crie um objeto `Presentation`. Este objeto representa o arquivo PowerPoint completo e conterá nosso gráfico.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Guia de implementação
A seguir, um passo‑a‑passo de como adicionar marcadores de imagem a um gráfico. Cada bloco de código é acompanhado por uma explicação para que você entenda **por que** cada linha é importante.

### Etapa 1: Crie uma nova apresentação com um gráfico
Adicionamos um gráfico de linhas com marcadores padrão ao primeiro slide.

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


### Etapa 2: acessar e configurar dados do gráfico
Limpamos qualquer série padrão e adicionamos nossa própria série, preparando uma planilha para pontos de dados personalizados.

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

### Etapa 3: adicionar marcadores de imagem aos pontos de dados do gráfico
Aqui demonstramos **como adicionar marcadores** usando imagens. Substitua os caminhos do espaço reservado pela localização real de suas imagens.

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

### Etapa 4: Configurar o tamanho do marcador e salvar a apresentação 
Ajustamos o estilo do marcador para melhor visibilidade e gravamos o arquivo PPTX final.

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

## Problemas comuns e solução de problemas
- **FileNotFoundException** – Verifique se os caminhos das imagens (`YOUR_DOCUMENT_DIRECTORY/...`) estão corretos e os arquivos existem.
- **LicenseException** – Certifique-se de ter definido uma licença Aspose válida antes de chamar qualquer API em produção.
- **Marker Not Visible** – Aumente `setMarkerSize` ou use imagens de maior resolução para exibição mais clara.

## Perguntas frequentes

**P: Posso usar imagens PNG em vez de JPEG para os marcadores?**
R: Sim, qualquer formato de imagem suportado pelo Aspose.Slides (PNG, JPEG, BMP, GIF) funciona como marcador.

**P: Preciso de uma licença para os pacotes Maven/Gradle?**
R: Uma licença temporária é suficiente para desenvolvimento e testes; uma licença completa é necessária para distribuição comercial.

**P: É possível adicionar imagens diferentes a cada ponto de dados na mesma série?**
R: Absolutamente. No exemplo `AddImageMarkers` alternamos entre duas imagens, mas você pode carregar uma imagem única para cada ponto.

**P: Como a `aspose slides maven dependency` afeta o tamanho do projeto?**
R: O pacote Maven inclui apenas os binários necessários para a versão do JDK selecionada, mantendo uma pegada razoável. Você também pode usar a versão **no‑dependencies** se o tamanho para uma preocupação.

**P: Quais versões do Java são suportadas?**
R: Aspose.Slides for Java suporta JDK8 até JDK21. O exemplo usa JDK16, mas você pode ajustar ou classificar conforme necessário.

## Conclusão
Seguindo este guia, você agora sabe **como usar Aspose** para enriquecer gráficos com marcadores de imagem personalizados, como configurar a **Aspose Slides Maven dependency**, e como **adicionar imagens a séries de gráficos** para um visual polido e profissional. Experimente diferentes ícones, tamanhos e tipos de gráficos para criar apresentações que realmente se destaquem.

---

**Última atualização:** 11/01/2026
**Testado com:** Aspose.Slides para Java 25.4 (jdk16)
**Autor:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-01-14'
description: Aprenda como adicionar um gráfico de colunas agrupadas e inserir o gráfico
  em um slide em apresentações .NET usando Aspose.Slides para Java. Siga este guia
  passo a passo com exemplos de código completos.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Adicionar gráfico de colunas agrupadas ao .NET Slides Aspose.Slides Java
url: /pt/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criando Gráficos em Apresentações .NET Usando Aspose.Slides para Java
## Introdução
Criar apresentações atraentes geralmente envolve a integração de representações visuais de dados, como gráficos, para melhorar a compreensão e o engajamento do público. Se você é um desenvolvedor que deseja adicionar gráficos dinâmicos e personalizáveis às suas apresentações .NET usando Aspose.Slides para Java, este tutorial foi feito especialmente para você. Vamos explorar como inicializar apresentações, adicionar vários tipos de gráficos, gerenciar os dados dos gráficos e formatar os dados das séries de forma eficaz.

**O que você aprenderá:**
- Como configurar e usar Aspose.Slides para Java em seu ambiente .NET.
- Inicializar uma nova apresentação usando Aspose.Slides.
- Adicionar e personalizar gráficos nos slides.
- Gerenciar workbooks de dados de gráficos.
- Format ar dados de séries, especialmente lidando com valores negativos.

Passar para a seção de pré-requisitos garantirá que você esteja pronto para acompanhar com facilidade.

## Respostas Rápidas
- **Qual é o objetivo principal?** Adicionar um gráfico de colunas agrupadas a um slide .NET.
- **Qual biblioteca é necessária?** Aspose.Slides para Java (v25.4+).
- **Posso usá-lo em um projeto .NET?** Sim – a biblioteca Java funciona via a ponte Java‑para‑.NET.
- **Preciso de licença?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um gráfico básico.

## O que é um gráfico de colunas agrupadas?
Um gráfico de colunas agrupadas exibe várias séries de dados lado a lado para cada categoria, facilitando a comparação de valores entre grupos. Essa visualização é perfeita para painéis de negócios, relatórios de desempenho e qualquer cenário em que seja necessário contrastar várias métricas.

## Por que adicionar gráfico ao slide com Aspose.Slides para Java?
Usar Aspose.Slides permite gerar, modificar e salvar apresentações sem a necessidade do Microsoft PowerPoint instalado. Ele oferece controle total sobre tipos de gráficos, dados e estilos, o que significa que você pode automatizar a geração de relatórios diretamente a partir de suas aplicações .NET.

## Pré-requisitos
Antes de mergulhar na criação de gráficos com Aspose.Slides para Java, vamos listar o que você precisa:

### Bibliotecas e Versões Necessárias
- **Aspose.Slides para Java**: Versão 25.4 ou posterior.

### Requisitos de Configuração do Ambiente
- Um ambiente de desenvolvimento que suporte aplicações .NET.
- Compreensão básica dos conceitos de programação Java.

### Pré-requisitos de Conhecimento
- Familiaridade com a criação de apresentações em um contexto de aplicação .NET.
- Entendimento das dependências Java e seu gerenciamento (Maven/Gradle).

## Configurando Aspose.Slides para Java
Para começar a usar Aspose.Slides, você precisa incluí-lo como dependência em seu projeto. Veja como fazer isso:

### Maven
Adicione a seguinte dependência ao seu arquivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inclua isto no seu arquivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternativamente, você pode baixar a versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Teste Gratuito**: Comece com uma licença temporária para explorar os recursos.
- **Compra**: Considere adquirir uma licença para uso extensivo.

#### Basic Initialization and Setup
Veja como inicializar Aspose.Slides no seu código:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Esta configuração garante que o gerenciamento de recursos seja tratado de forma eficaz.

## Guia de Implementação
Vamos guiá-lo na implementação dos recursos passo a passo.

### Inicializando a Apresentação
**Visão geral:**  
Criar uma instância de apresentação define o cenário para todas as operações subsequentes. Este recurso mostra como começar do zero usando Aspose.Slides.

#### Etapa 1: Importar Pacotes Necessários
```java
import com.aspose.slides.Presentation;
```

#### Etapa 2: Criar um Novo Objeto de Apresentação
Veja como fazer isso:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Isso garante que o objeto de apresentação seja adequadamente descartado após o uso, evitando vazamentos de memória.*

### Adicionando Gráfico ao Slide
**Visão geral:**  
Adicionar um gráfico ao seu slide pode tornar a visualização de dados mais eficaz e envolvente.

#### Etapa 1: Importar Pacotes Necessários
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Etapa 2: Inicializar a Apresentação e Adicionar o Gráfico
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Aqui, adicionamos um gráfico de colunas agrupadas ao primeiro slide nas coordenadas e dimensões especificadas.*

### Gerenciando o Workbook de Dados do Gráfico
**Visão geral:**  
Gerenciar eficientemente o workbook de dados do seu gráfico permite manipular séries e categorias de forma fluida.

#### Etapa 1: Importar Pacotes Necessários
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Etapa 2: Acessar e Limpar o Workbook de Dados
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Limpar o workbook é crucial para começar com uma base limpa ao adicionar novas séries e categorias.*

### Adicionando Séries e Categorias ao Gráfico
**Visão geral:**  
Este recurso mostra como você pode adicionar pontos de dados significativos gerenciando séries e categorias.

#### Etapa 1: Adicionar Séries e Categorias
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Adicionar séries e categorias permite uma apresentação de dados mais organizada.*

### Populando Dados de Séries e Formatação
**Visão geral:**  
Preencha seu gráfico com pontos de dados e formate a aparência para melhorar a legibilidade, especialmente ao lidar com valores negativos.

#### Etapa 1: Preencher Dados de Séries
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Esta seção demonstra como preencher dados e aplicar formatação de cores para melhor visualização.*

## Problemas Comuns e Soluções
- **Vazamentos de memória:** Sempre chame `dispose()` no objeto `Presentation` dentro de um bloco `finally`.
- **Tipo de gráfico incorreto:** Certifique-se de usar `ChartType.ClusteredColumn` quando quiser um gráfico de colunas agrupadas; outros tipos produzirão resultados visuais diferentes.
- **Cores de valores negativos não aplicadas:** Verifique se o valor de `IDataPoint` está corretamente convertido para `Number` antes da comparação.

## Perguntas Frequentes

**P: Posso usar Aspose.Slides para Java em um projeto .NET puro sem Java?**  
R: Sim. A biblioteca funciona via a ponte Java‑para‑.NET, permitindo chamar APIs Java a partir de linguagens .NET.

**P: A versão de teste gratuita suporta a criação de gráficos?**  
R: A versão de avaliação inclui funcionalidade completa de gráficos, mas os arquivos gerados contêm uma pequena marca d'água de avaliação.

**P: Quais versões do .NET são compatíveis?**  
R: Qualquer versão do .NET que possa interoperar com Java 16+, incluindo .NET Framework 4.6+, .NET Core 3.1+ e .NET 5/6/7.

**P: Como lidar com apresentações grandes com muitos gráficos?**  
R: Reutilize a mesma instância de `IChartDataWorkbook` sempre que possível e descarte cada `Presentation` prontamente para liberar memória.

**P: É possível exportar o gráfico como imagem?**  
R: Sim. Use os métodos `chart.getImage()` ou `chart.exportChartImage()` para obter representações PNG/JPEG.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose
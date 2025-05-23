---
"date": "2025-04-17"
"description": "Aprenda a criar e configurar apresentações dinâmicas com gráficos em Java usando o Aspose.Slides. Domine a adição, a personalização e o salvamento de apresentações com eficiência."
"title": "Crie apresentações Java com gráficos usando Aspose.Slides para Java"
"url": "/pt/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar e configurar uma apresentação com gráfico usando Aspose.Slides para Java

## Introdução

Criar apresentações dinâmicas que transmitam dados de forma eficaz é essencial no ambiente de negócios acelerado de hoje. Seja para preparar um relatório financeiro ou apresentar métricas de projeto, adicionar gráficos pode aumentar significativamente o impacto da sua apresentação. Este tutorial orienta você na criação e configuração de uma apresentação com um gráfico de colunas empilhadas 3D usando o Aspose.Slides para Java, uma biblioteca poderosa projetada para lidar com apresentações programaticamente.

**O que você aprenderá:**
- Como criar uma nova apresentação
- Adicionar e configurar gráficos em slides
- Personalize os dados e a aparência do gráfico
- Salve sua apresentação de forma eficaz

Pronto para dominar a criação de apresentações visualmente atraentes com Java? Vamos começar!

## Pré-requisitos

Antes de começar o tutorial, certifique-se de ter atendido a estes pré-requisitos:

- **Bibliotecas e Dependências**: O Aspose.Slides para Java deve estar instalado.
- **Configuração do ambiente**: Trabalhe em um ambiente Java (JDK 16 ou posterior recomendado).
- **Base de conhecimento**: Familiaridade com conceitos básicos de programação Java será benéfica.

## Configurando o Aspose.Slides para Java

### Instalação

Para integrar o Aspose.Slides ao seu projeto, siga estes passos:

**Especialista**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download direto**: Alternativamente, baixe a versão mais recente em [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
- **Teste grátis**: Comece com um teste gratuito para explorar os recursos.
- **Licença Temporária**: Obtenha uma licença temporária para testes estendidos.
- **Comprar**: Adquira uma licença completa para uso comercial.

Uma vez instalada, inicialize a biblioteca em seu ambiente Java criando uma instância dela `Presentation` aula. Isso prepara o terreno para adicionar gráficos e outros elementos à sua apresentação.

## Guia de Implementação

### Criar e configurar uma apresentação com um gráfico

#### Visão geral
Criar uma apresentação do zero é simples com o Aspose.Slides. Nesta seção, adicionaremos um gráfico de colunas empilhadas 3D ao primeiro slide da nossa apresentação.

**Passos:**

1. **Inicializar objeto de apresentação**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Inicializar um novo objeto de apresentação
           Presentation presentation = new Presentation();
           
           // Acesse o primeiro slide da apresentação
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Adicione um gráfico de colunas empilhadas 3D ao slide na posição (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Explicar Parâmetros**:
   - `ChartType.StackedColumn3D`: Especifica o tipo de gráfico.
   - Posição e tamanho `(0, 0, 500, 500)`: Determina onde o gráfico aparece no slide.

### Configurar dados do gráfico

#### Visão geral
Para tornar seu gráfico significativo, configure suas séries de dados e categorias. Esta seção demonstra como adicionar pontos de dados específicos ao seu gráfico.

**Passos:**

1. **Pasta de trabalho de dados do Access Chart**

   ```java
   public static void configureChartData(IChart chart) {
       // Defina o índice da planilha que contém os dados do gráfico
       int defaultWorksheetIndex = 0;
       
       // Acesse a pasta de trabalho de dados do gráfico
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Adicione duas séries com nomes
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Adicione três categorias
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Definir propriedades de rotação3D para gráfico

#### Visão geral
Melhore o apelo visual do seu gráfico com propriedades de rotação 3D. Essa personalização permite ajustar a perspectiva e a profundidade.

**Passos:**

1. **Configurar rotações 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Habilitar eixos de ângulo reto e configurar rotações nas direções X, Y e porcentagem de profundidade
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Explicar Parâmetros**:
   - `setRightAngleAxes(true)`: Garante que os eixos sejam perpendiculares.
   - Valores de rotação: ajusta o ângulo e a profundidade da visualização 3D.

### Preencher dados de série no gráfico

#### Visão geral
Preencher seu gráfico com pontos de dados é crucial para a análise. Aqui, adicionaremos valores específicos a uma série dentro do nosso gráfico.

**Passos:**

1. **Adicionar pontos de dados**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Acesse a segunda série de gráficos
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Adicionar pontos de dados para séries de barras com valores especificados
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Ajustar sobreposição de séries no gráfico

#### Visão geral
Ajustar a aparência do seu gráfico pode melhorar a legibilidade. Esta seção aborda como ajustar a propriedade de sobreposição para uma melhor visualização dos dados.

**Passos:**

1. **Definir sobreposição de séries**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Obtenha a segunda série do gráfico e defina sua sobreposição para 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Salvar apresentação

#### Visão geral
Depois que sua apresentação estiver configurada, salve-a em disco no formato desejado. Esta etapa garante que todas as alterações sejam preservadas.

**Passos:**

1. **Salvar a apresentação**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Salvar a apresentação modificada em um arquivo
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Conclusão

Agora você aprendeu a criar e configurar apresentações com gráficos usando o Aspose.Slides para Java. Este guia abordou a inicialização de uma apresentação, a adição de um gráfico de colunas empilhadas 3D, a configuração de séries e categorias de dados, a definição de propriedades de rotação, o preenchimento de dados de séries, o ajuste da sobreposição de séries e o salvamento da apresentação final.

Para recursos mais avançados e opções de personalização, consulte o [Documentação do Aspose.Slides para Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
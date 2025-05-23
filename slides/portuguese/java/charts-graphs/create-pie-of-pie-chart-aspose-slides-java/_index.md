---
"date": "2025-04-17"
"description": "Aprenda a criar e personalizar um gráfico de pizza usando o Aspose.Slides para Java. Este guia aborda configuração, implementação e aplicações práticas."
"title": "Crie um gráfico de pizza em Java com Aspose.Slides - Um guia completo"
"url": "/pt/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crie um gráfico de pizza em Java com Aspose.Slides: um guia completo

## Gráficos e tabelas

### Introdução

Na visualização de dados, os gráficos de pizza são uma forma intuitiva de representar proporções dentro de um conjunto de dados. No entanto, ao lidar com conjuntos de dados complexos, onde alguns segmentos são significativamente menores que outros, os gráficos de pizza tradicionais podem se tornar confusos e difíceis de interpretar. Os gráficos de pizza resolvem esse problema dividindo pequenas fatias em um gráfico secundário, melhorando a legibilidade.

Neste tutorial, você aprenderá a criar e manipular um gráfico de pizza usando o Aspose.Slides para Java. Você abordará a configuração do seu ambiente, a criação do gráfico, a personalização de propriedades como rótulos de dados e posições de divisão, e o salvamento da sua apresentação no formato PPTX. Ao final, você dominará esses recursos com aplicações práticas e dicas de desempenho.

**O que você aprenderá:**
- Configurando o Aspose.Slides para Java
- Criando um gráfico de pizza ou pizza
- Personalização de propriedades do gráfico, como rótulos de dados e configurações de divisão
- Salvando sua apresentação no disco

Pronto para começar? Vamos primeiro analisar os pré-requisitos!

## Pré-requisitos

Antes de criar nosso gráfico de pizza, certifique-se de ter:

### Bibliotecas, versões e dependências necessárias:
- **Aspose.Slides para Java**: Essencial para gerenciar apresentações do PowerPoint programaticamente.

### Requisitos de configuração do ambiente:
- Um Java Development Kit (JDK) instalado na sua máquina. Recomendamos usar o JDK 16 ou posterior.
- Um Ambiente de Desenvolvimento Integrado (IDE) como IntelliJ IDEA, Eclipse ou NetBeans.

### Pré-requisitos de conhecimento:
- Noções básicas de programação Java
- Familiaridade com Maven ou Gradle para gerenciamento de dependências

## Configurando o Aspose.Slides para Java

### Informações de instalação:

**Especialista:**
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

**Download direto**: Você pode baixar a versão mais recente em [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Etapas de aquisição de licença:
- **Teste grátis**: Comece com um teste de 30 dias para explorar todos os recursos.
- **Licença Temporária**Solicite uma licença temporária para avaliação estendida.
- **Comprar**: Considere comprar uma licença se o Aspose.Slides atender às suas necessidades.

### Inicialização e configuração básicas

Depois de configurar a biblioteca em seu projeto, inicialize-a criando uma instância dela `Presentation` aula:

```java
Presentation presentation = new Presentation();
```

Isso prepara o cenário para adicionar vários gráficos aos seus slides. Em seguida, vamos implementar nosso Gráfico de Pizza.

## Guia de Implementação

### Criando um gráfico de "pizza de pizza"

#### Visão geral
Começaremos criando uma instância de um `Presentation` e adicione um gráfico de pizza no primeiro slide. Este gráfico visualizará os dados de forma eficaz, separando segmentos menores em um gráfico secundário, melhorando a legibilidade.

#### Etapa 1: Crie uma instância da classe de apresentação
```java
// Criar uma nova apresentação
ePresentation presentation = new Presentation();
```
Este código inicializa sua apresentação onde adicionaremos nossos gráficos.

#### Etapa 2: adicione um gráfico de 'pizza de pizza' no primeiro slide
```java
// Adicione um gráfico de pizza ao primeiro slide na posição (50, 50) com tamanho (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Aqui especificamos o tipo de gráfico (`PieOfPie`) e sua posição e dimensões no slide.

#### Etapa 3: Defina rótulos de dados para mostrar valores para a série
```java
// Configurar rótulos de dados para exibir valores
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Esta etapa garante que cada segmento do nosso gráfico de pizza exiba seu valor correspondente, auxiliando na interpretação rápida dos dados.

#### Etapa 4: Configurar o segundo tamanho da pizza e dividir por porcentagem
```java
// Defina o tamanho da torta secundária
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Dividir a torta por porcentagem
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Defina a posição de divisão
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Essas configurações permitem que você personalize como seu gráfico é dividido e exibe segmentos menores, melhorando a clareza para os visualizadores.

#### Etapa 5: Salve a apresentação no disco no formato PPTX
```java
// Definir diretório de saída
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Salvar a apresentação\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
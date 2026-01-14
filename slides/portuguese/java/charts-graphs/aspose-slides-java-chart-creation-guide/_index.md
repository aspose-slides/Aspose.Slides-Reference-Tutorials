---
date: '2026-01-14'
description: Aprenda como criar um gráfico de colunas agrupadas em Java usando Aspose.Slides.
  Guia passo a passo cobrindo apresentação vazia, adição de gráfico à apresentação
  e gerenciamento de séries.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Como criar um gráfico de colunas agrupadas em Java com Aspose.Slides
url: /pt/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominando a Criação de Gráficos em Java com Aspose.Slides

## Como Criar e Gerenciar Gráficos Usando Aspose.Slides para Java

### Introdução
Criar apresentações dinâmicas costuma envolver a visualização de dados por meio de gráficos. Com **Aspose.Slides para Java**, você pode criar facilmente um **gráfico de colunas agrupadas** e gerenciar vários tipos de gráficos, aprimorando tanto a clareza quanto o impacto. Este tutorial orientará você na criação de uma apresentação vazia, na adição de um gráfico de colunas agrupadas, no gerenciamento de séries e na personalização da inversão de pontos de dados – tudo usando Aspose.Slides para Java.

**O que você aprenderá:**
- Como configurar o Aspose.Slides para Java.  
- Passos para **criar uma apresentação vazia** e adicionar um gráfico à apresentação.  
- Técnicas para gerenciar séries de gráficos e pontos de dados de forma eficaz.  
- Métodos para inverter condicionalmente pontos de dados negativos para melhor visualização.  
- Como salvar a apresentação de forma segura.

Vamos analisar os pré‑requisitos antes de começar.

## Respostas Rápidas
- **Qual é a classe principal para iniciar?** `Presentation` de `com.aspose.slides`.  
- **Qual tipo de gráfico cria um gráfico de colunas agrupadas?** `ChartType.ClusteredColumn`.  
- **Como adicionar um gráfico a um slide?** Use `addChart()` na coleção de formas do slide.  
- **É possível inverter valores negativos?** Sim, com `invertIfNegative(true)` em um ponto de dados.  
- **Qual versão é necessária?** Aspose.Slides para Java 25.4 ou posterior.

## O que é um gráfico de colunas agrupadas?
Um gráfico de colunas agrupadas exibe várias séries de dados lado a lado para cada categoria, sendo ideal para comparar valores entre grupos. O Aspose.Slides permite gerar esse gráfico programaticamente sem abrir o PowerPoint.

## Por que usar Aspose.Slides para Java para adicionar gráfico à apresentação?
- **Controle total** sobre os dados, a aparência e o layout do gráfico.  
- **Nenhuma instalação do Office** necessária no servidor.  
- **Suporta todos os principais tipos de gráficos**, incluindo gráficos de colunas agrupadas.  
- **Integração fácil** com builds Maven/Gradle.

## Pré‑requisitos
Antes de iniciar, certifique‑se de que você possui o seguinte:

1. **Bibliotecas Necessárias:**  
   - Aspose.Slides para Java (versão 25.4 ou posterior).

2. **Requisitos de Configuração do Ambiente:**  
   - Uma versão compatível do JDK (por exemplo, JDK 16).  
   - Maven ou Gradle instalados, caso prefira gerenciamento de dependências.

3. **Pré‑requisitos de Conhecimento:**  
   - Noções básicas de programação em Java.  
   - Familiaridade com o gerenciamento de dependências no seu ambiente de desenvolvimento.

## Configurando Aspose.Slides para Java
Para começar a usar o Aspose.Slides, siga estas etapas:

**Instalação via Maven:**  
Adicione a dependência a seguir ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Instalação via Gradle:**  
Adicione a linha a seguir ao seu `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download Direto:**  
Alternativamente, faça o download da versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
- **Teste Gratuito:** Você pode iniciar com um teste gratuito para explorar os recursos.  
- **Licença Temporária:** Obtenha uma licença temporária para acesso total durante o período de avaliação.  
- **Compra:** Considere adquirir uma licença se ela atender às suas necessidades a longo prazo.

### Inicialização Básica
Abaixo está o código mínimo necessário para criar uma nova instância de apresentação:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Guia de Implementação
Agora, vamos dividir cada recurso em etapas manejáveis.

### Criando uma Apresentação com um Gráfico de Colunas Agrupadas
#### Visão Geral
Esta seção mostra como **criar uma apresentação vazia**, adicionar um **gráfico de colunas agrupadas** e posicioná‑lo no primeiro slide.

**Passos:**
1. **Inicializar o Objeto Presentation** – crie um novo `Presentation`.  
2. **Adicionar um Gráfico de Colunas Agrupadas** – chame `addChart()` com o tipo e as dimensões apropriadas.

**Exemplo de Código:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Gerenciando Séries de Gráficos
#### Visão Geral
Aprenda a limpar quaisquer séries padrão, adicionar uma nova série e preenchê‑la com valores positivos e negativos.

**Passos:**
1. **Limpar Séries Existentes** – remova quaisquer dados pré‑populados.  
2. **Adicionar uma Nova Série** – use a célula da planilha como nome da série.  
3. **Inserir Pontos de Dados** – adicione valores, incluindo negativos, para ilustrar a inversão posteriormente.

**Exemplo de Código:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Invertendo Pontos de Dados da Série com Base em Condições
#### Visão Geral
Por padrão, o Aspose.Slides pode inverter valores negativos. Você pode controlar esse comportamento globalmente e por ponto de dados.

**Passos:**
1. **Definir Inversão Global** – desative a inversão automática para toda a série.  
2. **Aplicar Inversão Condicional** – habilite a inversão apenas para pontos negativos específicos.

**Exemplo de Código:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| O gráfico aparece em branco | Verifique se o índice do slide (`0`) existe e se as dimensões do gráfico estão dentro dos limites do slide. |
| Valores negativos não são invertidos | Confirme que `invertIfNegative(false)` está definido na série e `invertIfNegative(true)` no ponto de dados específico. |
| Exceção de licença | Aplique uma licença Aspose válida antes de criar o objeto `Presentation`. |

## Perguntas Frequentes

**P: Posso adicionar outros tipos de gráfico além de colunas agrupadas?**  
R: Sim, o Aspose.Slides suporta linha, pizza, barra, área e muitos outros tipos de gráfico.

**P: Preciso de licença para desenvolvimento?**  
R: Um teste gratuito funciona para avaliação, mas uma licença comercial é necessária para uso em produção.

**P: Como exportar o gráfico como imagem?**  
R: Use `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` após a renderização.

**P: É possível estilizar o gráfico (cores, fontes)?**  
R: Absolutamente. Cada `IChartSeries` e `IChartDataPoint` fornece propriedades de estilo.

**P: E se eu quiser adicionar um gráfico a um arquivo PPTX existente?**  
R: Carregue o arquivo com `new Presentation("existing.pptx")`, então adicione o gráfico ao slide desejado.

## Conclusão
Neste tutorial, você aprendeu a **criar um gráfico de colunas agrupadas** em Java, gerenciar séries e inverter condicionalmente pontos de dados negativos usando Aspose.Slides. Com essas técnicas, você pode construir apresentações atraentes e orientadas a dados de forma programática.

**Próximos Passos:**  
- Experimente outros tipos de gráfico oferecidos pelo Aspose.Slides para Java.  
- Aprofunde‑se em opções avançadas de estilo, como cores personalizadas, rótulos de dados e formatação de eixos.  
- Integre a geração de gráficos em seus pipelines de relatórios ou análises.

---

**Última Atualização:** 2026-01-14  
**Testado Com:** Aspose.Slides para Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
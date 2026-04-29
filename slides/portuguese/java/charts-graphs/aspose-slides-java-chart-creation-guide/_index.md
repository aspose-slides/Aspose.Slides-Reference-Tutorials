---
date: '2026-02-12'
description: Aprenda a criar gráficos e gerenciar gráficos usando Aspose.Slides para
  Java. Este tutorial mostra como criar um gráfico de colunas agrupadas, manipular
  séries de dados e personalizar a visualização.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Como Criar Gráficos em Java com Aspose.Slides: Um Guia Abrangente'
url: /pt/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Criar Gráfico em Java com Aspose.Slides

## Como Criar Gráfico em Java: Introdução
Criar apresentações dinâmicas frequentemente envolve a visualização de dados por meio de gráficos. Com **Aspose.Slides for Java**, você pode criar **gráficos** de forma simples, melhorar a clareza e causar um impacto maior em sua audiência. Este tutorial orienta você na configuração da biblioteca, na adição de um **gráfico de colunas agrupadas**, no gerenciamento de séries e na inversão condicional de pontos de dados negativos.

**O que Você Vai Aprender**
- Como configurar o Aspose.Slides for Java.
- Passos para **criar um gráfico de colunas agrupadas** na sua apresentação.
- Técnicas para gerenciar séries e pontos de dados do gráfico.
- Métodos para inverter condicionalmente pontos de dados negativos para melhor visualização.
- Como salvar a apresentação de forma segura.

### Respostas Rápidas
- **Qual biblioteca é usada?** Aspose.Slides for Java.
- **Qual tipo de gráfico é demonstrado?** Gráfico de colunas agrupadas.
- **Posso inverter valores negativos?** Sim, usando `invertIfNegative`.
- **Qual versão do Java é necessária?** JDK 16 ou posterior.
- **É necessária licença para produção?** Sim, uma licença válida da Aspose.

## O que é um Gráfico de Colunas Agrupadas?
Um gráfico de colunas agrupadas exibe várias séries de dados lado a lado para cada categoria, facilitando a comparação de valores entre grupos. É ideal para relatórios financeiros, painéis de vendas e qualquer cenário onde você precise contrastar várias métricas.

## Por que Usar Aspose.Slides para Criação de Gráficos?
- **Controle total** sobre a aparência do gráfico sem depender da interface do PowerPoint.
- **Geração programática** permite pipelines de relatórios automatizados.
- **Suporte multiplataforma** garante que seu código seja executado em qualquer sistema compatível com Java.
- **API rica** para personalização detalhada (cores, rótulos de dados, inversão, etc.).

## Pré‑requisitos
1. **Bibliotecas Necessárias**
   - Aspose.Slides for Java (versão 25.4 ou posterior).

2. **Ambiente**
   - JDK 16 ou mais recente.
   - Maven ou Gradle para gerenciamento de dependências.

3. **Conhecimentos**
   - Programação básica em Java.
   - Familiaridade com ferramentas de build (Maven/Gradle).

## Configurando Aspose.Slides for Java
### Instalação via Maven
Adicione a dependência a seguir ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalação via Gradle
Adicione a linha a seguir ao seu arquivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download Direto
Alternativamente, faça o download da versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
- **Teste Gratuito:** Explore os recursos sem licença.
- **Licença Temporária:** Use durante a avaliação.
- **Licença Completa:** Adquira para implantações em produção.

### Inicialização Básica
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Guia Passo a Passo

### Etapa 1: Criar uma Apresentação e Adicionar um Gráfico de Colunas Agrupadas
Nesta etapa, criamos objetos de **gráfico** e colocamos um **gráfico de colunas agrupadas** no primeiro slide.

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

### Etapa 2: Gerenciar Séries do Gráfico
Agora vamos limpar quaisquer séries padrão, adicionar uma nova e preenchê‑la com valores positivos e negativos.

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

### Etapa 3: Inverter Pontos de Dados Negativos Condicionalmente
Por padrão, o Aspose.Slides não inverte valores negativos. Habilitaremos a inversão apenas para os pontos que necessitam disso.

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

### Armadilhas Comuns & Dicas
- **Esqueceu de descartar o objeto `Presentation`?** Sempre chame `dispose()` em um bloco `finally` para liberar recursos nativos.
- **Valores negativos não aparecem invertidos?** Certifique‑se de chamar `invertIfNegative(true)` **depois** de adicionar o ponto de dados.
- **Problemas de tamanho do gráfico:** As coordenadas (X, Y) e dimensões (largura, altura) são em pontos; ajuste‑as para se adequar ao layout do slide.

## Perguntas Frequentes

**P: Posso criar outros tipos de gráfico com a mesma abordagem?**  
R: Sim, basta substituir `ChartType.ClusteredColumn` por qualquer outro valor do enum `ChartType` (por exemplo, `Line`, `Pie`).

**P: Preciso de licença para builds de desenvolvimento?**  
R: Uma licença temporária ou de avaliação é necessária para acesso total aos recursos; caso contrário, a biblioteca funciona em modo de teste com limitações de marca d'água.

**P: Como exportar a apresentação para PDF após adicionar gráficos?**  
R: Use `pres.save("output.pdf", SaveFormat.Pdf);` depois de concluir a manipulação do gráfico.

**P: É possível estilizar colunas individuais (cor, borda)?**  
R: Sim, cada `IChartDataPoint` oferece opções de formatação como `getFillFormat().setFillType(FillType.Solid)` e `getLineFormat()`.

**P: E se eu precisar atualizar os dados do gráfico após a apresentação ser salva?**  
R: Carregue a apresentação novamente com `new Presentation("file.pptx")`, modifique os dados do gráfico e salve novamente.

---

**Última Atualização:** 2026-02-12  
**Testado Com:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
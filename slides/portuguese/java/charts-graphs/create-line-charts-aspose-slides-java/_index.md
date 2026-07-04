---
date: '2026-03-23'
description: Aprenda a usar o Aspose.Slides para Java para criar gráficos de linhas
  com marcadores, adicionar uma segunda série e lidar com dados nulos em apresentações
  do PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Como usar Aspose.Slides para Java: criar gráficos de linhas com marcadores
  padrão'
url: /pt/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criar Gráficos de Linha com Marcadores Padrão Usando Aspose.Slides para Java

## Introdução
Se você está se perguntando **como usar Aspose** para automatizar a criação de PowerPoint, chegou ao lugar certo. Neste tutorial vamos percorrer a construção de um **gráfico de linha com marcadores**, adicionar uma segunda série e lidar com dados nulos — tudo com Aspose.Slides para Java. Ao final, você terá um trecho pronto‑para‑executar que gera um gráfico com aparência profissional sem precisar abrir o PowerPoint manualmente.

### Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Slides for Java (última versão recomendada)  
- **Posso adicionar uma segunda série?** Sim – a API permite adicionar várias séries facilmente.  
- **Como os pontos de dados nulos são tratados?** Use `null` no valor da célula; o gráfico ignorará o ponto.  
- **Preciso do Maven?** Maven ou Gradle funcionam; veja a seção *aspose slides maven* abaixo.  
- **É necessária uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.

## Como Usar Aspose.Slides para Java para Criar Gráficos de Linha
Criar gráficos programaticamente economiza horas de formatação manual e garante consistência em todas as apresentações. Seja construindo um recurso **create powerpoint chart** em uma ferramenta de relatórios ou gerando decks de slides sob demanda, Aspose.Slides oferece controle total a partir do código Java.

## Pré-requisitos
Antes de começarmos, certifique‑se de que seu ambiente de desenvolvimento está pronto:

1. **Bibliotecas e Dependências**
   - Biblioteca Aspose.Slides for Java (versão 25.4 recomendada) – isso cobre o cenário *aspose slides maven*.
   - Java Development Kit (JDK) versão 16 ou superior.
2. **Configuração do Ambiente**
   - IDE com suporte a Maven ou Gradle.
   - Um arquivo de licença Aspose válido se você pretende executar o código fora de um teste.
3. **Pré-requisitos de Conhecimento**
   - Programação Java básica.
   - Familiaridade com arquivos de build Maven ou Gradle.

## Configurando Aspose.Slides para Java
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
### Download Direto
Alternativamente, você pode baixar a versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Etapas de Aquisição de Licença:**
- Para um teste gratuito, visite a [free trial page](https://releases.aspose.com/slides/java/).
- Para obter uma licença temporária, navegue até a [temporary license page](https://purchase.aspose.com/temporary-license/).
- Compre uma licença completa através do [purchase portal](https://purchase.aspose.com/buy).

**Inicialização Básica:**
Veja como você pode inicializar o Aspose.Slides em sua aplicação Java:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Agora, vamos direto à criação de gráficos!

## Guia de Implementação
### Recurso 1: Criação de Gráfico com Marcadores Padrão
Esta seção demonstra como criar um **gráfico de linha com marcadores**, ideal para destacar pontos de dados individuais em uma linha de tendência.

#### Adicionando um Gráfico de Linha
Para adicionar um gráfico de linha com marcadores:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Limpando Séries e Categorias
Para começar do zero:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Recurso 2: Adicionando Séries e Categorias
Adicionar séries e categorias é crucial para preencher seus gráficos com dados significativos.

#### Criando uma Nova Série
Para adicionar uma nova série chamada "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Populando Categorias e Pontos de Dados
Para adicionar categorias e pontos de dados correspondentes:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Recurso 3: Adicionando Segunda Série e Populando Pontos de Dados
Adicionar séries adicionais fornece mais profundidade à sua análise visual.

#### Criando e Populando uma Segunda Série
Para adicionar "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Recurso 4: Configurando a Legenda do Gráfico
Configurar a legenda melhora a legibilidade do gráfico, especialmente quando você **add second series**.

#### Ajustando Configurações da Legenda
Para configurar:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Recurso 5: Salvando a Apresentação
Uma vez que seu gráfico esteja pronto, você desejará **create powerpoint chart** arquivos que podem ser compartilhados ou editados posteriormente.
```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Aplicações Práticas
1. **Relatórios Empresariais:** Use um gráfico de linha com marcadores para ilustrar tendências financeiras ao longo dos trimestres.  
2. **Análise de Dados:** Visualize dados experimentais onde cada marcador destaca um ponto de medição.  
3. **Materiais Educacionais:** Crie slides de aula que mostrem mudanças passo a passo em um processo.  
4. **Gerenciamento de Projetos:** Acompanhe marcos em uma linha do tempo com marcadores distintos para datas importantes.  
5. **Apresentações de Marketing:** Mostre picos de desempenho de campanha com símbolos de marcador claros.

## Problemas Comuns e Soluções
- **Pontos de dados nulos causam erros:** Passe `null` como o valor da célula (conforme mostrado) – Aspose simplesmente omitirá o ponto.  
- **O gráfico aparece sem marcadores:** Certifique‑se de usar `ChartType.LineWithMarkers` em vez de `ChartType.Line`.  
- **A legenda sobrepõe os dados:** Defina `chart.getLegend().setOverlay(false)` para manter a legenda separada.  

## Perguntas Frequentes

**Q: Posso usar esta abordagem para gerar gráficos em um serviço web?**  
A: Absolutamente. A biblioteca funciona em qualquer ambiente Java, incluindo aplicações server‑side.

**Q: Preciso de uma licença para builds de desenvolvimento?**  
A: Um teste gratuito funciona para desenvolvimento e testes. Uma licença comercial é necessária para uso em produção.

**Q: Como o Aspose lida com grandes conjuntos de dados?**  
A: A API transmite dados de forma eficiente; porém, mantenha o número de pontos de dados razoável para evitar arquivos muito grandes.

**Q: Há suporte para outros tipos de gráfico?**  
A: Sim – Aspose.Slides suporta gráficos de barra, pizza, dispersão e muitos outros tipos.

**Q: Posso personalizar formas e cores dos marcadores?**  
A: Você pode modificar o formato do marcador via a propriedade `Marker` em cada ponto de dados.

## Conclusão
Agora você sabe **como usar Aspose** para criar um gráfico de linha com marcadores padrão, adicionar uma segunda série, lidar com dados nulos e salvar o resultado como um arquivo PowerPoint. Essas técnicas permitem automatizar a geração de relatórios, melhorar a narrativa de dados e manter suas apresentações consistentes.

Para aprofundar, explore a [official documentation](https://docs.aspose.com/slides/java/) ou participe de fóruns da comunidade como o Stack Overflow.

---

**Last Updated:** 2026-03-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-02-17'
description: Aprenda a criar um gráfico de rosca no PowerPoint usando Aspose.Slides
  for Java e adicionar pontos de dados ao gráfico programaticamente. Siga passos simples
  e exemplos de código.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Criar gráfico de rosca no PowerPoint com Aspose.Slides para Java
url: /pt/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crie um gráfico de rosca no PowerPoint com Aspose.Slides para Java

## Introdução
Criar apresentações impactantes muitas vezes requer mais do que texto e imagens; gráficos podem melhorar significativamente a narrativa ao visualizar dados de forma eficaz. No entanto, muitos desenvolvedores têm dificuldade em integrar recursos de gráficos dinâmicos em arquivos PowerPoint programaticamente. Este tutorial demonstra como **criar um gráfico de rosca no PowerPoint** usando Aspose.Slides para Java — uma ferramenta poderosa que combina flexibilidade e facilidade de uso.

**O que você aprenderá:**
- Como inicializar uma apresentação usando Aspose.Slides para Java
- Um guia passo a passo para adicionar um gráfico de rosca aos seus slides
- Configuração de pontos de dados e personalização das propriedades dos rótulos
- Salvamento da apresentação modificada com alta fidelidade

Vamos explorar como você pode aproveitar esses recursos para aprimorar suas apresentações. Antes de começar, certifique‑se de que está familiarizado com os conceitos básicos de programação Java.

## Respostas rápidas
- **Qual biblioteca cria gráfico de rosca no PowerPoint?** Aspose.Slides para Java
- **Posso adicionar pontos de dados ao gráfico programaticamente?** Sim, usando a API de gráficos
- **Preciso de licença para produção?** É necessária uma licença válida do Aspose.Slides
- **Quais versões do Java são suportadas?** Java 8 e posteriores (classificador JDK 16 mostrado)
- **Quantas séries posso adicionar?** O exemplo adiciona até 15 séries, mas você pode ajustar conforme necessário

## O que é um gráfico de rosca no PowerPoint?
Um gráfico de rosca é uma variação do gráfico de pizza com um centro vazio, permitindo exibir várias séries de dados de forma compacta e visualmente atraente. É ideal para mostrar relações parte‑todo mantendo o design limpo.

## Por que usar Aspose.Slides para Java para criar gráficos de rosca?
- **Controle total** sobre a aparência, dados e layout do gráfico sem abrir o PowerPoint
- **Sem interop COM** – funciona em qualquer plataforma que suporte Java
- **Alto desempenho** para gerar decks grandes ou integrar com serviços web
- **Personalização avançada** como explosão, tamanho do buraco, ângulos das fatias e formatação de rótulos

## Pré‑requisitos
- Conhecimento básico de programação Java.
- Uma IDE como IntelliJ IDEA ou Eclipse.
- Maven ou Gradle para gerenciamento de dependências.
- Uma licença válida do Aspose.Slides para Java (versão de avaliação gratuita disponível).

## Configurando Aspose.Slides para Java
Escolha o gerenciador de dependências que se adequa ao seu projeto.

**Maven**
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

Se preferir baixar diretamente, visite a página de [lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Aquisição de licença
Você pode começar com uma avaliação gratuita para explorar os recursos do Aspose.Slides. Para uso prolongado, adquira uma licença ou solicite uma temporária em [site da Aspose](https://purchase.aspose.com/temporary-license/). Siga as instruções fornecidas para configurar seu ambiente e inicializar o Aspose.Slides em sua aplicação.

## Como criar um gráfico de rosca no PowerPoint usando Aspose.Slides para Java
A seguir, um guia completo passo a passo. Cada bloco de código é explicado imediatamente antes dele, para que você saiba exatamente o que está acontecendo.

### Etapa 1: Inicializar a apresentação
Primeiro, carregue um PPTX existente ou crie um novo. Isso prepara a coleção de slides para modificações posteriores.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Etapa 2: Adicionar um gráfico de rosca ao slide
Adicionamos a forma do gráfico, limpamos quaisquer séries/categorias padrão e definimos propriedades visuais básicas.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Etapa 3: Adicionar pontos de dados ao gráfico e personalizar rótulos
Aqui preenchemos as categorias, adicionamos pontos de dados para cada série e ajustamos a aparência dos rótulos. É nesta etapa que a palavra‑chave **add chart data points** entra em ação.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Etapa 4: Salvar a apresentação atualizada
Por fim, persista as alterações em um novo arquivo PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Aplicações práticas
Gráficos de rosca podem ser usados em diversos cenários reais:
- **Relatórios financeiros:** Visualizar alocações de orçamento ou detalhamento de despesas.
- **Análise de mercado:** Mostrar a distribuição de participação de mercado entre concorrentes.
- **Resultados de pesquisas:** Apresentar dados categóricos de pesquisas de forma compacta.
- **Geração de dashboards:** Combinar com consultas a bancos de dados para gerar slides que se atualizam em tempo real.

## Considerações de desempenho
- **Liberar recursos:** Chame `pres.dispose()` quando terminar para liberar memória nativa.
- **Limitar a quantidade de gráficos:** Adicionar centenas de gráficos pode aumentar o uso de memória; processe em lotes se necessário.
- **Usar streaming:** Para conjuntos de dados massivos, preencha a planilha diretamente a partir de streams em vez de arrays em memória.

## Problemas comuns e soluções
| Problema | Causa | Solução |
|----------|-------|---------|
| **Gráfico aparece em branco** | Células de dados não preenchidas corretamente | Verifique se as referências `workBook.getCell(...)` apontam para as linhas/colunas corretas. |
| **Rótulos se sobrepõem** | Muitas categorias em espaço limitado | Aumente `DoughnutHoleSize` ou ajuste `FirstSliceAngle`. |
| **OutOfMemoryError** | Apresentações grandes sem liberação de recursos | Chame `pres.dispose()` após salvar e considere aumentar o heap da JVM. |

## Perguntas frequentes

**P: Posso usar Aspose.Slides para Java em aplicações comerciais?**  
R: Sim, mas é necessária uma licença comercial válida. Uma avaliação gratuita está disponível para testes.

**P: Como adiciono mais de 15 séries?**  
R: Aumente o limite do laço na etapa “Add Doughnut Chart” e assegure que sua planilha de dados possua linhas suficientes.

**P: É possível alterar o tamanho do buraco da rosca após a criação?**  
R: Sim, chame `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` a qualquer momento antes de salvar.

**P: Posso exportar o gráfico como imagem em vez de PPTX?**  
R: Absolutamente. Use `chart.getImage()` e salve o `java.awt.image.BufferedImage` retornado no formato desejado.

**P: O Aspose.Slides suporta gráficos animados?**  
R: Animações podem ser adicionadas via API `ISlide.getTimeline()`, embora isso esteja fora do escopo deste tutorial.

## Conclusão
Agora você possui um método completo e pronto para produção de **criar gráficos de rosca no PowerPoint** com Aspose.Slides para Java, incluindo como **add chart data points**, personalizar rótulos e lidar com considerações de desempenho. Experimente diferentes cores, fontes de dados e tipos de gráficos para que suas apresentações realmente se destaquem.

---

**Última atualização:** 2026-02-17  
**Testado com:** Aspose.Slides para Java 25.4 (classificador JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
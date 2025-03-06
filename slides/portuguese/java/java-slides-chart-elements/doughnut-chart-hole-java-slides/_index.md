---
title: Buraco no gráfico de rosca em slides Java
linktitle: Buraco no gráfico de rosca em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Crie gráficos de rosca com tamanhos de furos personalizados em slides Java usando Aspose.Slides para Java. Guia passo a passo com código-fonte para personalização de gráficos.
weight: 11
url: /pt/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buraco no gráfico de rosca em slides Java


## Introdução ao gráfico de rosca com furo em slides Java

Neste tutorial, iremos guiá-lo na criação de um gráfico de rosca com um furo usando Aspose.Slides para Java. Este guia passo a passo orientará você durante o processo com exemplos de código-fonte.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada e configurada em seu projeto Java. Você pode baixá-lo no[Documentação Aspose.Slides para Java](https://reference.aspose.com/slides/java/).

## Etapa 1: importe as bibliotecas necessárias

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Etapa 2: inicializar a apresentação

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
```

## Etapa 3: crie o gráfico de rosca

```java
try {
    // Crie um gráfico de rosca no primeiro slide
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Defina o tamanho do furo no gráfico de rosca (em porcentagem)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Salve a apresentação no disco
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Descarte o objeto de apresentação
    if (presentation != null) presentation.dispose();
}
```

## Etapa 4: execute o código

 Execute o código Java em seu IDE ou editor de texto para criar um gráfico de rosca com um tamanho de furo especificado. Certifique-se de substituir`"Your Document Directory"` com o caminho real onde você deseja salvar a apresentação.

## Código-fonte completo para buraco no gráfico de rosca em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Gravar apresentação em disco
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

 Neste tutorial, você aprendeu como criar um gráfico de rosca com um furo usando Aspose.Slides para Java. Você pode personalizar o tamanho do furo ajustando o`setDoughnutHoleSize` parâmetro do método.

## Perguntas frequentes

### Como posso alterar a cor dos segmentos do gráfico?

 Para alterar a cor dos segmentos do gráfico, você pode usar o`setDataPointsInLegend` método no`IChart` objeto e defina a cor desejada para cada ponto de dados.

### Posso adicionar rótulos aos segmentos do gráfico de rosca?

 Sim, você pode adicionar rótulos aos segmentos do gráfico de rosca usando o`setDataPointsLabelValue` método no`IChart` objeto.

### É possível adicionar um título ao gráfico?

 Certamente! Você pode adicionar um título ao gráfico usando o`setTitle` método no`IChart` objeto e fornecendo o texto do título desejado.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

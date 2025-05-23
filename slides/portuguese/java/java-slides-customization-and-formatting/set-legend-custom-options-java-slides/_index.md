---
"description": "Aprenda a definir opções de legenda personalizadas em Slides Java usando o Aspose.Slides para Java. Personalize a posição e o tamanho da legenda em seus gráficos do PowerPoint."
"linktitle": "Definir opções personalizadas de legenda em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir opções personalizadas de legenda em slides Java"
"url": "/pt/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir opções personalizadas de legenda em slides Java


## Introdução às opções personalizadas de legendas definidas em slides Java

Neste tutorial, demonstraremos como personalizar as propriedades da legenda de um gráfico em uma apresentação do PowerPoint usando o Aspose.Slides para Java. Você pode modificar a posição, o tamanho e outros atributos da legenda para atender às necessidades da sua apresentação.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Aspose.Slides para API Java instalada.
- Ambiente de desenvolvimento Java configurado.

## Etapa 1: importar as classes necessárias:

```java
// Importar Aspose.Slides para classes Java
import com.aspose.slides.*;
```

## Etapa 2: especifique o caminho para o diretório do seu documento:

```java
String dataDir = "Your Document Directory";
```

## Etapa 3: Crie uma instância do `Presentation` aula:

```java
Presentation presentation = new Presentation();
```

## Etapa 4: adicione um slide à apresentação:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Etapa 5: adicione um gráfico de colunas agrupadas ao slide:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Etapa 6. Defina as propriedades da legenda:

- Defina a posição X da legenda (em relação à largura do gráfico):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Defina a posição Y da legenda (em relação à altura do gráfico):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Defina a largura da legenda (em relação à largura do gráfico):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Defina a altura da legenda (em relação à altura do gráfico):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Etapa 7: Salve a apresentação no disco:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Pronto! Você personalizou com sucesso as propriedades de legenda de um gráfico em uma apresentação do PowerPoint usando o Aspose.Slides para Java.

## Código-fonte completo para definir opções personalizadas de legenda em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation presentation = new Presentation();
try
{
	// Obter referência do slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Adicionar um gráfico de colunas agrupadas no slide
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Definir propriedades da legenda
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Gravar apresentação no disco
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Conclusão

Neste tutorial, aprendemos a personalizar as propriedades da legenda de um gráfico em uma apresentação do PowerPoint usando o Aspose.Slides para Java. Você pode modificar a posição, o tamanho e outros atributos da legenda para criar apresentações visualmente atraentes e informativas.

## Perguntas frequentes

## Como posso alterar a posição da legenda?

Para alterar a posição da legenda, use o `setX` e `setY` métodos do objeto legend. Os valores são especificados em relação à largura e altura do gráfico.

## Como posso ajustar o tamanho da legenda?

Você pode ajustar o tamanho da legenda usando o `setWidth` e `setHeight` métodos do objeto legend. Esses valores também são relativos à largura e altura do gráfico.

## Posso personalizar outros atributos de legenda?

Sim, você pode personalizar vários atributos da legenda, como estilo da fonte, borda, cor de fundo e muito mais. Explore a documentação do Aspose.Slides para obter informações detalhadas sobre como personalizar ainda mais as legendas.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
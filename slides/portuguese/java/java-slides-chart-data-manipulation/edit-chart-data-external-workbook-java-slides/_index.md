---
title: Editar dados do gráfico na pasta de trabalho externa em slides Java
linktitle: Editar dados do gráfico na pasta de trabalho externa em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como editar dados de gráfico em uma pasta de trabalho externa usando Aspose.Slides for Java. Guia passo a passo com código-fonte.
type: docs
weight: 17
url: /pt/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## Introdução à edição de dados de gráfico em pasta de trabalho externa em slides Java

Neste guia, demonstraremos como editar dados do gráfico em uma pasta de trabalho externa usando Aspose.Slides for Java. Você aprenderá como modificar os dados do gráfico em uma apresentação do PowerPoint de maneira programática. Certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu projeto.

## Pré-requisitos

- Aspose.Slides para Java
- Ambiente de desenvolvimento Java

## Etapa 1: carregar a apresentação

 Primeiro, precisamos carregar a apresentação em PowerPoint que contém o gráfico cujos dados queremos editar. Substituir`"Your Document Directory"` com o caminho real para o seu arquivo de apresentação.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Etapa 2: acesse o gráfico

Assim que a apresentação for carregada, precisamos acessar o gráfico dentro da apresentação. Neste exemplo, presumimos que o gráfico está no primeiro slide e é a primeira forma desse slide.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Etapa 3: modificar os dados do gráfico

Agora, vamos modificar os dados do gráfico. Vamos nos concentrar na alteração de um ponto de dados específico no gráfico. Neste exemplo, definimos o valor do primeiro ponto de dados na primeira série como 100. Você pode ajustar esse valor conforme necessário.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Etapa 4: salve a apresentação

Depois de fazer as alterações necessárias nos dados do gráfico, salve a apresentação modificada em um novo arquivo. Você pode especificar o caminho e o formato do arquivo de saída de acordo com suas necessidades.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Etapa 5: limpeza

Não se esqueça de descartar o objeto de apresentação para liberar recursos.

```java
if (pres != null) pres.dispose();
```

Agora você editou com sucesso os dados do gráfico em uma pasta de trabalho externa em sua apresentação do PowerPoint usando Aspose.Slides for Java. Você pode personalizar esse código para atender às suas necessidades específicas e integrá-lo aos seus aplicativos Java.

## Código fonte completo

```java
        // Preste atenção que o caminho para a pasta de trabalho externa dificilmente fica salvo na apresentação
        // então copie o arquivo externalWorkbook.xlsx do diretório Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ antes de executar o exemplo
        // O caminho para o diretório de documentos.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusão

Neste guia abrangente, exploramos como editar dados de gráficos em pastas de trabalho externas em apresentações do PowerPoint usando Aspose.Slides para Java. Seguindo as instruções passo a passo e os exemplos de código-fonte, você adquiriu o conhecimento e as habilidades para modificar programaticamente os dados do gráfico com facilidade.

## Perguntas frequentes

### Como especifico um gráfico ou slide diferente?

 Para acessar um gráfico ou slide diferente, modifique o índice apropriado na`getSlides().get_Item()` e`getShapes().get_Item()`métodos. Lembre-se de que a indexação começa em 0.

### Posso editar dados em vários gráficos na mesma apresentação?

Sim, você pode editar dados em vários gráficos na mesma apresentação, repetindo as etapas de modificação dos dados do gráfico para cada gráfico.

### E se eu quiser editar dados em uma pasta de trabalho externa com um formato diferente?

Você pode adaptar o código para lidar com diferentes formatos de pasta de trabalho externa usando as classes e métodos Aspose.Cells apropriados para ler e gravar dados nesse formato.

### Como posso automatizar esse processo para múltiplas apresentações?

Você pode criar um loop para processar múltiplas apresentações, carregando cada uma, fazendo as alterações desejadas e salvando as apresentações modificadas uma por uma.
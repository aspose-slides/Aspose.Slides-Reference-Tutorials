---
"description": "Aprenda a editar dados de gráficos em uma pasta de trabalho externa usando o Aspose.Slides para Java. Guia passo a passo com código-fonte."
"linktitle": "Editar dados do gráfico em pasta de trabalho externa em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Editar dados do gráfico em pasta de trabalho externa em slides Java"
"url": "/pt/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Editar dados do gráfico em pasta de trabalho externa em slides Java


## Introdução à edição de dados de gráfico em pasta de trabalho externa em slides Java

Neste guia, demonstraremos como editar dados de gráficos em uma pasta de trabalho externa usando o Aspose.Slides para Java. Você aprenderá a modificar dados de gráficos em uma apresentação do PowerPoint programaticamente. Certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu projeto.

## Pré-requisitos

- Aspose.Slides para Java
- Ambiente de desenvolvimento Java

## Etapa 1: Carregue a apresentação

Primeiro, precisamos carregar a apresentação do PowerPoint que contém o gráfico cujos dados queremos editar. Substituir `"Your Document Directory"` com o caminho real para o arquivo de apresentação.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Etapa 2: Acesse o gráfico

Após o carregamento da apresentação, precisamos acessar o gráfico dentro dela. Neste exemplo, presumimos que o gráfico está no primeiro slide e é a primeira forma desse slide.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Etapa 3: Modificar dados do gráfico

Agora, vamos modificar os dados do gráfico. Vamos nos concentrar em alterar um ponto de dados específico no gráfico. Neste exemplo, definimos o valor do primeiro ponto de dados da primeira série como 100. Você pode ajustar esse valor conforme necessário.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Etapa 4: Salve a apresentação

Após fazer as alterações necessárias nos dados do gráfico, salve a apresentação modificada em um novo arquivo. Você pode especificar o caminho e o formato do arquivo de saída de acordo com suas necessidades.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Etapa 5: Limpeza

Não se esqueça de descartar o objeto de apresentação para liberar quaisquer recursos.

```java
if (pres != null) pres.dispose();
```

Agora você editou com sucesso os dados do gráfico em uma pasta de trabalho externa dentro da sua apresentação do PowerPoint usando o Aspose.Slides para Java. Você pode personalizar este código para atender às suas necessidades específicas e integrá-lo aos seus aplicativos Java.

## Código-fonte completo

```java
        // Preste atenção que o caminho para a pasta de trabalho externa dificilmente é salvo na apresentação
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

Neste guia completo, exploramos como editar dados de gráficos em pastas de trabalho externas em apresentações do PowerPoint usando o Aspose.Slides para Java. Seguindo as instruções passo a passo e os exemplos de código-fonte, você adquiriu o conhecimento e as habilidades para modificar dados de gráficos programaticamente com facilidade.

## Perguntas frequentes

### Como especifico um gráfico ou slide diferente?

Para acessar um gráfico ou slide diferente, modifique o índice apropriado no `getSlides().get_Item()` e `getShapes().get_Item()` métodos. Lembre-se de que a indexação começa em 0.

### Posso editar dados em vários gráficos na mesma apresentação?

Sim, você pode editar dados em vários gráficos dentro da mesma apresentação repetindo as etapas de modificação de dados do gráfico para cada gráfico.

### E se eu quiser editar dados em uma pasta de trabalho externa com um formato diferente?

Você pode adaptar o código para lidar com diferentes formatos de pasta de trabalho externa usando as classes e métodos Aspose.Cells apropriados para ler e gravar dados nesse formato.

### Como posso automatizar esse processo para múltiplas apresentações?

Você pode criar um loop para processar várias apresentações, carregando cada uma, fazendo as alterações desejadas e salvando as apresentações modificadas uma por uma.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
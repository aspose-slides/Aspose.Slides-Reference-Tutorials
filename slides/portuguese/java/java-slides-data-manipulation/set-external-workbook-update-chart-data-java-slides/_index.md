---
"description": "Aprenda a definir pastas de trabalho externas e atualizar dados de gráficos no Java Slides usando o Aspose.Slides para Java. Aprimore suas habilidades de automação do PowerPoint."
"linktitle": "Definir pasta de trabalho externa com dados de atualização do gráfico em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir pasta de trabalho externa com dados de atualização do gráfico em slides Java"
"url": "/pt/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir pasta de trabalho externa com dados de atualização do gráfico em slides Java


## Introdução ao conjunto de pastas de trabalho externas com atualização de dados do gráfico em slides Java

Neste guia completo, mostraremos o processo de configuração de uma pasta de trabalho externa com dados de gráficos atualizados no Java Slides usando a API Aspose.Slides para Java. Esta poderosa biblioteca permite manipular apresentações do PowerPoint programaticamente, facilitando a automatização de tarefas como a atualização de dados de gráficos a partir de uma fonte externa. Ao final deste tutorial, você terá uma compreensão clara de como realizar essa tarefa com instruções passo a passo e o código Java correspondente.

## Pré-requisitos

Antes de começarmos a implementação, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Aspose.Slides para Java: Você deve ter a biblioteca Aspose.Slides para Java instalada. Você pode baixá-la em [aqui](https://releases.aspose.com/slides/java/).

2. Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java configurado no seu sistema.

## Etapa 1: Crie uma nova apresentação

Para começar, vamos criar uma nova apresentação do PowerPoint usando o Aspose.Slides para Java. Aqui está o código Java para fazer isso:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: Adicionar um gráfico

Agora, vamos adicionar um gráfico à nossa apresentação. Neste exemplo, criaremos um gráfico de pizza:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Etapa 3: Definir pasta de trabalho externa

É aqui que definimos a pasta de trabalho externa como fonte de dados para o nosso gráfico. Você precisa fornecer a URL da pasta de trabalho externa, mesmo que ela ainda não exista:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://caminho/não/existe", falso);
```

## Etapa 4: Salve a apresentação

Por fim, salve a apresentação com os dados do gráfico atualizados:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para definir pasta de trabalho externa com dados de gráfico de atualização em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://caminho/não/existe", falso);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Parabéns! Você aprendeu a configurar uma pasta de trabalho externa com dados de gráficos atualizados no Java Slides usando o Aspose.Slides para Java. Isso pode ser incrivelmente útil para atualizar gráficos dinamicamente em suas apresentações do PowerPoint a partir de fontes de dados externas.

## Perguntas frequentes

### Como posso atualizar os dados da pasta de trabalho externa para o gráfico?

Para atualizar os dados da pasta de trabalho externa para o gráfico, basta modificar os dados na pasta de trabalho externa no URL especificado. Na próxima vez que você abrir a apresentação, o Aspose.Slides para Java buscará os dados atualizados da pasta de trabalho externa e atualizará o gráfico de acordo.

### Posso usar um arquivo local como pasta de trabalho externa?

Sim, você pode usar um arquivo local como pasta de trabalho externa, fornecendo o caminho do arquivo em vez de uma URL. Apenas certifique-se de que o caminho do arquivo esteja correto e acessível a partir do seu aplicativo Java.

### Há alguma limitação no uso de pastas de trabalho externas com o Aspose.Slides para Java?

Embora o uso de pastas de trabalho externas seja um recurso poderoso, lembre-se de que a disponibilidade dos dados da pasta de trabalho externa depende de sua acessibilidade na URL ou no caminho de arquivo fornecido. Certifique-se de que a fonte de dados externa esteja disponível ao abrir a apresentação para evitar problemas de recuperação de dados.

### Posso personalizar a aparência do gráfico depois de definir a pasta de trabalho externa?

Sim, você pode personalizar a aparência do gráfico, incluindo título, rótulos, cores e muito mais, mesmo depois de definir a pasta de trabalho externa. O Aspose.Slides para Java oferece diversas opções de formatação de gráficos para atender às suas necessidades.

### Onde posso encontrar mais documentação e recursos para o Aspose.Slides para Java?

Para documentação detalhada e recursos adicionais, visite a documentação do Aspose.Slides para Java em [aqui](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Definir pasta de trabalho externa com atualização de dados de gráfico em slides Java
linktitle: Definir pasta de trabalho externa com atualização de dados de gráfico em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir pastas de trabalho externas e atualizar dados de gráficos em Java Slides usando Aspose.Slides for Java. Aprimore suas habilidades de automação do PowerPoint.
weight: 20
url: /pt/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introdução à definição de pasta de trabalho externa com atualização de dados de gráfico em slides Java

Neste guia abrangente, orientaremos você no processo de configuração de uma pasta de trabalho externa com dados de gráfico atualizados em Java Slides usando a API Aspose.Slides for Java. Esta poderosa biblioteca permite manipular apresentações do PowerPoint de forma programática, facilitando a automatização de tarefas como a atualização de dados de gráficos de uma fonte externa. Ao final deste tutorial, você terá uma compreensão clara de como realizar essa tarefa com instruções passo a passo e o código Java que o acompanha.

## Pré-requisitos

Antes de mergulharmos na implementação, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Aspose.Slides for Java: você deve ter a biblioteca Aspose.Slides for Java instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

2. Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java configurado em seu sistema.

## Etapa 1: crie uma nova apresentação

Para começar, vamos criar uma nova apresentação em PowerPoint usando Aspose.Slides para Java. Aqui está o código Java para fazer isso:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Etapa 2: adicionar um gráfico

Agora, vamos adicionar um gráfico à nossa apresentação. Criaremos um gráfico de pizza neste exemplo:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Etapa 3: definir pasta de trabalho externa

É aqui que definimos a pasta de trabalho externa como fonte de dados para nosso gráfico. Você precisa fornecer a URL da pasta de trabalho externa, mesmo que ela não exista no momento:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://caminho/não/existe", false);
```

## Etapa 4: salve a apresentação

Por fim, salve a apresentação com os dados atualizados do gráfico:

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
	chartData.setExternalWorkbook("http://caminho/não/existe", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Parabéns! Você aprendeu como definir uma pasta de trabalho externa com dados de gráfico atualizados em Java Slides usando Aspose.Slides for Java. Isso pode ser extremamente útil para atualizar gráficos dinamicamente em suas apresentações do PowerPoint a partir de fontes de dados externas.

## Perguntas frequentes

### Como posso atualizar os dados da pasta de trabalho externa do gráfico?

Para atualizar os dados da pasta de trabalho externa para o gráfico, basta modificar os dados da pasta de trabalho externa no URL especificado. Na próxima vez que você abrir a apresentação, o Aspose.Slides for Java buscará os dados atualizados da pasta de trabalho externa e atualizará o gráfico de acordo.

### Posso usar um arquivo local como pasta de trabalho externa?

Sim, você pode usar um arquivo local como pasta de trabalho externa, fornecendo o caminho do arquivo em vez de um URL. Apenas certifique-se de que o caminho do arquivo esteja correto e acessível em seu aplicativo Java.

### Há alguma limitação no uso de pastas de trabalho externas com Aspose.Slides for Java?

Embora o uso de pastas de trabalho externas seja um recurso poderoso, lembre-se de que a disponibilidade dos dados da pasta de trabalho externa depende de sua acessibilidade na URL ou no caminho do arquivo fornecido. Certifique-se de que a fonte de dados externa esteja disponível ao abrir a apresentação para evitar problemas de recuperação de dados.

### Posso personalizar a aparência do gráfico depois de configurar a pasta de trabalho externa?

Sim, você pode personalizar a aparência do gráfico, incluindo título, rótulos, cores e muito mais, mesmo depois de configurar a pasta de trabalho externa. Aspose.Slides for Java oferece amplas opções de formatação de gráficos para atender às suas necessidades.

### Onde posso encontrar mais documentação e recursos para Aspose.Slides for Java?

 Para documentação detalhada e recursos adicionais, visite a documentação Aspose.Slides for Java em[aqui](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

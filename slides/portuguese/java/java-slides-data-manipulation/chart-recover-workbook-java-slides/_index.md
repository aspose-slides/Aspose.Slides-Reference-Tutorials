---
title: Pasta de trabalho de recuperação de gráfico em slides Java
linktitle: Pasta de trabalho de recuperação de gráfico em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como recuperar pastas de trabalho de gráficos em Java Slides com Aspose.Slides. Guia passo a passo para automação do PowerPoint.
weight: 17
url: /pt/java/data-manipulation/chart-recover-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pasta de trabalho de recuperação de gráfico em slides Java


## Introdução à pasta de trabalho de recuperação de gráfico em slides Java

Ao trabalhar com apresentações do PowerPoint em Java, você poderá encontrar cenários em que precisará recuperar dados da pasta de trabalho de um gráfico. Esta pode ser uma tarefa crucial, especialmente quando se trata de apresentações baseadas em dados. Aspose.Slides for Java simplifica esse processo e, neste guia, mostraremos como fazê-lo.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

- Java Development Kit (JDK) instalado em seu sistema.
-  Aspose.Slides para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: configurando seu projeto

Crie um novo projeto Java em seu ambiente de desenvolvimento integrado (IDE) favorito e adicione a biblioteca Aspose.Slides para Java às dependências do seu projeto.

## Passo 2: Importando as Classes Necessárias

Em seu código Java, importe as classes necessárias de Aspose.Slides for Java:

```java
import com.aspose.slides.*;
```

## Etapa 3: Carregando a Apresentação

Carregue a apresentação do PowerPoint que contém o gráfico do qual você deseja recuperar os dados da pasta de trabalho:

```java
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = "Path to Output File";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
```

## Etapa 4: acessando os dados do gráfico

Agora você pode acessar os dados do gráfico e recuperar a pasta de trabalho:

```java
try
{
    IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    // Execute operações nos dados da pasta de trabalho aqui
    pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Código-fonte completo para pasta de trabalho de recuperação de gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = RunExamples.OutPath + "ExternalWB_out.pptx";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
try
{
	IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste guia, percorremos o processo de recuperação de uma pasta de trabalho de um gráfico em Java Slides usando Aspose.Slides for Java. Essa biblioteca simplifica a tarefa, tornando mais fácil para os desenvolvedores trabalharem programaticamente com apresentações do PowerPoint. Agora você pode lidar com apresentações baseadas em dados com confiança e extrair informações da pasta de trabalho conforme necessário.

## Perguntas frequentes

### Como faço para instalar o Aspose.Slides para Java?

 Aspose.Slides for Java pode ser facilmente instalado baixando a biblioteca do site em[aqui](https://releases.aspose.com/slides/java/). Siga as instruções de instalação fornecidas para integrá-lo ao seu projeto Java.

### Posso recuperar dados da pasta de trabalho de qualquer gráfico em uma apresentação do PowerPoint?

Sim, você pode recuperar dados da pasta de trabalho de qualquer gráfico em uma apresentação do PowerPoint, desde que tenha a biblioteca Aspose.Slides para Java e o gráfico esteja acessível na apresentação. O trecho de código fornecido demonstra como fazer isso.

### Existem opções adicionais para trabalhar com dados gráficos usando Aspose.Slides for Java?

Sim, Aspose.Slides for Java oferece uma ampla gama de opções para trabalhar com dados gráficos. Você pode manipular propriedades de gráficos, recuperar pontos de dados e executar diversas operações em gráficos para atender a seus requisitos específicos.

### O Aspose.Slides for Java é adequado para automação profissional de PowerPoint?

Absolutamente! Aspose.Slides for Java é uma biblioteca poderosa para automatizar tarefas do PowerPoint, tornando-a adequada para casos de uso profissionais básicos e avançados. Ele fornece recursos abrangentes para criar, modificar e gerenciar apresentações do PowerPoint de forma programática.

### Como posso acessar mais documentação do Aspose.Slides for Java?

 Para documentação detalhada e referências sobre Aspose.Slides for Java, visite a página de documentação em[aqui](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

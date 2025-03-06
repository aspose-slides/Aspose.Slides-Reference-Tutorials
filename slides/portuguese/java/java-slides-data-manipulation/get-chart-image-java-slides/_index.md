---
title: Obtenha imagem de gráfico em slides Java
linktitle: Obtenha imagem de gráfico em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como obter imagens de gráficos em Java Slides usando Aspose.Slides for Java. Este guia passo a passo fornece código-fonte e dicas para uma integração perfeita.
weight: 19
url: /pt/java/data-manipulation/get-chart-image-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenha imagem de gráfico em slides Java


## Introdução para obter imagem de gráfico em slides Java

Aspose.Slides for Java é uma biblioteca poderosa que permite trabalhar com apresentações do PowerPoint de forma programática. Com esta biblioteca, você pode criar, manipular e extrair diversos elementos de apresentações, incluindo gráficos. Um requisito comum é obter imagens gráficas de slides, e demonstraremos como fazer exatamente isso neste guia.

## Pré-requisitos

Antes de mergulharmos no código, certifique-se de ter os seguintes pré-requisitos em vigor:

- Java Development Kit (JDK) instalado em seu sistema.
-  Biblioteca Aspose.Slides para Java baixada e configurada em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: configure seu projeto

Comece criando um projeto Java em seu ambiente de desenvolvimento integrado (IDE) preferido. Certifique-se de ter adicionado a biblioteca Aspose.Slides para Java às dependências do seu projeto.

## Etapa 2: inicializar a apresentação

Para começar, você precisa inicializar uma apresentação do PowerPoint. Neste exemplo, presumimos que você tenha um arquivo PowerPoint chamado “test.pptx” em seu diretório de documentos.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Etapa 3: adicione um gráfico e obtenha a imagem

A seguir, você pode adicionar um gráfico a um slide e obter sua imagem. Neste exemplo, adicionaremos um gráfico de colunas agrupadas.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

Neste trecho de código, criamos um gráfico de colunas agrupadas no primeiro slide da apresentação e, em seguida, obtemos sua imagem em miniatura. A imagem é salva como "image.png" no diretório especificado.

## Código-fonte completo para obter imagem de gráfico em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Obter imagens de gráficos de Java Slides usando Aspose.Slides for Java é um processo simples. Com o código fornecido, você pode integrar facilmente essa funcionalidade em seus aplicativos Java, permitindo trabalhar com apresentações do PowerPoint de maneira eficaz.

## Perguntas frequentes

### Como faço para instalar o Aspose.Slides para Java?

 Instalar Aspose.Slides para Java é simples. Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/slides/java/) e siga as instruções de instalação fornecidas na documentação.

### Posso personalizar o gráfico antes de obter sua imagem?

Sim, você pode personalizar a aparência, os dados e outras propriedades do gráfico antes de obter sua imagem. Aspose.Slides for Java oferece amplas opções para personalização de gráficos.

### Que outros recursos o Aspose.Slides for Java oferece?

Aspose.Slides for Java oferece uma ampla gama de recursos para trabalhar com apresentações em PowerPoint, incluindo criação de slides, manipulação de texto, edição de formas e muito mais. Você pode explorar a documentação para obter informações detalhadas.

### O Aspose.Slides for Java é adequado para uso comercial?

Sim, Aspose.Slides for Java pode ser usado para fins comerciais. Ele oferece opções de licenciamento que atendem tanto a desenvolvedores individuais quanto a empresas.

### Posso salvar a imagem do gráfico em um formato diferente?

 Certamente! Você pode salvar a imagem da carta em vários formatos, como JPEG ou GIF, especificando a extensão de arquivo apropriada no campo`ImageIO.write` método.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Aprenda a converter apresentações do PowerPoint para o formato XPS usando o Aspose.Slides para Java. Guia passo a passo com código-fonte."
"linktitle": "Converter sem opções XPS em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Converter sem opções XPS em slides Java"
"url": "/pt/java/presentation-conversion/convert-without-xps-options-java-slides/"
"weight": 33
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Converter sem opções XPS em slides Java


## Introdução Converter PowerPoint para XPS sem opções de XPS no Aspose.Slides para Java

Neste tutorial, guiaremos você pelo processo de conversão de uma apresentação do PowerPoint para um documento XPS (XML Paper Specification) usando o Aspose.Slides para Java sem especificar nenhuma opção XPS. Forneceremos instruções passo a passo e o código-fonte Java para realizar essa tarefa.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Aspose.Slides para Java: Certifique-se de ter a biblioteca Aspose.Slides para Java instalada e configurada em seu projeto Java. Você pode baixá-la do site [Site Aspose.Slides para Java](https://downloads.aspose.com/slides/java).

2. Ambiente de desenvolvimento Java: você deve ter um ambiente de desenvolvimento Java configurado no seu computador.

## Etapa 1: Importar Aspose.Slides para Java

No seu projeto Java, importe as classes Aspose.Slides for Java necessárias no início do seu arquivo Java:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Etapa 2: Carregue a apresentação do PowerPoint

Agora, carregaremos a apresentação do PowerPoint que você deseja converter para XPS. Substituir `"Your Document Directory"` com o caminho real para o arquivo de apresentação do PowerPoint:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Instanciar um objeto Presentation que representa um arquivo de apresentação
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

Certifique-se de substituir `"Convert_XPS.pptx"` com o nome real do seu arquivo do PowerPoint.

## Etapa 3: Salvar como XPS sem opções de XPS

Com o Aspose.Slides para Java, você pode salvar facilmente a apresentação carregada como um documento XPS sem especificar nenhuma opção XPS. Veja como fazer isso:

```java
try {
    // Salvando a apresentação em um documento XPS
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

Este bloco de código salva a apresentação como um documento XPS com o nome `"XPS_Output_Without_XPSOption_out.xps"`. Você pode alterar o nome do arquivo de saída conforme necessário.

## Código-fonte completo para converter sem opções XPS em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Instanciar um objeto Presentation que representa um arquivo de apresentação
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	// Salvando a apresentação em um documento XPS
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu a converter uma apresentação do PowerPoint em um documento XPS sem especificar nenhuma opção XPS usando o Aspose.Slides para Java. Você pode personalizar ainda mais o processo de conversão explorando as opções fornecidas pelo Aspose.Slides para Java. Para recursos mais avançados e documentação detalhada, visite o [Documentação do Aspose.Slides para Java](https://docs.aspose.com/slides/java/).

## Perguntas frequentes

### Como especifico opções XPS durante a conversão?

Para especificar opções XPS ao converter uma apresentação do PowerPoint, você pode usar o `XpsOptions` classe e definir várias propriedades, como compactação de imagem e incorporação de fontes. Se você tiver requisitos específicos para conversão XPS, consulte o [Documentação do Aspose.Slides para Java](https://docs.aspose.com/slides/java/) para mais detalhes.

### Existem opções adicionais para salvar em outros formatos?

Sim, o Aspose.Slides para Java oferece vários formatos de saída além do XPS, como PDF, TIFF e HTML. Você pode especificar o formato de saída desejado alterando o `SaveFormat` parâmetro ao chamar o `save` método. Consulte a documentação para obter uma lista completa dos formatos suportados.

### Como posso lidar com exceções durante o processo de conversão?

Você pode implementar o tratamento de exceções para lidar com quaisquer erros que possam ocorrer durante o processo de conversão. Conforme mostrado no código, um `try` e `finally` Os blocos são usados para garantir o descarte adequado de recursos, mesmo se ocorrer uma exceção.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
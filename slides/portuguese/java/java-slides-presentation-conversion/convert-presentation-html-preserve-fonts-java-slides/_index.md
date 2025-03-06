---
title: Convertendo apresentação em HTML preservando fontes originais em slides Java
linktitle: Convertendo apresentação em HTML preservando fontes originais em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Converta apresentações do PowerPoint em HTML preservando as fontes originais usando Aspose.Slides para Java.
weight: 14
url: /pt/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introdução à conversão de apresentações em HTML com preservação de fontes originais em slides Java

Neste tutorial, exploraremos como converter uma apresentação do PowerPoint (PPTX) em HTML preservando as fontes originais usando Aspose.Slides para Java. Isso garantirá que o HTML resultante se assemelhe muito à aparência da apresentação original.

## Etapa 1: Configurando o Projeto
Antes de mergulharmos no código, vamos garantir que você tenha a configuração necessária em vigor:

1. Baixe Aspose.Slides para Java: Se ainda não o fez, baixe e inclua a biblioteca Aspose.Slides para Java em seu projeto.

2. Crie um projeto Java: Configure um projeto Java em seu IDE favorito e certifique-se de ter uma pasta “lib” onde você pode colocar o arquivo JAR Aspose.Slides.

3. Importe classes necessárias: importe as classes necessárias no início do seu arquivo Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Etapa 2: convertendo a apresentação em HTML com fontes originais

Agora, vamos converter uma apresentação do PowerPoint em HTML preservando as fontes originais:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Carregar a apresentação
Presentation pres = new Presentation("input.pptx");

try {
    // Exclua fontes de apresentação padrão como Calibri e Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Crie opções de HTML e defina o formatador HTML personalizado
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Salve a apresentação como HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Descarte o objeto de apresentação
    if (pres != null) pres.dispose();
}
```

Neste trecho de código:

-  Carregamos a apresentação de entrada do PowerPoint usando`Presentation`.

- Definimos uma lista de fontes (`fontNameExcludeList`que queremos excluir da incorporação no HTML. Isso é útil para excluir fontes comuns como Calibri e Arial para reduzir o tamanho do arquivo.

-  Criamos uma instância de`EmbedAllFontsHtmlController` e passe a lista de exclusão de fontes para ele.

-  Nós criamos`HtmlOptions` e defina um formatador HTML personalizado usando`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Finalmente, salvamos a apresentação como HTML com as opções especificadas.

## Código-fonte completo para converter apresentação em HTML preservando fontes originais em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// excluir fontes de apresentação padrão
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusão

Neste tutorial, você aprendeu como converter uma apresentação do PowerPoint em HTML preservando as fontes originais usando Aspose.Slides para Java. Isso é útil quando você deseja manter a fidelidade visual de suas apresentações ao compartilhá-las na web.

## Perguntas frequentes

### Como faço o download do Aspose.Slides para Java?

 Você pode baixar Aspose.Slides para Java no site da Aspose. Visita[aqui](https://downloads.aspose.com/slides/java/) para obter a versão mais recente.

### Posso personalizar a lista de fontes excluídas?

 Sim, você pode personalizar o`fontNameExcludeList` array para incluir ou excluir fontes específicas de acordo com seus requisitos.

### Este método funciona para formatos mais antigos do PowerPoint, como PPT?

Este exemplo de código foi projetado para arquivos PPTX. Se precisar converter arquivos PPT mais antigos, pode ser necessário fazer ajustes no código.

### Como posso personalizar ainda mais a saída HTML?

 Você pode explorar o`HtmlOptions` classe para personalizar vários aspectos da saída HTML, como tamanho do slide, qualidade da imagem e muito mais.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

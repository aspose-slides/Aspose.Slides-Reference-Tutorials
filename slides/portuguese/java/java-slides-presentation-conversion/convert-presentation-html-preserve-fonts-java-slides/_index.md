---
"description": "Converta apresentações do PowerPoint para HTML preservando as fontes originais usando o Aspose.Slides para Java."
"linktitle": "Convertendo apresentação para HTML preservando fontes originais em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Convertendo apresentação para HTML preservando fontes originais em slides Java"
"url": "/pt/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertendo apresentação para HTML preservando fontes originais em slides Java


## Introdução à conversão de apresentações em HTML com preservação das fontes originais em slides Java

Neste tutorial, exploraremos como converter uma apresentação do PowerPoint (PPTX) para HTML, preservando as fontes originais, usando o Aspose.Slides para Java. Isso garantirá que o HTML resultante se assemelhe bastante à aparência da apresentação original.

## Etapa 1: Configurando o Projeto
Antes de mergulharmos no código, vamos garantir que você tenha a configuração necessária:

1. Baixe o Aspose.Slides para Java: se ainda não o fez, baixe e inclua a biblioteca Aspose.Slides para Java no seu projeto.

2. Crie um projeto Java: configure um projeto Java no seu IDE favorito e certifique-se de ter uma pasta "lib" onde você pode colocar o arquivo JAR Aspose.Slides.

3. Importar classes necessárias: importe as classes necessárias no início do seu arquivo Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Etapa 2: Convertendo a apresentação para HTML com fontes originais

Agora, vamos converter uma apresentação do PowerPoint para HTML preservando as fontes originais:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Carregar a apresentação
Presentation pres = new Presentation("input.pptx");

try {
    // Excluir fontes de apresentação padrão como Calibri e Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Crie opções HTML e defina o formatador HTML personalizado
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Salvar a apresentação como HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Descarte o objeto de apresentação
    if (pres != null) pres.dispose();
}
```

Neste trecho de código:

- Carregamos a apresentação de entrada do PowerPoint usando `Presentation`.

- Definimos uma lista de fontes (`fontNameExcludeList`) que queremos excluir da incorporação no HTML. Isso é útil para excluir fontes comuns como Calibri e Arial e reduzir o tamanho do arquivo.

- Criamos uma instância de `EmbedAllFontsHtmlController` e passar a lista de exclusão de fontes para ele.

- Nós criamos `HtmlOptions` e defina um formatador HTML personalizado usando `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Por fim, salvamos a apresentação como HTML com as opções especificadas.

## Código-fonte completo para converter apresentação em HTML com preservação das fontes originais em slides Java

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

Neste tutorial, você aprendeu a converter uma apresentação do PowerPoint para HTML, preservando as fontes originais, usando o Aspose.Slides para Java. Isso é útil quando você deseja manter a fidelidade visual das suas apresentações ao compartilhá-las na web.

## Perguntas frequentes

### Como faço para baixar o Aspose.Slides para Java?

Você pode baixar o Aspose.Slides para Java no site da Aspose. Visite [aqui](https://downloads.aspose.com/slides/java/) para obter a versão mais recente.

### Posso personalizar a lista de fontes excluídas?

Sim, você pode personalizar o `fontNameExcludeList` matriz para incluir ou excluir fontes específicas conforme suas necessidades.

### Este método funciona para formatos mais antigos do PowerPoint, como o PPT?

Este exemplo de código foi desenvolvido para arquivos PPTX. Se você precisar converter arquivos PPT mais antigos, talvez seja necessário fazer ajustes no código.

### Como posso personalizar ainda mais a saída HTML?

Você pode explorar o `HtmlOptions` classe para personalizar vários aspectos da saída HTML, como tamanho do slide, qualidade da imagem e muito mais.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
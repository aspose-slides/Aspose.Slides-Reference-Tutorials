---
title: Converta apresentações em HTML com fontes incorporadas
linktitle: Converta apresentações em HTML com fontes incorporadas
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Converta apresentações do PowerPoint em HTML com fontes incorporadas usando Aspose.Slides for .NET. Mantenha a originalidade perfeitamente.
weight: 13
url: /pt/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Na era digital de hoje, o compartilhamento de apresentações e documentos online tornou-se uma prática comum. No entanto, um desafio que surge frequentemente é garantir que suas fontes sejam exibidas corretamente ao converter apresentações para HTML. Este tutorial passo a passo irá guiá-lo através do processo de uso do Aspose.Slides for .NET para converter apresentações em HTML com fontes incorporadas, garantindo que seus documentos tenham a aparência desejada.

## Introdução ao Aspose.Slides para .NET

Antes de mergulharmos no tutorial, vamos apresentar brevemente o Aspose.Slides para .NET. É uma biblioteca poderosa que permite aos desenvolvedores trabalhar com apresentações do PowerPoint em aplicativos .NET. Com Aspose.Slides, você pode criar, modificar e converter arquivos PowerPoint programaticamente.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Slides for .NET: Você deve ter a biblioteca Aspose.Slides instalada em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/net/).

## Etapa 1: configure seu projeto

1. Crie um novo projeto ou abra um existente em seu ambiente de desenvolvimento .NET preferido.

2. Adicione uma referência à biblioteca Aspose.Slides em seu projeto.

3. Importe os namespaces necessários em seu código:

   ```csharp
   using Aspose.Slides;
   ```

## Etapa 2: carregue sua apresentação

 Para começar, você precisa carregar a apresentação que deseja converter para HTML. Substituir`"Your Document Directory"` com o diretório real onde seu arquivo de apresentação está localizado.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Seu código vai aqui
}
```

## Etapa 3: excluir fontes de apresentação padrão

Nesta etapa, você pode especificar quaisquer fontes de apresentação padrão que deseja excluir da incorporação. Isso pode ajudar a otimizar o tamanho do arquivo HTML resultante.

```csharp
string[] fontNameExcludeList = { };
```

## Etapa 4: escolha um controlador HTML

Agora você tem duas opções para incorporar fontes no HTML:

### Opção 1: incorporar todas as fontes

 Para incorporar todas as fontes usadas na apresentação, use o`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Opção 2: vincular todas as fontes

 Para vincular todas as fontes usadas na apresentação, use o`LinkAllFontsHtmlController`. Você deve especificar o diretório onde as fontes estão localizadas em seu sistema.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Etapa 5: definir opções de HTML

 Criar um`HtmlOptions` objeto e defina o formatador HTML para aquele que você selecionou na etapa anterior.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Use embedFontsController para incorporar todas as fontes
};
```

## Etapa 6: salvar como HTML

 Por fim, salve a apresentação como um arquivo HTML. Você pode escolher qualquer um`SaveFormat.Html` ou`SaveFormat.Html5` dependendo de suas necessidades.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Conclusão

Parabéns! Você converteu com sucesso sua apresentação para HTML com fontes incorporadas usando Aspose.Slides for .NET. Isso garante que suas fontes serão exibidas corretamente ao compartilhar suas apresentações online.

Agora você pode compartilhar facilmente suas apresentações lindamente formatadas com confiança, sabendo que seu público as verá exatamente como você pretendia.

 Para obter mais informações e referências detalhadas da API, confira o[Documentação do Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).

## Perguntas frequentes

### 1. Posso converter apresentações do PowerPoint para HTML usando Aspose.Slides for .NET em modo lote?

Sim, você pode converter em lote várias apresentações para HTML usando Aspose.Slides for .NET, percorrendo seus arquivos de apresentação e aplicando o processo de conversão a cada um.

### 2. Existe uma maneira de personalizar a aparência da saída HTML?

Certamente! Aspose.Slides for .NET oferece várias opções para personalizar a aparência e a formatação da saída HTML, como ajuste de cores, fontes e layout.

### 3. Há alguma limitação para incorporar fontes em HTML usando Aspose.Slides for .NET?

Embora o Aspose.Slides for .NET ofereça excelentes recursos de incorporação de fontes, lembre-se de que o tamanho dos seus arquivos HTML pode aumentar ao incorporar fontes. Certifique-se de otimizar suas escolhas de fontes para uso na web.

### 4. Posso converter apresentações do PowerPoint para outros formatos com Aspose.Slides for .NET?

Sim, Aspose.Slides for .NET oferece suporte a uma ampla variedade de formatos de saída, incluindo PDF, imagens e muito mais. Você pode converter facilmente suas apresentações para o formato de sua escolha.

### 5. Onde posso encontrar recursos adicionais e suporte para Aspose.Slides for .NET?

 Você pode acessar uma grande variedade de recursos, incluindo documentação, no[Referência da API Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

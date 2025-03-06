---
title: Preservando fontes originais - Converta apresentação em HTML
linktitle: Preservando fontes originais - Converta apresentação em HTML
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como preservar as fontes originais ao converter apresentações em HTML usando Aspose.Slides for .NET. Garanta a consistência da fonte e o impacto visual sem esforço.
weight: 14
url: /pt/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Neste guia completo, orientaremos você no processo de preservação das fontes originais ao converter uma apresentação para HTML usando Aspose.Slides for .NET. Forneceremos o código-fonte C# necessário e explicaremos cada etapa detalhadamente. Ao final deste tutorial, você poderá garantir que as fontes do documento HTML convertido permaneçam fiéis à apresentação original.

## 1. Introdução

Ao converter apresentações do PowerPoint para HTML, é crucial manter as fontes originais para garantir a consistência visual do seu conteúdo. Aspose.Slides for .NET fornece uma solução poderosa para conseguir isso. Neste tutorial, orientaremos você nas etapas necessárias para preservar as fontes originais durante o processo de conversão.

## 2. Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

- Visual Studio instalado em sua máquina.
- Biblioteca Aspose.Slides for .NET adicionada ao seu projeto.

## 3. Configurando Seu Projeto

Para começar, crie um novo projeto no Visual Studio e adicione a biblioteca Aspose.Slides for .NET como referência.

## 4. Carregando a apresentação

Use o seguinte código para carregar sua apresentação do PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Seu código aqui
}
```

 Substituir`"Your Document Directory"` com o caminho para o seu arquivo de apresentação.

## 5. Excluindo fontes padrão

Para excluir fontes padrão como Calibri e Arial, use o seguinte código:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Você pode personalizar esta lista conforme necessário.

## 6. Incorporando todas as fontes

A seguir, incorporaremos todas as fontes no documento HTML. Isso garante que as fontes originais sejam preservadas. Use o seguinte código:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Salvando como HTML

Agora salve a apresentação como um documento HTML com fontes incorporadas:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Substituir`"output.html"` com o nome do arquivo de saída desejado.

## 8. Conclusão

Neste tutorial, demonstramos como preservar as fontes originais ao converter uma apresentação do PowerPoint para HTML usando Aspose.Slides for .NET. Seguindo essas etapas, você pode garantir que o documento HTML convertido mantenha a integridade visual da apresentação original.

## 9. Perguntas frequentes

### Q1: Posso personalizar a lista de fontes excluídas?

 Sim você pode. Modifique o`fontNameExcludeList`array para incluir ou excluir fontes específicas de acordo com suas necessidades.

### P2: E se eu não quiser incorporar todas as fontes?

Se quiser incorporar apenas fontes específicas, você pode modificar o código de acordo. Consulte a documentação do Aspose.Slides for .NET para obter mais detalhes.

### Q3: Há algum requisito de licenciamento para usar Aspose.Slides for .NET?

Sim, você pode precisar de uma licença válida para usar Aspose.Slides for .NET em seus projetos. Consulte o site Aspose para obter informações de licenciamento.

### Q4: Posso converter outros formatos de arquivo para HTML usando Aspose.Slides for .NET?

Aspose.Slides for .NET concentra-se principalmente em apresentações em PowerPoint. Para converter outros formatos de arquivo para HTML, pode ser necessário explorar outros produtos Aspose adaptados para esses formatos.

### P5: Onde posso acessar recursos e suporte adicionais?

 Você pode encontrar mais documentação, tutoriais e suporte no site Aspose. Visita[Documentação Aspose.Slides para .NET](https://reference.aspose.com/slides/net/) para obter informações detalhadas.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

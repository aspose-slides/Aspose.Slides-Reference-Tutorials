---
"description": "Aprenda a preservar as fontes originais ao converter apresentações para HTML usando o Aspose.Slides para .NET. Garanta a consistência das fontes e o impacto visual sem esforço."
"linktitle": "Preservando fontes originais - Converta apresentação para HTML"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Preservando fontes originais - Converta apresentação para HTML"
"url": "/pt/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Preservando fontes originais - Converta apresentação para HTML


Neste guia completo, mostraremos o processo de preservação das fontes originais ao converter uma apresentação para HTML usando o Aspose.Slides para .NET. Forneceremos o código-fonte C# necessário e explicaremos cada etapa em detalhes. Ao final deste tutorial, você garantirá que as fontes do seu documento HTML convertido permaneçam fiéis à apresentação original.

## 1. Introdução

Ao converter apresentações do PowerPoint para HTML, é crucial manter as fontes originais para garantir a consistência visual do seu conteúdo. O Aspose.Slides para .NET oferece uma solução poderosa para isso. Neste tutorial, guiaremos você pelas etapas necessárias para preservar as fontes originais durante o processo de conversão.

## 2. Pré-requisitos

Antes de começar, certifique-se de que você tenha os seguintes pré-requisitos:

- Visual Studio instalado na sua máquina.
- Biblioteca Aspose.Slides para .NET adicionada ao seu projeto.

## 3. Configurando seu projeto

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

Substituir `"Your Document Directory"` com o caminho para o arquivo da sua apresentação.

## 5. Excluindo fontes padrão

Para excluir fontes padrão como Calibri e Arial, use o seguinte código:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Você pode personalizar esta lista conforme necessário.

## 6. Incorporando todas as fontes

Em seguida, incorporaremos todas as fontes no documento HTML. Isso garante que as fontes originais sejam preservadas. Use o seguinte código:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Salvando como HTML

Agora, salve a apresentação como um documento HTML com fontes incorporadas:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Substituir `"output.html"` com o nome do arquivo de saída desejado.

## 8. Conclusão

Neste tutorial, demonstramos como preservar as fontes originais ao converter uma apresentação do PowerPoint para HTML usando o Aspose.Slides para .NET. Seguindo esses passos, você garante que o documento HTML convertido mantenha a integridade visual da apresentação original.

## 9. Perguntas frequentes

### P1: Posso personalizar a lista de fontes excluídas?

Sim, você pode. Modifique o `fontNameExcludeList` matriz para incluir ou excluir fontes específicas de acordo com suas necessidades.

### P2: E se eu não quiser incorporar todas as fontes?

Se quiser incorporar apenas fontes específicas, você pode modificar o código conforme necessário. Consulte a documentação do Aspose.Slides para .NET para obter mais detalhes.

### Q3: Há algum requisito de licenciamento para usar o Aspose.Slides para .NET?

Sim, você pode precisar de uma licença válida para usar o Aspose.Slides para .NET em seus projetos. Consulte o site do Aspose para obter informações sobre licenciamento.

### T4: Posso converter outros formatos de arquivo para HTML usando o Aspose.Slides para .NET?

Aspose.Slides para .NET foca principalmente em apresentações do PowerPoint. Para converter outros formatos de arquivo para HTML, talvez você precise explorar outros produtos Aspose desenvolvidos especialmente para esses formatos.

### P5: Onde posso acessar recursos e suporte adicionais?

Você pode encontrar mais documentação, tutoriais e suporte no site da Aspose. Visite [Documentação do Aspose.Slides para .NET](https://reference.aspose.com/slides/net/) para obter informações detalhadas.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
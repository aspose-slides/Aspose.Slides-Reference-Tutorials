---
"description": "Explore o poder do Aspose.Slides para .NET na alteração de dados de objetos OLE sem esforço. Aprimore suas apresentações com conteúdo dinâmico."
"linktitle": "Alterando dados de objetos OLE em apresentações com Aspose.Slides"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Alterando dados de objetos OLE em apresentações com Aspose.Slides"
"url": "/pt/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Alterando dados de objetos OLE em apresentações com Aspose.Slides

## Introdução
Criar apresentações dinâmicas e interativas em PowerPoint é uma necessidade comum no mundo digital atual. Uma ferramenta poderosa para isso é o Aspose.Slides para .NET, uma biblioteca robusta que permite aos desenvolvedores manipular e aprimorar apresentações em PowerPoint programaticamente. Neste tutorial, vamos nos aprofundar no processo de alteração de dados de objetos OLE (Object Linking and Embedding) em slides de apresentação usando o Aspose.Slides.
## Pré-requisitos
Antes de começar a trabalhar com o Aspose.Slides para .NET, certifique-se de ter os seguintes pré-requisitos:
1. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento com o .NET instalado.
2. Biblioteca Aspose.Slides: Baixe e instale a biblioteca Aspose.Slides para .NET. Você pode encontrar a biblioteca [aqui](https://releases.aspose.com/slides/net/).
3. Noções básicas: familiarize-se com os conceitos básicos de programação em C# e apresentações em PowerPoint.
## Importar namespaces
No seu projeto C#, importe os namespaces necessários para usar as funcionalidades do Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Etapa 1: Configure seu projeto
Comece criando um novo projeto em C# e importando a biblioteca Aspose.Slides. Certifique-se de que seu projeto esteja configurado corretamente e que você tenha as dependências necessárias instaladas.
## Etapa 2: Acessar apresentação e slide
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Etapa 3: Localizar objeto OLE
Percorra todas as formas no slide para encontrar o quadro do objeto OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Etapa 4: Ler e modificar dados da pasta de trabalho
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Lendo dados de objetos na pasta de trabalho
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Modificando os dados da pasta de trabalho
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Alterando dados do objeto Ole Frame
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Etapa 5: Salve a apresentação
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Conclusão
Seguindo estes passos, você pode alterar facilmente os dados do objeto OLE nos slides da apresentação usando o Aspose.Slides para .NET. Isso abre um mundo de possibilidades para a criação de apresentações dinâmicas e personalizadas, adaptadas às suas necessidades específicas.
## Perguntas frequentes
### O que é Aspose.Slides para .NET?
Aspose.Slides para .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com apresentações do PowerPoint programaticamente, permitindo fácil manipulação e aprimoramento.
### Onde posso encontrar a documentação do Aspose.Slides?
A documentação do Aspose.Slides para .NET pode ser encontrada [aqui](https://reference.aspose.com/slides/net/).
### Como faço para baixar o Aspose.Slides para .NET?
Você pode baixar a biblioteca na página de lançamento [aqui](https://releases.aspose.com/slides/net/).
### Existe um teste gratuito disponível para o Aspose.Slides?
Sim, você pode acessar o teste gratuito [aqui](https://releases.aspose.com/).
### Onde posso obter suporte para o Aspose.Slides para .NET?
Para suporte e discussões, visite o [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
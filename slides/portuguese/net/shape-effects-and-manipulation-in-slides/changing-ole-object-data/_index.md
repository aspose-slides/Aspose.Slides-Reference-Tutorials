---
title: Alterando dados de objetos OLE na apresentação com Aspose.Slides
linktitle: Alterando dados de objetos OLE na apresentação com Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Explore o poder do Aspose.Slides for .NET na alteração de dados de objetos OLE sem esforço. Aprimore suas apresentações com conteúdo dinâmico.
weight: 25
url: /pt/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
Criar apresentações dinâmicas e interativas em PowerPoint é um requisito comum no mundo digital de hoje. Uma ferramenta poderosa para conseguir isso é Aspose.Slides for .NET, uma biblioteca robusta que permite aos desenvolvedores manipular e aprimorar apresentações do PowerPoint de forma programática. Neste tutorial, nos aprofundaremos no processo de alteração de dados de objetos OLE (Object Linking and Embedding) em slides de apresentação usando Aspose.Slides.
## Pré-requisitos
Antes de começar a trabalhar com Aspose.Slides for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento com .NET instalado.
2.  Biblioteca Aspose.Slides: Baixe e instale a biblioteca Aspose.Slides para .NET. Você pode encontrar a biblioteca[aqui](https://releases.aspose.com/slides/net/).
3. Compreensão Básica: Familiarize-se com conceitos básicos de programação C# e apresentações em PowerPoint.
## Importar namespaces
Em seu projeto C#, importe os namespaces necessários para usar as funcionalidades do Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Etapa 1: configure seu projeto
Comece criando um novo projeto C# e importando a biblioteca Aspose.Slides. Certifique-se de que seu projeto esteja configurado corretamente e de que você tenha as dependências necessárias instaladas.
## Etapa 2: acesse a apresentação e o slide
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Etapa 3: Localize o objeto OLE
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
## Etapa 4: ler e modificar dados da pasta de trabalho
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
            // Alterando dados do objeto de quadro Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Etapa 5: salve a apresentação
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Conclusão
Seguindo essas etapas, você pode alterar perfeitamente os dados do objeto OLE nos slides da apresentação usando Aspose.Slides for .NET. Isso abre um mundo de possibilidades para a criação de apresentações dinâmicas e personalizadas, adaptadas às suas necessidades específicas.
## perguntas frequentes
### O que é Aspose.Slides para .NET?
Aspose.Slides for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com apresentações do PowerPoint de forma programática, permitindo fácil manipulação e aprimoramento.
### Onde posso encontrar a documentação do Aspose.Slides?
 A documentação do Aspose.Slides for .NET pode ser encontrada[aqui](https://reference.aspose.com/slides/net/).
### Como faço o download do Aspose.Slides para .NET?
 Você pode baixar a biblioteca na página de lançamento[aqui](https://releases.aspose.com/slides/net/).
### Existe um teste gratuito disponível para Aspose.Slides?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### Onde posso obter suporte para Aspose.Slides for .NET?
 Para suporte e discussões, visite o[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

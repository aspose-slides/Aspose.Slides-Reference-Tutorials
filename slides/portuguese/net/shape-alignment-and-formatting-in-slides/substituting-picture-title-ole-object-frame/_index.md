---
title: Guia de incorporação de objetos OLE com Aspose.Slides para .NET
linktitle: Substituindo o título da imagem do quadro do objeto OLE nos slides da apresentação
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como aprimorar seus slides de apresentação com objetos OLE dinâmicos usando Aspose.Slides for .NET. Siga nosso guia passo a passo para uma integração perfeita.
weight: 15
url: /pt/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
A criação de slides de apresentação dinâmicos e envolventes geralmente envolve a incorporação de vários elementos multimídia. Neste tutorial, exploraremos como substituir o título da imagem de um quadro de objeto OLE (Object Linking and Embedding) em slides de apresentação usando a poderosa biblioteca Aspose.Slides para .NET. Aspose.Slides simplifica o processo de manipulação de objetos OLE, fornecendo aos desenvolvedores as ferramentas para aprimorar suas apresentações com facilidade.
## Pré-requisitos
Antes de mergulharmos no guia passo a passo, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Biblioteca Aspose.Slides for .NET: Certifique-se de ter a biblioteca Aspose.Slides for .NET instalada. Você pode baixá-lo no[Documentação Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- Dados de amostra: Prepare um arquivo Excel de amostra (por exemplo, "ExcelObject.xlsx") que você deseja incorporar como um objeto OLE na apresentação. Além disso, tenha um arquivo de imagem (por exemplo, "Image.png") que servirá como ícone para o objeto OLE.
- Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento com as ferramentas necessárias, como Visual Studio ou qualquer outro IDE preferido para desenvolvimento .NET.
## Importar namespaces
Em seu projeto .NET, certifique-se de importar os namespaces necessários para trabalhar com Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Etapa 1: configurar o diretório de documentos
```csharp
string dataDir = "Your Document Directory";
```
Certifique-se de substituir "Seu diretório de documentos" pelo caminho real para o diretório de documentos.
## Etapa 2: definir o arquivo de origem OLE e os caminhos do arquivo de ícone
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Atualize esses caminhos com os caminhos reais para seu arquivo Excel e arquivo de imagem de amostra.
## Etapa 3: crie uma instância de apresentação
```csharp
using (Presentation pres = new Presentation())
{
    // O código para as etapas subsequentes irá aqui
}
```
 Inicialize uma nova instância do`Presentation` aula.
## Etapa 4: adicionar quadro de objeto OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Adicione uma moldura de objeto OLE ao slide, especificando sua posição e dimensões.
## Etapa 5: adicionar objeto de imagem
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Leia o arquivo de imagem e adicione-o à apresentação como um objeto de imagem.
## Etapa 6: definir legenda para ícone OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Defina a legenda desejada para o ícone OLE.
## Conclusão
Incorporar objetos OLE em slides de apresentação usando Aspose.Slides for .NET é um processo simples. Este tutorial guiou você pelas etapas essenciais, desde a configuração do diretório de documentos até a adição e personalização de objetos OLE. Experimente diferentes tipos de arquivos e legendas para aprimorar o apelo visual de suas apresentações.
## Perguntas frequentes
### Posso incorporar outros tipos de arquivos como objetos OLE usando Aspose.Slides?
Sim, Aspose.Slides suporta a incorporação de vários tipos de arquivos, como planilhas do Excel, documentos do Word e muito mais.
### O ícone do objeto OLE é personalizável?
Absolutamente. Você pode substituir o ícone padrão por qualquer imagem de sua escolha para melhor se adequar ao tema da sua apresentação.
### O Aspose.Slides oferece suporte para animações com objetos OLE?
partir da versão mais recente, Aspose.Slides concentra-se na incorporação e exibição de objetos OLE e não manipula diretamente animações dentro dos objetos OLE.
### Posso manipular objetos OLE programaticamente depois de adicioná-los a um slide?
Certamente. Você tem controle programático total sobre objetos OLE, permitindo modificar suas propriedades e aparência conforme necessário.
### Há alguma limitação no tamanho dos objetos OLE incorporados?
Embora existam limitações de tamanho, elas geralmente são generosas. Recomenda-se testar com seu caso de uso específico para garantir o desempenho ideal.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

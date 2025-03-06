---
title: Como extrair vídeo de um slide usando Aspose.Slides para .NET
linktitle: Extrair vídeo do slide
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como extrair vídeos de slides do PowerPoint usando Aspose.Slides for .NET. Este guia passo a passo simplifica o processo para você.
weight: 14
url: /pt/net/audio-and-video-extraction/extract-video/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Aspose.Slides for .NET é uma biblioteca poderosa que permite trabalhar com apresentações do PowerPoint em um ambiente .NET. Um dos recursos úteis que oferece é a capacidade de extrair vídeos de slides. Neste guia passo a passo, mostraremos como extrair um vídeo de um slide do PowerPoint usando Aspose.Slides for .NET.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Slides para .NET: Você precisa ter o Aspose.Slides para .NET instalado. Você pode obtê-lo no[local na rede Internet](https://purchase.aspose.com/buy).

- Uma apresentação em PowerPoint: Prepare uma apresentação em PowerPoint (por exemplo, Video.pptx) que contenha o vídeo que você deseja extrair.

## Importar namespaces

Você precisa importar os namespaces necessários para trabalhar com Aspose.Slides for .NET. Veja como você pode fazer isso:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Agora, vamos dividir o processo de extração de um vídeo de um slide em várias etapas.

## Etapa 1: definir o diretório de documentos

```csharp
string dataDir = "Your Document Directory";
```

 Substituir`"Your Document Directory"` com o caminho para o diretório onde sua apresentação do PowerPoint está localizada.

## Etapa 2: carregar a apresentação

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Este código inicializa um objeto Presentation, representando seu arquivo de apresentação do PowerPoint.

## Etapa 3: iterar por meio de slides e formas

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Aqui, percorremos cada slide da apresentação e, em seguida, iteramos pelas formas do primeiro slide (modificamos conforme necessário).

## Etapa 4: verifique se a forma é um quadro de vídeo

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Esta etapa verifica se a forma do slide é um quadro de vídeo.

## Etapa 5: extrair dados de vídeo

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Este código extrai informações sobre o vídeo, incluindo tipo de conteúdo e dados binários.

## Etapa 6: salve o vídeo

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Finalmente, esta etapa salva o vídeo em um novo arquivo no diretório especificado.

Depois de concluir essas etapas, você terá extraído com sucesso um vídeo de um slide do PowerPoint usando Aspose.Slides for .NET.

## Conclusão

Aspose.Slides for .NET simplifica o processo de trabalhar com apresentações em PowerPoint, permitindo que você execute tarefas como extrair vídeos de slides com facilidade. Seguindo este guia passo a passo e usando a biblioteca Aspose.Slides, você pode aprimorar seus aplicativos .NET com recursos poderosos do PowerPoint.

## Perguntas frequentes (FAQ)

### O que é Aspose.Slides para .NET?
Aspose.Slides for .NET é uma biblioteca que permite que aplicativos .NET funcionem com apresentações em PowerPoint, incluindo criação, edição e extração de conteúdo.

### Onde posso encontrar a documentação do Aspose.Slides for .NET?
 Você pode encontrar a documentação[aqui](https://reference.aspose.com/slides/net/).

### O Aspose.Slides for .NET está disponível para teste gratuito?
 Sim, você pode obter uma versão de teste gratuita em[aqui](https://releases.aspose.com/).

### Como posso obter uma licença temporária do Aspose.Slides for .NET?
 Você pode solicitar uma licença temporária de[esse link](https://purchase.aspose.com/temporary-license/).

### Onde posso obter suporte para Aspose.Slides for .NET?
 Você pode encontrar suporte no[Fórum Aspose.Slides](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

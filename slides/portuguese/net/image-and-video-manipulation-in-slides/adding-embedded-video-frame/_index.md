---
title: Aspose.Slides - Adicionando vídeos incorporados em apresentações .NET
linktitle: Aspose.Slides - Adicionando vídeos incorporados em apresentações .NET
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprimore suas apresentações com vídeos incorporados usando Aspose.Slides for .NET. Siga nosso guia passo a passo para uma integração perfeita.
type: docs
weight: 19
url: /pt/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## Introdução
No mundo dinâmico das apresentações, a integração de elementos multimídia pode aumentar significativamente o envolvimento. Aspose.Slides for .NET fornece uma solução poderosa para incorporar quadros de vídeo incorporados em seus slides de apresentação. Este tutorial irá guiá-lo através do processo, detalhando cada etapa para garantir uma experiência perfeita.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter o seguinte:
-  Biblioteca Aspose.Slides for .NET: Baixe e instale a biblioteca do[página de lançamento](https://releases.aspose.com/slides/net/).
- Conteúdo de mídia: tenha um arquivo de vídeo (por exemplo, "Wildlife.mp4") que deseja incorporar em sua apresentação.
## Importar namespaces
Comece importando os namespaces necessários em seu projeto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Etapa 1: configurar diretórios
Certifique-se de que seu projeto tenha os diretórios necessários para arquivos de documentos e mídia:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Crie um diretório se ainda não estiver presente.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Etapa 2: instanciar aula de apresentação
Crie uma instância da classe Presentation para representar o arquivo PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Obtenha o primeiro slide
    ISlide sld = pres.Slides[0];
```
## Etapa 3: incorporar vídeo na apresentação
Use o código a seguir para incorporar um vídeo na apresentação:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Etapa 4: adicionar quadro de vídeo
Agora, adicione um quadro de vídeo ao slide:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Etapa 5: definir propriedades de vídeo
Defina o vídeo para o quadro de vídeo e configure o modo de reprodução e o volume:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Etapa 6: salve a apresentação
Finalmente, salve o arquivo PPTX no disco:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Repita essas etapas para cada vídeo que deseja incorporar à sua apresentação.
## Conclusão
Parabéns! Você adicionou com sucesso um quadro de vídeo incorporado à sua apresentação usando Aspose.Slides for .NET. Esse recurso dinâmico pode elevar suas apresentações a novos patamares, cativando seu público com elementos multimídia perfeitamente integrados em seus slides.
## Perguntas frequentes
### Posso incorporar vídeos em qualquer slide da apresentação?
 Sim, você pode escolher qualquer slide modificando o índice em`pres.Slides[index]`.
### Quais formatos de vídeo são suportados?
Aspose.Slides suporta uma variedade de formatos de vídeo, incluindo MP4, AVI e WMV.
### Posso personalizar o tamanho e a posição do quadro do vídeo?
 Absolutamente! Ajuste os parâmetros em`AddVideoFrame(x, y, width, height, video)` como necessário.
### Existe um limite para o número de vídeos que posso incorporar?
O número de vídeos incorporados normalmente é limitado pela capacidade do seu software de apresentação.
### Como posso procurar mais assistência ou partilhar a minha experiência?
 Visite a[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoio e discussões da comunidade.
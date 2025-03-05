---
title: Adicionando deslocamento de estiramento para preenchimento de imagem em apresentações do PowerPoint
linktitle: Adicionando deslocamento de estiramento para slides de preenchimento de imagem
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como aprimorar apresentações em PowerPoint com Aspose.Slides for .NET. Siga um guia passo a passo para adicionar um deslocamento de estiramento para preenchimento de imagem.
type: docs
weight: 18
url: /pt/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---
## Introdução
No mundo dinâmico das apresentações, os recursos visuais desempenham um papel fundamental na captura da atenção do público. Aspose.Slides for .NET capacita os desenvolvedores a aprimorar suas apresentações em PowerPoint, fornecendo um conjunto robusto de recursos. Um desses recursos é a capacidade de adicionar um deslocamento de estiramento para preenchimento de imagem, permitindo slides criativos e visualmente atraentes.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Biblioteca Aspose.Slides for .NET: Baixe e instale a biblioteca do[Documentação do Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento .NET funcional configurado.
Agora, vamos começar com o guia passo a passo.
## Importar namespaces
Em primeiro lugar, importe os namespaces necessários para aproveitar a funcionalidade Aspose.Slides em seu aplicativo .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Etapa 1: configure seu projeto
Crie um novo projeto .NET em seu ambiente de desenvolvimento preferido. Certifique-se de que Aspose.Slides for .NET esteja referenciado corretamente.
## Etapa 2: inicializar a aula de apresentação
 Instancie o`Presentation` classe para representar o arquivo PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Seu código vai aqui
}
```
## Etapa 3: obtenha o primeiro slide
Recupere o primeiro slide da apresentação para trabalhar.
```csharp
ISlide sld = pres.Slides[0];
```
## Etapa 4: instanciar a classe ImageEx
 Crie uma instância do`ImageEx`class para lidar com a imagem que você deseja adicionar ao slide.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Etapa 5: adicionar porta-retratos
 Utilize o`AddPictureFrame` método para adicionar uma moldura de imagem ao slide. Especifique as dimensões e a posição do quadro.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Etapa 6: salve a apresentação
Salve a apresentação modificada em disco.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
É isso! Você adicionou com sucesso um deslocamento de estiramento para slides de preenchimento de imagem usando Aspose.Slides for .NET.
## Conclusão
Aprimorar suas apresentações em PowerPoint agora é mais fácil do que nunca com Aspose.Slides for .NET. Seguindo este tutorial, você aprendeu como incorporar o deslocamento de estiramento para preenchimento de imagem, trazendo um novo nível de criatividade aos seus slides.
## Perguntas frequentes
### Posso usar Aspose.Slides for .NET em meus aplicativos da web?
Sim, Aspose.Slides for .NET é adequado para aplicativos de desktop e web.
### Existe um teste gratuito disponível para Aspose.Slides for .NET?
 Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### Como posso obter suporte para Aspose.Slides for .NET?
 Visite a[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoio comunitário.
### Onde posso encontrar a documentação completa do Aspose.Slides for .NET?
 Consulte o[documentação](https://reference.aspose.com/slides/net/) para obter informações detalhadas.
### Posso comprar Aspose.Slides para .NET?
 Sim, você pode comprar o produto[aqui](https://purchase.aspose.com/buy).
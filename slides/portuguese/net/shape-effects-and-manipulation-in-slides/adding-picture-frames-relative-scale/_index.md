---
title: Tutorial Adicionando Molduras de Imagem com Aspose.Slides .NET
linktitle: Adicionando molduras com altura de escala relativa em Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda a adicionar molduras com altura de escala relativa em Aspose.Slides for .NET. Siga este guia passo a passo para apresentações perfeitas.
weight: 17
url: /pt/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
Aspose.Slides for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e converter apresentações do PowerPoint em seus aplicativos .NET sem esforço. Neste tutorial, mergulharemos no processo de adição de molduras de imagem com altura de escala relativa usando Aspose.Slides for .NET. Siga este guia passo a passo para aprimorar suas habilidades de construção de apresentações.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
- Conhecimento básico da linguagem de programação C#.
- Visual Studio ou qualquer outro ambiente de desenvolvimento C# preferencial instalado.
- Biblioteca Aspose.Slides for .NET adicionada ao seu projeto.
## Importar namespaces
Comece importando os namespaces necessários para seu código C#. Esta etapa garante que você tenha acesso às classes e funcionalidades fornecidas pela biblioteca Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Etapa 1: configure seu projeto
Comece criando um novo projeto C# em seu ambiente de desenvolvimento preferido. Certifique-se de adicionar a biblioteca Aspose.Slides for .NET ao seu projeto referenciando-a.
## Etapa 2: carregar apresentação e imagem
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //Carregar imagem a ser adicionada na coleção de imagens de apresentação
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Nesta etapa criamos um novo objeto de apresentação e carregamos a imagem que queremos adicionar à apresentação.
## Etapa 3: adicionar moldura ao slide
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Agora, adicione uma moldura ao primeiro slide da apresentação. Ajuste os parâmetros como tipo de forma, posição e dimensões de acordo com suas necessidades.
## Etapa 4: definir largura e altura da escala relativa
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Defina a altura e a largura da escala relativa do porta-retratos para obter o efeito de escala desejado.
## Etapa 5: salvar a apresentação
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Por fim, salve a apresentação com o porta-retratos adicionado no formato de saída especificado.
## Conclusão
Parabéns! Você aprendeu com sucesso como adicionar molduras de imagem com altura de escala relativa usando Aspose.Slides for .NET. Experimente diferentes imagens, posições e escalas para criar apresentações visualmente atraentes e adaptadas às suas necessidades.
## perguntas frequentes
### Posso usar Aspose.Slides for .NET com outras linguagens de programação?
Aspose.Slides oferece suporte principalmente a linguagens .NET, mas você pode explorar outros produtos Aspose para compatibilidade com diferentes plataformas.
### Onde posso encontrar documentação detalhada para Aspose.Slides for .NET?
 Consulte o[documentação](https://reference.aspose.com/slides/net/) para obter informações abrangentes e exemplos.
### Existe um teste gratuito disponível para Aspose.Slides for .NET?
 Sim, você pode obter um[teste grátis](https://releases.aspose.com/) para avaliar as capacidades da biblioteca.
### Como posso obter suporte para Aspose.Slides for .NET?
 Visite a[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para buscar assistência da comunidade e de especialistas da Aspose.
### Onde posso comprar o Aspose.Slides para .NET?
 Você pode comprar Aspose.Slides para .NET no site[página de compra](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: Adicionando Stretch Offset à esquerda no PowerPoint com Aspose.Slide
linktitle: Adicionando Stretch Offset à esquerda para moldura de imagem em Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como aprimorar apresentações em PowerPoint usando Aspose.Slides for .NET. Siga nosso guia passo a passo para adicionar deslocamento de estiramento à esquerda para molduras de fotos.
type: docs
weight: 14
url: /pt/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## Introdução
Aspose.Slides for .NET é uma biblioteca poderosa que permite aos desenvolvedores manipular apresentações do PowerPoint com facilidade. Neste tutorial, exploraremos o processo de adição de um deslocamento de estiramento à esquerda para um porta-retratos usando Aspose.Slides for .NET. Siga este guia passo a passo para aprimorar suas habilidades no trabalho com imagens e formas em apresentações do PowerPoint.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Aspose.Slides for .NET: Certifique-se de ter a biblioteca instalada. Caso contrário, baixe-o do[Documentação do Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).
- Ambiente de desenvolvimento: tenha um ambiente de desenvolvimento funcional com recursos .NET.
## Importar namespaces
Comece importando os namespaces necessários em seu projeto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Etapa 1: configure seu projeto
Crie um novo projeto ou abra um existente. Certifique-se de ter a biblioteca Aspose.Slides referenciada em seu projeto.
## Passo 2: Criar Objeto de Apresentação
 Instancie o`Presentation` classe, representando o arquivo PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Seu código para as etapas subsequentes irá aqui.
}
```
## Etapa 3: obtenha o primeiro slide
Recupere o primeiro slide da apresentação:
```csharp
ISlide slide = pres.Slides[0];
```
## Etapa 4: instanciar a imagem
Carregue a imagem que deseja usar:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Etapa 5: adicionar AutoForma Retângulo
Crie uma AutoForma do tipo Retângulo:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Etapa 6: definir o tipo de preenchimento e o modo de preenchimento de imagem
Configure o tipo de preenchimento da forma e o modo de preenchimento da imagem:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Etapa 7: definir a imagem para preencher a forma
Especifique a imagem para preencher a forma:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Etapa 8: especificar deslocamentos de alongamento
Defina os deslocamentos da imagem a partir das bordas correspondentes da caixa delimitadora da forma:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Etapa 9: salve a apresentação
Grave o arquivo PPTX no disco:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Parabéns! Você adicionou com sucesso um deslocamento de estiramento à esquerda para um porta-retratos usando Aspose.Slides for .NET.
## Conclusão
Neste tutorial, exploramos o processo de manipulação de molduras em apresentações do PowerPoint usando Aspose.Slides for .NET. Seguindo o guia passo a passo, você obteve insights sobre como trabalhar com imagens, formas e deslocamentos.
## perguntas frequentes
### P: Posso aplicar deslocamentos de estiramento a outras formas além de retângulos?
R: Embora este tutorial se concentre em retângulos, os deslocamentos de estiramento podem ser aplicados a várias formas suportadas pelo Aspose.Slides.
### P: Como posso ajustar os deslocamentos de alongamento para diferentes efeitos?
R: Experimente diferentes valores de deslocamento para obter o impacto visual desejado. Ajuste os valores para atender às suas necessidades específicas.
### P: O Aspose.Slides é compatível com a estrutura .NET mais recente?
R: Aspose.Slides é atualizado regularmente para garantir compatibilidade com as versões mais recentes do .NET framework.
### P: Onde posso encontrar exemplos e recursos adicionais para Aspose.Slides?
 R: Explore o[Documentação do Aspose.Slides](https://reference.aspose.com/slides/net/) para obter exemplos e orientações abrangentes.
### P: Posso aplicar vários deslocamentos de alongamento a uma única forma?
R: Sim, você pode combinar vários deslocamentos de estiramento para obter efeitos visuais complexos e personalizados.
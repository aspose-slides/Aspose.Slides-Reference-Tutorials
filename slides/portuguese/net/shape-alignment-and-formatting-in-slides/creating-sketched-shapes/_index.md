---
"description": "Aprenda a adicionar formas esboçadas criativas aos slides da sua apresentação usando o Aspose.Slides para .NET. Aumente o apelo visual sem esforço!"
"linktitle": "Criando formas esboçadas em slides de apresentação com Aspose.Slides"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Crie formas esboçadas impressionantes com Aspose.Slides"
"url": "/pt/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crie formas esboçadas impressionantes com Aspose.Slides

## Introdução
Bem-vindo ao nosso guia passo a passo sobre como criar formas esboçadas em slides de apresentação usando o Aspose.Slides para .NET. Se você deseja adicionar um toque de criatividade às suas apresentações, as formas esboçadas proporcionam uma estética única e desenhada à mão. Neste tutorial, mostraremos o processo, dividindo-o em etapas simples para garantir uma experiência fluida.
## Pré-requisitos
Antes de começarmos o tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Aspose.Slides para .NET: Certifique-se de ter a biblioteca Aspose.Slides para .NET instalada. Você pode baixá-la [aqui](https://releases.aspose.com/slides/net/).
- Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET com seu IDE preferido.
## Importar namespaces
Comece importando os namespaces necessários para o seu projeto .NET. Esta etapa garante que você tenha acesso às classes e funcionalidades necessárias para trabalhar com o Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Etapa 1: Configurar o projeto
Comece criando um novo projeto .NET ou abrindo um existente. Certifique-se de incluir Aspose.Slides nas referências do seu projeto.
## Etapa 2: inicializar o Aspose.Slides
Inicialize o Aspose.Slides adicionando o seguinte trecho de código. Isso configura a apresentação e especifica os caminhos de saída para o arquivo de apresentação e a imagem em miniatura.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Continue para os próximos passos...
}
```
## Etapa 3: Adicionar forma esboçada
Agora, vamos adicionar uma forma esboçada ao slide. Neste exemplo, adicionaremos um retângulo com efeito de esboço à mão livre.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformar forma em esboço de estilo à mão livre
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Etapa 4: gerar miniatura
Crie uma miniatura do slide para visualizar a forma esboçada. Salve a miniatura como um arquivo PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Etapa 5: Salvar apresentação
Salve o arquivo de apresentação com a forma esboçada.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Pronto! Você criou com sucesso uma apresentação com formas esboçadas usando o Aspose.Slides para .NET.
## Conclusão
Adicionar formas esboçadas aos slides da sua apresentação pode aumentar o apelo visual e envolver o público. Com o Aspose.Slides para .NET, o processo se torna simples, permitindo que você libere sua criatividade sem esforço.
## Perguntas frequentes
### 1. Posso personalizar o efeito esboçado?
Sim, o Aspose.Slides para .NET oferece várias opções de personalização para efeitos esboçados. Consulte a [documentação](https://reference.aspose.com/slides/net/) para obter informações detalhadas.
### 2. Há um teste gratuito disponível?
Com certeza! Você pode experimentar uma versão de teste gratuita do Aspose.Slides para .NET [aqui](https://releases.aspose.com/).
### 3. Onde posso obter suporte?
Para qualquer assistência ou dúvida, visite o [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Como posso comprar o Aspose.Slides para .NET?
Para adquirir o Aspose.Slides para .NET, visite o [página de compra](https://purchase.aspose.com/buy).
### 5. Vocês oferecem licenças temporárias?
Sim, licenças temporárias estão disponíveis [aqui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
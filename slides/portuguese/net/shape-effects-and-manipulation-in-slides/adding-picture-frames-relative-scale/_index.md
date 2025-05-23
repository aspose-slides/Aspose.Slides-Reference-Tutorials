---
"description": "Aprenda a adicionar molduras com altura de escala relativa no Aspose.Slides para .NET. Siga este guia passo a passo para apresentações perfeitas."
"linktitle": "Adicionando molduras com altura de escala relativa no Aspose.Slides"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Tutorial de adição de molduras com Aspose.Slides .NET"
"url": "/pt/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial de adição de molduras com Aspose.Slides .NET

## Introdução
Aspose.Slides para .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e converter apresentações do PowerPoint em seus aplicativos .NET sem esforço. Neste tutorial, vamos nos aprofundar no processo de adição de molduras com altura de escala relativa usando o Aspose.Slides para .NET. Siga este guia passo a passo para aprimorar suas habilidades de criação de apresentações.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
- Conhecimento básico da linguagem de programação C#.
- Visual Studio ou qualquer outro ambiente de desenvolvimento C# preferido instalado.
- Biblioteca Aspose.Slides para .NET adicionada ao seu projeto.
## Importar namespaces
Comece importando os namespaces necessários para o seu código C#. Esta etapa garante que você tenha acesso às classes e funcionalidades fornecidas pela biblioteca Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Etapa 1: Configure seu projeto
Comece criando um novo projeto C# no seu ambiente de desenvolvimento preferido. Certifique-se de adicionar a biblioteca Aspose.Slides para .NET ao seu projeto, referenciando-a.
## Etapa 2: Carregar apresentação e imagem
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Carregar imagem a ser adicionada na coleção de imagens de apresentação
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Nesta etapa, criamos um novo objeto de apresentação e carregamos a imagem que queremos adicionar à apresentação.
## Etapa 3: adicionar moldura ao slide
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Agora, adicione uma moldura ao primeiro slide da apresentação. Ajuste os parâmetros como tipo de formato, posição e dimensões de acordo com suas necessidades.
## Etapa 4: definir largura e altura da escala relativa
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Defina a altura e a largura da escala relativa para a moldura da imagem para obter o efeito de escala desejado.
## Etapa 5: Salvar apresentação
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Por fim, salve a apresentação com a moldura adicionada no formato de saída especificado.
## Conclusão
Parabéns! Você aprendeu com sucesso a adicionar molduras com altura de escala relativa usando o Aspose.Slides para .NET. Experimente diferentes imagens, posições e escalas para criar apresentações visualmente atraentes e personalizadas de acordo com suas necessidades.
## Perguntas frequentes
### Posso usar o Aspose.Slides para .NET com outras linguagens de programação?
O Aspose.Slides oferece suporte principalmente à linguagem .NET, mas você pode explorar outros produtos Aspose para verificar a compatibilidade com diferentes plataformas.
### Onde posso encontrar documentação detalhada do Aspose.Slides para .NET?
Consulte o [documentação](https://reference.aspose.com/slides/net/) para obter informações e exemplos abrangentes.
### Existe uma avaliação gratuita disponível do Aspose.Slides para .NET?
Sim, você pode obter um [teste gratuito](https://releases.aspose.com/) para avaliar as capacidades da biblioteca.
### Como posso obter suporte para o Aspose.Slides para .NET?
Visite o [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para buscar assistência da comunidade e dos especialistas da Aspose.
### Onde posso comprar o Aspose.Slides para .NET?
Você pode comprar Aspose.Slides para .NET no [página de compra](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
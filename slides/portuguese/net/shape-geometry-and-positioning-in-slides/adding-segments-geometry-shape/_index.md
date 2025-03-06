---
title: Dominando recursos visuais - Adicionando segmentos com Aspose.Slides em .NET
linktitle: Adicionando segmentos à forma geométrica na apresentação com Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como aprimorar seus aplicativos .NET com Aspose.Slides. Este tutorial orienta você na adição de segmentos a formas geométricas para apresentações cativantes.
weight: 13
url: /pt/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
No mundo do desenvolvimento .NET, criar apresentações visualmente atraentes é um requisito comum. Aspose.Slides for .NET é uma biblioteca poderosa que facilita a integração perfeita de recursos robustos de criação de apresentações em seus aplicativos .NET. Este tutorial se concentra em um aspecto específico do design de apresentações – adicionar segmentos a formas geométricas.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento básico da linguagem de programação C#.
- Visual Studio instalado em sua máquina.
- Biblioteca Aspose.Slides for .NET baixada e referenciada em seu projeto.
## Importar namespaces
Em seu código C#, certifique-se de importar os namespaces necessários para acessar as funcionalidades do Aspose.Slides. Adicione as seguintes linhas ao seu código:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Agora, vamos dividir o exemplo em várias etapas.
## Etapa 1: configure seu projeto
Comece criando um novo projeto C# no Visual Studio. Certifique-se de ter a biblioteca Aspose.Slides referenciada em seu projeto.
## Etapa 2: crie uma apresentação
Inicialize um novo objeto de apresentação usando a biblioteca Aspose.Slides. Isso servirá como tela para sua forma geométrica.
```csharp
using (Presentation pres = new Presentation())
{
    // Seu código para criar uma apresentação vai aqui
}
```
## Etapa 3: adicionar uma forma geométrica
Crie uma forma geométrica dentro da apresentação. Por exemplo, vamos adicionar um retângulo ao primeiro slide.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Etapa 4: obter o caminho geométrico
Recupere o caminho geométrico da forma criada para manipular seus segmentos.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## Etapa 5: adicionar segmentos
Adicione segmentos (linhas) ao caminho geométrico. Neste exemplo, duas linhas são adicionadas ao caminho.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Etapa 6: Atribuir caminho de geometria editado
Atribua o caminho geométrico modificado de volta à forma para aplicar as alterações.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Etapa 7: salve a apresentação
Salve a apresentação modificada no local desejado.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Com essas etapas, você adicionou segmentos com êxito a uma forma geométrica em uma apresentação usando Aspose.Slides for .NET.
## Conclusão
Aspose.Slides for .NET capacita os desenvolvedores a aprimorar seus aplicativos com recursos avançados de criação de apresentações. Adicionar segmentos a formas geométricas fornece um meio de personalizar os elementos visuais de suas apresentações.
### perguntas frequentes
### Posso adicionar diferentes tipos de formas usando Aspose.Slides?
Sim, Aspose.Slides oferece suporte a vários tipos de formas, incluindo retângulos, círculos e formas geométricas personalizadas.
### É necessária uma licença para usar Aspose.Slides em meu projeto?
Sim, é necessária uma licença válida. Você pode obter uma licença temporária para fins de teste ou adquirir uma licença completa para produção.
### Como posso obter suporte para consultas relacionadas ao Aspose.Slides?
 Visite a[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoio e discussões da comunidade.
### Existem outros tutoriais disponíveis para Aspose.Slides?
 Explore o[documentação](https://reference.aspose.com/slides/net/) para guias e exemplos completos.
### Posso experimentar o Aspose.Slides gratuitamente antes de comprar?
 Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

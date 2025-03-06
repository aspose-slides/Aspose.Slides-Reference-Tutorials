---
title: Ocultar formas no PowerPoint com o tutorial Aspose.Slides .NET
linktitle: Ocultando formas em slides de apresentação com Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como ocultar formas em slides do PowerPoint usando Aspose.Slides for .NET. Personalize apresentações de maneira programática com este guia passo a passo.
weight: 21
url: /pt/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
No mundo dinâmico das apresentações, a personalização é fundamental. Aspose.Slides for .NET fornece uma solução poderosa para manipular apresentações do PowerPoint de forma programática. Um requisito comum é a capacidade de ocultar formas específicas em um slide. Este tutorial irá guiá-lo através do processo de ocultar formas em slides de apresentação usando Aspose.Slides for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Aspose.Slides para .NET: Certifique-se de ter a biblioteca Aspose.Slides instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/slides/net/).
- Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento preferido para .NET.
- Conhecimento básico de C#: Familiarize-se com C#, pois os exemplos de código fornecidos estão nesta linguagem.
## Importar namespaces
Para começar a trabalhar com Aspose.Slides, importe os namespaces necessários em seu projeto C#. Isso garante que você tenha acesso às classes e métodos necessários.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Agora, vamos dividir o código de exemplo em várias etapas para uma compreensão clara e concisa.
## Etapa 1: configure seu projeto
Crie um novo projeto C# e certifique-se de incluir a biblioteca Aspose.Slides.
## Etapa 2: crie uma apresentação
 Instancie o`Presentation` classe, representando o arquivo PowerPoint. Adicione um slide e obtenha uma referência a ele.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Etapa 3: adicionar formas ao slide
Adicione formas automáticas ao slide, como retângulos e luas, com dimensões específicas.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Etapa 4: ocultar formas com base em texto alternativo
Especifique um texto alternativo e oculte as formas que correspondam a esse texto.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Etapa 5: salve a apresentação
Salve a apresentação modificada em disco no formato PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusão
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Perguntas frequentes
### O Aspose.Slides é compatível com o .NET Core?
Sim, Aspose.Slides oferece suporte a .NET Core, proporcionando flexibilidade em seu ambiente de desenvolvimento.
### Posso ocultar formas com base em condições diferentes do texto alternativo?
Absolutamente! Você pode personalizar a lógica de ocultação com base em vários atributos, como tipo de forma, cor ou posição.
### Onde posso encontrar documentação adicional do Aspose.Slides?
 Explorar a documentação[aqui](https://reference.aspose.com/slides/net/)para obter informações detalhadas e exemplos.
### As licenças temporárias estão disponíveis para Aspose.Slides?
 Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/)para fins de teste.
### Como posso obter suporte da comunidade para Aspose.Slides?
 Junte-se à comunidade Aspose.Slides no[fórum](https://forum.aspose.com/c/slides/11) para discussões e assistência.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
"description": "Aprenda a ocultar formas em slides do PowerPoint usando o Aspose.Slides para .NET. Personalize apresentações programaticamente com este guia passo a passo."
"linktitle": "Ocultando formas em slides de apresentação com Aspose.Slides"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Tutorial para ocultar formas no PowerPoint com Aspose.Slides .NET"
"url": "/pt/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial para ocultar formas no PowerPoint com Aspose.Slides .NET

## Introdução
No mundo dinâmico das apresentações, a personalização é fundamental. O Aspose.Slides para .NET oferece uma solução poderosa para manipular apresentações do PowerPoint programaticamente. Um requisito comum é a capacidade de ocultar formas específicas dentro de um slide. Este tutorial guiará você pelo processo de ocultar formas em slides de apresentação usando o Aspose.Slides para .NET.
## Pré-requisitos
Antes de começar o tutorial, certifique-se de ter os seguintes pré-requisitos:
- Aspose.Slides para .NET: Certifique-se de ter a biblioteca Aspose.Slides instalada. Você pode baixá-la [aqui](https://releases.aspose.com/slides/net/).
- Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento preferido para .NET.
- Conhecimento básico de C#: familiarize-se com C#, pois os exemplos de código fornecidos estão nessa linguagem.
## Importar namespaces
Para começar a trabalhar com o Aspose.Slides, importe os namespaces necessários para o seu projeto C#. Isso garante que você tenha acesso às classes e métodos necessários.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Agora, vamos dividir o código de exemplo em várias etapas para uma compreensão clara e concisa.
## Etapa 1: Configure seu projeto
Crie um novo projeto C# e certifique-se de incluir a biblioteca Aspose.Slides.
## Etapa 2: Crie uma apresentação
Instanciar o `Presentation` classe, representando o arquivo do PowerPoint. Adicione um slide e obtenha uma referência a ele.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Etapa 3: adicione formas ao slide
Adicione formas automáticas ao slide, como retângulos e luas, com dimensões específicas.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Etapa 4: ocultar formas com base em texto alternativo
Especifique um texto alternativo e oculte as formas que correspondem a esse texto.
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
## Etapa 5: Salve a apresentação
Salve a apresentação modificada no disco no formato PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusão
Parabéns! Você ocultou formas com sucesso na sua apresentação usando o Aspose.Slides para .NET. Isso abre um mundo de possibilidades para a criação de slides dinâmicos e personalizados programaticamente.
---
## Perguntas frequentes
### O Aspose.Slides é compatível com o .NET Core?
Sim, o Aspose.Slides suporta .NET Core, proporcionando flexibilidade no seu ambiente de desenvolvimento.
### Posso ocultar formas com base em condições diferentes do texto alternativo?
Com certeza! Você pode personalizar a lógica de ocultação com base em vários atributos, como tipo de forma, cor ou posição.
### Onde posso encontrar documentação adicional do Aspose.Slides?
Explore a documentação [aqui](https://reference.aspose.com/slides/net/) para obter informações e exemplos mais detalhados.
### Há licenças temporárias disponíveis para o Aspose.Slides?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para fins de teste.
### Como posso obter suporte da comunidade para o Aspose.Slides?
Junte-se à comunidade Aspose.Slides no [fórum](https://forum.aspose.com/c/slides/11) para discussões e assistência.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
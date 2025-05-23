---
"description": "Aprenda a criar formas de grupo no PowerPoint com o Aspose.Slides para .NET. Siga nosso guia passo a passo para criar apresentações visualmente atraentes."
"linktitle": "Criando formas de grupo em slides de apresentação com Aspose.Slides"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides - Criando Formas de Grupo no .NET"
"url": "/pt/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Criando Formas de Grupo no .NET

## Introdução
Se você busca aprimorar o apelo visual dos slides da sua apresentação e organizar o conteúdo com mais eficiência, incorporar formas de grupo é uma solução poderosa. O Aspose.Slides para .NET oferece uma maneira simples de criar e manipular formas de grupo em suas apresentações do PowerPoint. Neste tutorial, mostraremos o processo de criação de formas de grupo usando o Aspose.Slides, dividindo-o em etapas fáceis de seguir.
## Pré-requisitos
Antes de começarmos o tutorial, certifique-se de ter o seguinte:
- Aspose.Slides para .NET: Certifique-se de ter a biblioteca Aspose.Slides instalada. Você pode baixá-la do site [site](https://releases.aspose.com/slides/net/).
- Ambiente de desenvolvimento: configure um ambiente de trabalho com um IDE compatível com .NET, como o Visual Studio.
- Conhecimento básico de C#: familiarize-se com os conceitos básicos da linguagem de programação C#.
## Importar namespaces
No seu projeto C#, comece importando os namespaces necessários:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Etapa 1: Instanciar a classe de apresentação

Crie uma instância do `Presentation` classe e especifique o diretório onde seus documentos estão armazenados:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continue com os seguintes passos dentro deste bloco de uso
}
```

## Etapa 2: Acesse o primeiro slide

Recupere o primeiro slide da apresentação:

```csharp
ISlide sld = pres.Slides[0];
```

## Etapa 3: Acessando a coleção de formas

Acesse a coleção de formas no slide:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Etapa 4: Adicionando uma forma de grupo

Adicione uma forma de grupo ao slide:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Etapa 5: Adicionando formas dentro da forma do grupo

Preencha a forma do grupo com formas individuais:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Etapa 6: Adicionando o quadro de forma do grupo

Defina o quadro para todo o formato do grupo:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Etapa 7: Salve a apresentação

Salve a apresentação modificada no diretório especificado:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Repita essas etapas no seu aplicativo C# para criar com sucesso formas de grupo nos slides da sua apresentação usando o Aspose.Slides.

## Conclusão
Neste tutorial, exploramos o processo de criação de formas de grupo com o Aspose.Slides para .NET. Seguindo esses passos, você pode aprimorar o apelo visual e a organização das suas apresentações do PowerPoint.
## Perguntas frequentes
### O Aspose.Slides é compatível com a versão mais recente do .NET?
Sim, o Aspose.Slides é atualizado regularmente para oferecer suporte às versões mais recentes do .NET. Verifique a [documentação](https://reference.aspose.com/slides/net/) para detalhes de compatibilidade.
### Posso testar o Aspose.Slides antes de comprar?
Com certeza! Você pode baixar uma versão de teste gratuita [aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte para dúvidas relacionadas ao Aspose.Slides?
Visite o Aspose.Slides [fórum](https://forum.aspose.com/c/slides/11) para apoio e discussões da comunidade.
### Como obtenho uma licença temporária para o Aspose.Slides?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar uma licença completa para o Aspose.Slides?
Você pode comprar uma licença do [página de compra](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
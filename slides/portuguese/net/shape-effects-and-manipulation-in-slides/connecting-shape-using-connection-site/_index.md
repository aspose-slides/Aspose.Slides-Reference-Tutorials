---
title: Domínio da conexão de formas com Aspose.Slides para .NET
linktitle: Conectando forma usando site de conexão na apresentação
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Crie apresentações cativantes com Aspose.Slides for .NET, conectando formas perfeitamente. Siga nosso guia para uma experiência tranquila e envolvente.
weight: 30
url: /pt/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Domínio da conexão de formas com Aspose.Slides para .NET

## Introdução
No mundo dinâmico das apresentações, criar slides visualmente atraentes com formas interligadas é crucial para uma comunicação eficaz. Aspose.Slides for .NET fornece uma solução poderosa para conseguir isso, permitindo conectar formas usando sites de conexão. Este tutorial irá guiá-lo através do processo de conexão de formas passo a passo, garantindo que suas apresentações se destaquem com transições visuais perfeitas.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Uma compreensão básica de programação C# e .NET.
-  Biblioteca Aspose.Slides para .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/slides/net/).
- Um ambiente de desenvolvimento integrado (IDE) como o Visual Studio configurado.
## Importar namespaces
Comece importando os namespaces necessários em seu código C#:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Etapa 1: configure seu diretório de documentos
Certifique-se de ter um diretório designado para o seu documento. Se não existir, crie um:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Etapa 2: crie uma apresentação
Instancie a classe Presentation para representar seu arquivo PPTX:
```csharp
using (Presentation presentation = new Presentation())
{
    // Seu código para a apresentação vai aqui
}
```
## Etapa 3: acessar e adicionar formas
Acesse a coleção de formas do slide selecionado e adicione as formas necessárias:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Etapa 4: unir formas usando conectores
Conecte as formas usando o conector:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## Etapa 5: definir o site de conexão desejado
Especifique o índice do site de conexão desejado para o conector:
```csharp
uint wantedIndex = 6;
if (ellipse.ConnectionSiteCount > wantedIndex)
{
    connector.StartShapeConnectionSiteIndex = wantedIndex;
}
```
## Etapa 6: salve sua apresentação
Salve sua apresentação com as formas conectadas:
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
Agora você conectou formas com sucesso usando sites de conexão em sua apresentação.
## Conclusão
Aspose.Slides for .NET simplifica o processo de conexão de formas, permitindo criar apresentações visualmente envolventes sem esforço. Seguindo este guia passo a passo, você pode aprimorar o apelo visual de seus slides e transmitir sua mensagem de maneira eficaz.
## perguntas frequentes
### O Aspose.Slides é compatível com o Visual Studio 2019?
Sim, Aspose.Slides é compatível com Visual Studio 2019. Certifique-se de ter a versão apropriada instalada.
### Posso conectar mais de duas formas em um único conector?
Aspose.Slides permite conectar duas formas com um único conector. Para conectar mais formas, você precisará de conectores adicionais.
### Como lidar com exceções ao usar Aspose.Slides?
Você pode usar blocos try-catch para lidar com exceções. Consulte o[documentação](https://reference.aspose.com/slides/net/) para exceções específicas e tratamento de erros.
### Existe uma versão de teste do Aspose.Slides disponível?
 Sim, você pode baixar uma versão de avaliação gratuita[aqui](https://releases.aspose.com/).
### Onde posso obter suporte para Aspose.Slides?
 Visite a[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoio e discussões da comunidade.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

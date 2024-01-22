---
title: Aspose.Slides - Conecte formas perfeitamente no .NET
linktitle: Conectando formas usando conectores na apresentação
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Explore o poder do Aspose.Slides for .NET, conectando formas sem esforço em suas apresentações. Eleve seus slides com conectores dinâmicos.
type: docs
weight: 29
url: /pt/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Introdução
No mundo dinâmico das apresentações, a capacidade de conectar formas usando conectores adiciona uma camada de sofisticação aos seus slides. Aspose.Slides for .NET capacita os desenvolvedores a conseguir isso perfeitamente. Este tutorial irá guiá-lo através do processo, detalhando cada etapa para garantir uma compreensão clara.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter o seguinte:
- Conhecimento básico de C# e .NET framework.
-  Aspose.Slides para .NET instalado. Se não, baixe-o[aqui](https://releases.aspose.com/slides/net/).
- Um ambiente de desenvolvimento configurado.
## Importar namespaces
No seu código C#, comece importando os namespaces necessários:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Configure o diretório de documentos
Comece definindo o diretório do seu documento:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Instanciar aula de apresentação
Crie uma instância da classe Presentation para representar seu arquivo PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Acessando a coleção de formas do slide selecionado
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Adicione formas ao slide
Adicione as formas necessárias ao seu slide, como Elipse e Retângulo:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Adicionar formato de conector
Inclua uma forma de conector na coleção de formas do slide:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Conecte formas com conector
Especifique as formas a serem conectadas pelo conector:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Conector de redirecionamento
Chame o método reroute para definir o caminho mais curto automático entre as formas:
```csharp
connector.Reroute();
```
## 7. Salvar apresentação
Salve sua apresentação para visualizar as formas conectadas:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Conclusão
Parabéns! Você conectou formas com sucesso usando conectores em slides de apresentação usando Aspose.Slides for .NET. Aprimore suas apresentações com esse recurso avançado e cative seu público.
## Perguntas frequentes
### O Aspose.Slides for .NET é compatível com a estrutura .NET mais recente?
Sim, o Aspose.Slides for .NET é atualizado regularmente para garantir compatibilidade com as versões mais recentes do .NET framework.
### Posso conectar mais de duas formas usando um único conector?
Com certeza, você pode conectar várias formas estendendo a lógica do conector em seu código.
### Há alguma limitação nas formas que posso conectar?
Aspose.Slides for .NET suporta a conexão de várias formas, incluindo formas básicas, arte inteligente e formas personalizadas.
### Como posso personalizar a aparência do conector?
Explore a documentação do Aspose.Slides para conhecer métodos para personalizar a aparência do conector, como estilo de linha e cor.
### Existe um fórum da comunidade para suporte do Aspose.Slides?
 Sim, você pode encontrar assistência e compartilhar suas experiências no[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
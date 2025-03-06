---
title: Criando geometria personalizada em C# com Aspose.Slides para .NET
linktitle: Criando geometria personalizada em forma geométrica usando Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda a criar geometria personalizada em Aspose.Slides for .NET. Eleve suas apresentações com formas exclusivas. Guia passo a passo para desenvolvedores C#.
weight: 15
url: /pt/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criando geometria personalizada em C# com Aspose.Slides para .NET

## Introdução
No mundo dinâmico das apresentações, adicionar formas e geometrias exclusivas pode elevar o seu conteúdo, tornando-o mais envolvente e visualmente atraente. Aspose.Slides for .NET fornece uma solução poderosa para criar geometrias personalizadas dentro de formas, permitindo que você se liberte dos designs convencionais. Este tutorial irá guiá-lo através do processo de criação de geometria personalizada em um GeometryShape usando Aspose.Slides for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Uma compreensão básica da linguagem de programação C#.
- Biblioteca Aspose.Slides for .NET instalada em seu ambiente de desenvolvimento.
- Visual Studio ou qualquer ambiente de desenvolvimento C# preferencial configurado.
## Importar namespaces
Para começar, importe os namespaces necessários para o seu projeto C#:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Etapa 1: configure seu projeto
Crie um novo projeto C# em seu ambiente de desenvolvimento preferido. Certifique-se de que o Aspose.Slides for .NET esteja instalado corretamente.
## Etapa 2: Defina seu diretório de documentos
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Etapa 3: definir o raio da estrela externa e interna
```csharp
float R = 100, r = 50; // Raio estelar externo e interno
```
## Etapa 4: criar um caminho de geometria estelar
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Etapa 5: crie uma apresentação
```csharp
using (Presentation pres = new Presentation())
{
    // Criar nova forma
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Defina um novo caminho geométrico para a forma
    shape.SetGeometryPath(starPath);
    // Salve a apresentação
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Etapa 6: Definir o método CreateStarGeometry
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Conclusão
Parabéns! Você aprendeu com sucesso como criar geometria personalizada em um GeometryShape usando Aspose.Slides para .NET. Isso abre um mundo de possibilidades para a criação de apresentações únicas e visualmente deslumbrantes.
## Perguntas frequentes
### 1. Posso usar Aspose.Slides for .NET com outras linguagens de programação?
Sim, Aspose.Slides oferece suporte a várias linguagens de programação, mas este tutorial se concentra em C#.
### 2. Onde posso encontrar a documentação do Aspose.Slides for .NET?
 Visite a[documentação](https://reference.aspose.com/slides/net/) para obter informações detalhadas.
### 3. Existe uma avaliação gratuita disponível para Aspose.Slides for .NET?
 Sim, você pode explorar um[teste grátis](https://releases.aspose.com/) para experimentar os recursos.
### 4. Como posso obter suporte para Aspose.Slides for .NET?
 Busque assistência e se envolva com a comunidade no[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Onde posso comprar o Aspose.Slides para .NET?
 Você pode comprar Aspose.Slides para .NET[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

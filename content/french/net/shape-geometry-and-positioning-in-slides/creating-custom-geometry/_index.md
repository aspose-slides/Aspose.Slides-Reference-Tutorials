---
title: Création d'une géométrie personnalisée en C# avec Aspose.Slides pour .NET
linktitle: Création d'une géométrie personnalisée dans une forme géométrique à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à créer une géométrie personnalisée dans Aspose.Slides pour .NET. Élevez vos présentations avec des formes uniques. Guide étape par étape pour les développeurs C#.
type: docs
weight: 15
url: /fr/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---
## Introduction
Dans le monde dynamique des présentations, l’ajout de formes et de géométries uniques peut rehausser votre contenu, le rendant plus attrayant et visuellement attrayant. Aspose.Slides pour .NET fournit une solution puissante pour créer des géométries personnalisées dans des formes, vous permettant de vous libérer des conceptions conventionnelles. Ce didacticiel vous guidera tout au long du processus de création d'une géométrie personnalisée dans un GeometryShape à l'aide d'Aspose.Slides pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Une compréhension de base du langage de programmation C#.
- Bibliothèque Aspose.Slides pour .NET installée dans votre environnement de développement.
- Visual Studio ou tout autre environnement de développement C# préféré configuré.
## Importer des espaces de noms
Pour commencer, importez les espaces de noms nécessaires dans votre projet C# :
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Étape 1 : Configurez votre projet
Créez un nouveau projet C# dans votre environnement de développement préféré. Assurez-vous qu'Aspose.Slides pour .NET est correctement installé.
## Étape 2 : définissez votre répertoire de documents
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Étape 3 : Définir le rayon de l'étoile externe et interne
```csharp
float R = 100, r = 50; // Rayon d'étoile extérieur et intérieur
```
## Étape 4 : Créer un chemin de géométrie en étoile
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Étape 5 : Créer une présentation
```csharp
using (Presentation pres = new Presentation())
{
    // Créer une nouvelle forme
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Définir un nouveau chemin géométrique vers la forme
    shape.SetGeometryPath(starPath);
    // Enregistrez la présentation
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Étape 6 : Définir la méthode CreateStarGeometry
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
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment créer une géométrie personnalisée dans un GeometryShape à l'aide d'Aspose.Slides pour .NET. Cela ouvre un monde de possibilités pour créer des présentations uniques et visuellement époustouflantes.
## FAQ
### 1. Puis-je utiliser Aspose.Slides pour .NET avec d’autres langages de programmation ?
Oui, Aspose.Slides prend en charge différents langages de programmation, mais ce didacticiel se concentre sur C#.
### 2. Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?
 Visiter le[Documentation](https://reference.aspose.com/slides/net/) pour des informations détaillées.
### 3. Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
 Oui, vous pouvez explorer un[essai gratuit](https://releases.aspose.com/) pour découvrir les fonctionnalités.
### 4. Comment puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?
 Demandez de l'aide et engagez-vous auprès de la communauté au[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Où puis-je acheter Aspose.Slides pour .NET ?
 Vous pouvez acheter Aspose.Slides pour .NET[ici](https://purchase.aspose.com/buy).
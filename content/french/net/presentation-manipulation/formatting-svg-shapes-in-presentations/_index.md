---
title: Formatage des formes SVG dans les présentations
linktitle: Formatage des formes SVG dans les présentations
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment formater des formes SVG dans des présentations à l'aide d'Aspose.Slides pour .NET. Guide étape par étape avec le code source. Améliorez le design de votre présentation dès aujourd'hui !
type: docs
weight: 13
url: /fr/net/presentation-manipulation/formatting-svg-shapes-in-presentations/
---

SVG (Scalable Vector Graphics) est un format largement utilisé pour représenter des graphiques vectoriels bidimensionnels. Aspose.Slides pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations par programme. Ce guide étape par étape montrera comment formater des formes SVG dans des présentations à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio : installez Visual Studio ou tout autre environnement de développement C#.
2.  Aspose.Slides pour .NET : téléchargez et installez la bibliothèque Aspose.Slides pour .NET à partir de[ici](https://releases.aspose.com/slides/net/).

## Guide étape par étape

## 1. Créez un nouveau projet C#
Créez un nouveau projet C# dans Visual Studio.

## 2. Ajouter une référence à Aspose.Slides
Ajoutez une référence à la bibliothèque Aspose.Slides for .NET dans votre projet.

## 3. Charger le fichier de présentation
Chargez le fichier de présentation PowerPoint contenant les formes SVG.

```csharp
using Aspose.Slides;

// Charger la présentation
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Votre code ici
}
```

## 4. Accédez à la diapositive et à la forme SVG
Accédez à la diapositive spécifique et à la forme SVG que vous souhaitez formater.

```csharp
// Accéder à la diapositive
ISlide slide = presentation.Slides[0]; // Remplacer par l'index de diapositive approprié

// Accéder à la forme SVG
IShape svgShape = slide.Shapes[0]; // Remplacer par l'indice de forme approprié
```

## 5. Appliquer le formatage à la forme SVG
 Appliquez le formatage à la forme SVG à l'aide du`ISvgShape` méthodes d'interface.

```csharp
// Convertir la forme en ISvgShape
ISvgShape svg = svgShape as ISvgShape;

if (svg != null)
{
    // Appliquer la mise en forme
    svg.FillFormat.SolidFillColor.Color = Color.Red;
    svg.LineFormat.Width = 2.0;
    svg.LineFormat.DashStyle = LineDashStyle.DashDot;
    
    // Autres options de formatage
    //svg.LineFormat.FillFormat.SolidFillColor.Color = Couleur.Bleu;
    // svg.LineFormat.Style = LineStyle.ThickBetweenThin;
}
```

## 6. Enregistrez la présentation
Enregistrez la présentation modifiée avec la forme SVG formatée.

```csharp
string outputPath = "output_path.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

## FAQ

### Comment puis-je installer Aspose.Slides pour .NET ?
 Vous pouvez télécharger et installer la bibliothèque Aspose.Slides pour .NET à partir de la page des versions :[Téléchargez Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/)

### Comment charger une présentation existante à l’aide d’Aspose.Slides ?
 Vous pouvez charger une présentation en utilisant le`Presentation` classe. Voici un exemple :
```csharp
using Aspose.Slides;

string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Votre code ici
}
```

### Comment appliquer le formatage à une forme SVG ?
 Vous pouvez formater une forme SVG à l'aide de l'outil`ISvgShape` interface. Voici un exemple d'application du formatage :
```csharp
IShape svgShape = slide.Shapes[0]; // Accéder à la forme SVG
ISvgShape svg = svgShape as ISvgShape; // Caster vers ISvgShape

if (svg != null)
{
    svg.FillFormat.SolidFillColor.Color = Color.Red; // Définir la couleur de remplissage
    svg.LineFormat.Width = 2.0; // Définir la largeur de la ligne
    svg.LineFormat.DashStyle = LineDashStyle.DashDot; // Définir le style de tiret de ligne
    // Autres options de formatage
}
```

### Comment enregistrer la présentation modifiée ?
 Vous pouvez enregistrer la présentation modifiée à l'aide du`Save` méthode. Voici un exemple :
```csharp
string outputPath = "output_path.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

 Pour des informations et des options plus détaillées, reportez-vous au[Aspose.Slides pour la référence de l'API .NET](https://reference.aspose.com/slides/net/).

## Conclusion
Dans ce guide, vous avez appris à formater des formes SVG dans des présentations à l'aide d'Aspose.Slides pour .NET. Vous avez exploré le chargement de présentations, l'accès aux formes SVG, l'application du formatage et l'enregistrement de la présentation modifiée. Aspose.Slides for .NET fournit un ensemble complet d'outils pour travailler avec des présentations par programmation, vous permettant de contrôler chaque aspect de vos diapositives.
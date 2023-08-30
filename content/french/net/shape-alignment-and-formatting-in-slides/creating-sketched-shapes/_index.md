---
title: Création de formes esquissées dans des diapositives de présentation avec Aspose.Slides
linktitle: Création de formes esquissées dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à créer des diapositives de présentation captivantes avec des formes esquissées à l'aide d'Aspose.Slides pour .NET. Suivez ce guide étape par étape avec le code source complet pour ajouter des éléments personnalisés et créatifs à vos diapositives.
type: docs
weight: 13
url: /fr/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

## Introduction à la création de formes esquissées dans les diapositives de présentation

Les diapositives de présentation sont un outil puissant pour transmettre des informations visuellement. Parfois, vous souhaiterez peut-être ajouter une touche personnelle à vos diapositives en incorporant des formes esquissées, ce qui peut rendre vos présentations plus attrayantes et créatives. Dans ce guide étape par étape, nous explorerons comment y parvenir à l'aide de la bibliothèque Aspose.Slides pour .NET. À la fin de ce didacticiel, vous serez en mesure de créer des diapositives de présentation avec des formes esquissées qui se démarquent. Allons-y !

## Mise en place du projet

 Avant de commencer, assurez-vous que l'environnement de développement .NET est configuré sur votre ordinateur. Vous pouvez télécharger la dernière version d’Aspose.Slides depuis le site Web[ici](https://releases.aspose.com/slides/net/). Une fois téléchargée, installez la bibliothèque dans votre projet.

## Créer une nouvelle présentation

Commençons par créer une nouvelle présentation à l'aide d'Aspose.Slides. Voici comment procéder :

```csharp
using Aspose.Slides;

// Créer une nouvelle présentation
Presentation presentation = new Presentation();
```

## Ajout de formes esquissées

Pour ajouter des formes esquissées à vos diapositives, vous pouvez utiliser des formes libres disponibles dans Aspose.Slides. Ces formes peuvent être personnalisées pour ressembler à des croquis dessinés à la main. Voici un exemple de comment ajouter un rectangle esquissé à une diapositive :

```csharp
// Accédez à la première diapositive
ISlide slide = presentation.Slides[0];

// Définir les points du rectangle esquissé
PointF[] points = new PointF[]
{
    new PointF(100, 100),
    new PointF(200, 100),
    new PointF(200, 200),
    new PointF(100, 200)
};

// Ajouter une forme libre à la diapositive
IFreeformShape freeformShape = slide.Shapes.AddFreeform(ShapeType.Rectangle, points);

// Personnaliser l'apparence de la forme esquissée
freeformShape.LineFormat.Style = LineStyle.Single;
freeformShape.LineFormat.Width = 2;
freeformShape.FillFormat.FillType = FillType.Solid;
freeformShape.FillFormat.SolidFillColor.Color = Color.LightGray;
```

## Personnalisation des formes esquissées

Vous pouvez personnaliser davantage les formes esquissées en ajustant leurs couleurs, leurs styles de ligne et d'autres propriétés. Expérimentez avec différents réglages pour obtenir l’effet dessiné à la main souhaité.

## Enregistrement et exportation de la présentation

Une fois que vous avez ajouté des formes esquissées à votre présentation, vous pouvez l'enregistrer et l'exporter vers différents formats, tels que PPTX ou PDF. Voici comment procéder :

```csharp
// Enregistrer la présentation dans un fichier
presentation.Save("SketchedShapesPresentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment créer des diapositives de présentation avec des formes esquissées à l'aide d'Aspose.Slides pour .NET. En ajoutant des formes esquissées à vos diapositives, vous pouvez ajouter une touche créative et personnalisée à vos présentations, les rendant plus attrayantes pour votre public. N'hésitez pas à expérimenter différentes formes et options de personnalisation pour créer des diapositives visuellement attrayantes qui laissent un impact durable.

## FAQ

### Comment puis-je télécharger Aspose.Slides pour .NET ?

 Vous pouvez télécharger la dernière version d'Aspose.Slides pour .NET à partir de leur page de versions[ici](https://releases.aspose.com/slides/net/).

### Puis-je personnaliser l’apparence des formes esquissées ?

Oui, vous pouvez personnaliser l'apparence des formes esquissées en ajustant leurs couleurs, leurs styles de ligne et d'autres propriétés à l'aide d'Aspose.Slides.

### Aspose.Slides convient-il aussi bien aux développeurs débutants qu’expérimentés ?

Oui, Aspose.Slides fournit une API conviviale qui convient aussi bien aux développeurs débutants qu'expérimentés. Il propose une documentation complète pour vous aider à démarrer.

### Puis-je exporter ma présentation avec des formes esquissées au format PDF ?

Absolument! Vous pouvez exporter votre présentation avec des formes esquissées vers différents formats, y compris PDF, à l'aide des options d'exportation fournies par Aspose.Slides.

### Comment puis-je ajouter d’autres types de formes esquissées, telles que des cercles ou des lignes ?

 Vous pouvez ajouter d'autres types de formes esquissées, telles que des cercles ou des lignes, en modifiant les points et le type de forme dans la fenêtre`AddFreeform` méthode. Expérimentez avec différentes configurations de points pour créer les formes souhaitées.
---
title: Maîtriser les visuels – Ajout de segments avec Aspose.Slides dans .NET
linktitle: Ajout de segments à la forme géométrique dans la présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos applications .NET avec Aspose.Slides. Ce didacticiel vous guide dans l'ajout de segments aux formes géométriques pour des présentations captivantes.
type: docs
weight: 13
url: /fr/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---
## Introduction
Dans le monde du développement .NET, la création de présentations visuellement attrayantes est une exigence courante. Aspose.Slides for .NET est une bibliothèque puissante qui facilite l'intégration transparente de fonctionnalités robustes de création de présentations dans vos applications .NET. Ce didacticiel se concentre sur un aspect spécifique de la conception de présentation : l'ajout de segments aux formes géométriques.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Connaissance de base du langage de programmation C#.
- Visual Studio installé sur votre ordinateur.
- Bibliothèque Aspose.Slides pour .NET téléchargée et référencée dans votre projet.
## Importer des espaces de noms
Dans votre code C#, assurez-vous d'importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Slides. Ajoutez les lignes suivantes à votre code :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Maintenant, décomposons l'exemple en plusieurs étapes.
## Étape 1 : Configurez votre projet
Commencez par créer un nouveau projet C# dans Visual Studio. Assurez-vous que la bibliothèque Aspose.Slides est référencée dans votre projet.
## Étape 2 : Créer une présentation
Initialisez un nouvel objet de présentation à l'aide de la bibliothèque Aspose.Slides. Cela servira de canevas pour votre forme géométrique.
```csharp
using (Presentation pres = new Presentation())
{
    // Votre code pour créer une présentation va ici
}
```
## Étape 3 : ajouter une forme géométrique
Créez une forme géométrique dans la présentation. Par exemple, ajoutons un rectangle à la première diapositive.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Étape 4 : obtenir le chemin géométrique
Récupérez le chemin géométrique de la forme créée pour manipuler ses segments.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## Étape 5 : Ajouter des segments
Ajoutez des segments (lignes) au chemin géométrique. Dans cet exemple, deux lignes sont ajoutées au chemin.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Étape 6 : attribuer un chemin de géométrie modifié
Attribuez le chemin de géométrie modifié à la forme pour appliquer les modifications.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Étape 7 : Enregistrez la présentation
Enregistrez la présentation modifiée à l'emplacement souhaité.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Grâce à ces étapes, vous avez réussi à ajouter des segments à une forme géométrique dans une présentation à l’aide d’Aspose.Slides pour .NET.
## Conclusion
Aspose.Slides pour .NET permet aux développeurs d'améliorer leurs applications grâce à des capacités avancées de création de présentations. L'ajout de segments aux formes géométriques permet de personnaliser les éléments visuels de vos présentations.
### Questions fréquemment posées
### Puis-je ajouter différents types de formes à l’aide d’Aspose.Slides ?
Oui, Aspose.Slides prend en charge différents types de formes, notamment les rectangles, les cercles et les formes géométriques personnalisées.
### Une licence est-elle requise pour utiliser Aspose.Slides dans mon projet ?
Oui, une licence valide est nécessaire. Vous pouvez obtenir une licence temporaire à des fins de test ou acheter une licence complète pour la production.
### Comment puis-je obtenir de l'aide pour les requêtes liées à Aspose.Slides ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.
### Existe-t-il d'autres didacticiels disponibles pour Aspose.Slides ?
 Explore le[Documentation](https://reference.aspose.com/slides/net/) pour des guides et des exemples complets.
### Puis-je essayer Aspose.Slides gratuitement avant d’acheter ?
 Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).
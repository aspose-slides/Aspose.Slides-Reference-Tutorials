---
"description": "Améliorez vos présentations avec Aspose.Slides pour .NET ! Apprenez pas à pas à remplir des formes avec des dégradés. Téléchargez votre essai gratuit dès maintenant !"
"linktitle": "Remplissage de formes avec un dégradé dans les diapositives de présentation avec Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Créez de superbes dégradés dans PowerPoint avec Aspose.Slides"
"url": "/fr/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Créez de superbes dégradés dans PowerPoint avec Aspose.Slides

## Introduction
Créer des diapositives de présentation visuellement captivantes est essentiel pour capter et maintenir l'attention de votre public. Dans ce tutoriel, nous vous expliquerons comment améliorer vos diapositives en remplissant une ellipse avec un dégradé à l'aide d'Aspose.Slides pour .NET.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
- Connaissances de base du langage de programmation C#.
- Visual Studio installé sur votre machine.
- Bibliothèque Aspose.Slides pour .NET. Téléchargez-la. [ici](https://releases.aspose.com/slides/net/).
- Un répertoire de projet pour organiser vos fichiers.
## Importer des espaces de noms
Dans votre projet C#, incluez les espaces de noms requis pour Aspose.Slides :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Étape 1 : Créer une présentation
Commencez par créer une nouvelle présentation à l’aide de la bibliothèque Aspose.Slides :
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Votre code va ici...
}
```
## Étape 2 : ajouter une forme d’ellipse
Insérez une forme d’ellipse dans la première diapositive de votre présentation :
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Étape 3 : Appliquer le formatage du dégradé
Spécifiez que la forme doit être remplie avec un dégradé et définissez les caractéristiques du dégradé :
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Étape 4 : ajouter des arrêts de dégradé
Définissez les couleurs et les positions des arrêts du dégradé :
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Étape 5 : Enregistrer la présentation
Enregistrez votre présentation avec la forme remplie de dégradé nouvellement ajoutée :
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Répétez ces étapes dans votre code C#, en respectant la séquence et les valeurs des paramètres. Vous obtiendrez ainsi un fichier de présentation avec une forme d'ellipse visuellement attrayante, remplie d'un dégradé.
## Conclusion
Avec Aspose.Slides pour .NET, améliorez facilement l'esthétique de vos présentations. En suivant ce guide, vous avez appris à remplir des formes avec des dégradés, donnant à vos diapositives un aspect professionnel et attrayant.
---
## FAQ
### Q : Puis-je appliquer des dégradés à des formes autres que des ellipses ?
R : Certainement ! Aspose.Slides pour .NET prend en charge le remplissage en dégradé pour diverses formes telles que les rectangles, les polygones, etc.
### Q : Où puis-je trouver des exemples supplémentaires et une documentation détaillée ?
A : Explorez le [Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/) pour des guides et des exemples complets.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
R : Oui, vous pouvez accéder à un essai gratuit [ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir de l’aide pour Aspose.Slides pour .NET ?
A : Demandez de l'aide et engagez-vous auprès de la communauté sur le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Q : Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?
R : Certainement, vous pouvez obtenir un permis temporaire [ici](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
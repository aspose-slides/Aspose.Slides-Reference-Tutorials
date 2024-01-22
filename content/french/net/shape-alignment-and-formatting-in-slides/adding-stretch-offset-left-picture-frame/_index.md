---
title: Ajout d'un décalage d'étirement vers la gauche dans PowerPoint avec Aspose.Slide
linktitle: Ajout d'un décalage d'étirement vers la gauche pour le cadre photo dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer les présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Suivez notre guide étape par étape pour ajouter un décalage d'étirement vers la gauche pour les cadres photo.
type: docs
weight: 14
url: /fr/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## Introduction
Aspose.Slides pour .NET est une bibliothèque puissante qui permet aux développeurs de manipuler facilement des présentations PowerPoint. Dans ce didacticiel, nous explorerons le processus d'ajout d'un décalage d'étirement vers la gauche pour un cadre photo à l'aide d'Aspose.Slides pour .NET. Suivez ce guide étape par étape pour améliorer vos compétences dans l'utilisation d'images et de formes dans des présentations PowerPoint.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Aspose.Slides pour .NET : assurez-vous que la bibliothèque est installée. Sinon, téléchargez-le depuis le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).
- Environnement de développement : disposer d'un environnement de développement fonctionnel avec des capacités .NET.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet .NET :
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Étape 1 : Configurez votre projet
Créez un nouveau projet ou ouvrez-en un existant. Assurez-vous que la bibliothèque Aspose.Slides est référencée dans votre projet.
## Étape 2 : Créer un objet de présentation
 Instancier le`Presentation` classe, représentant le fichier PPTX :
```csharp
using (Presentation pres = new Presentation())
{
    // Votre code pour les étapes suivantes ira ici.
}
```
## Étape 3 : Obtenez la première diapositive
Récupérez la première diapositive de la présentation :
```csharp
ISlide slide = pres.Slides[0];
```
## Étape 4 : Instancier l'image
Chargez l'image que vous souhaitez utiliser :
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Étape 5 : ajouter une forme automatique rectangulaire
Créez une forme automatique de type Rectangle :
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Étape 6 : Définir le type de remplissage et le mode de remplissage de l'image
Configurez le type de remplissage de la forme et le mode de remplissage de l'image :
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Étape 7 : définir l'image pour remplir la forme
Spécifiez l'image pour remplir la forme :
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Étape 8 : Spécifier les décalages d'étirement
Définissez les décalages de l'image par rapport aux bords correspondants du cadre de délimitation de la forme :
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Étape 9 : Enregistrez la présentation
Écrivez le fichier PPTX sur le disque :
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Toutes nos félicitations! Vous avez ajouté avec succès un décalage d'étirement vers la gauche pour un cadre photo à l'aide d'Aspose.Slides pour .NET.
## Conclusion
Dans ce didacticiel, nous avons exploré le processus de manipulation des cadres d'image dans des présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. En suivant le guide étape par étape, vous avez acquis des connaissances sur l'utilisation d'images, de formes et de décalages.
## Questions fréquemment posées
### Q : Puis-je appliquer des décalages d'étirement à d'autres formes que les rectangles ?
R : Bien que ce didacticiel se concentre sur les rectangles, les décalages d'étirement peuvent être appliqués à diverses formes prises en charge par Aspose.Slides.
### Q : Comment puis-je ajuster les décalages d’étirement pour différents effets ?
R : Expérimentez avec différentes valeurs de décalage pour obtenir l'impact visuel souhaité. Ajustez les valeurs en fonction de vos besoins spécifiques.
### Q : Aspose.Slides est-il compatible avec le dernier framework .NET ?
R : Aspose.Slides est régulièrement mis à jour pour garantir la compatibilité avec les dernières versions du framework .NET.
### Q : Où puis-je trouver des exemples et des ressources supplémentaires pour Aspose.Slides ?
 R : Explorez le[Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) pour des exemples et des conseils complets.
### Q : Puis-je appliquer plusieurs décalages d’étirement à une seule forme ?
R : Oui, vous pouvez combiner plusieurs décalages d'étirement pour obtenir des effets visuels complexes et personnalisés.
---
"description": "Apprenez à améliorer vos présentations PowerPoint avec Aspose.Slides pour .NET. Suivez notre guide étape par étape pour ajouter un décalage d'étirement à gauche pour les cadres d'image."
"linktitle": "Ajout d'un décalage d'étirement à gauche pour le cadre photo dans Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Ajout d'un décalage d'étirement à gauche dans PowerPoint avec Aspose.Slide"
"url": "/fr/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajout d'un décalage d'étirement à gauche dans PowerPoint avec Aspose.Slide

## Introduction
Aspose.Slides pour .NET est une bibliothèque puissante qui permet aux développeurs de manipuler facilement les présentations PowerPoint. Dans ce tutoriel, nous explorerons le processus d'ajout d'un décalage d'étirement à gauche pour un cadre d'image avec Aspose.Slides pour .NET. Suivez ce guide étape par étape pour améliorer vos compétences en manipulation d'images et de formes dans les présentations PowerPoint.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Aspose.Slides pour .NET : Assurez-vous que la bibliothèque est installée. Sinon, téléchargez-la depuis le [Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).
- Environnement de développement : Disposez d’un environnement de développement fonctionnel avec des fonctionnalités .NET.
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
Instancier le `Presentation` classe, représentant le fichier PPTX :
```csharp
using (Presentation pres = new Presentation())
{
    // Votre code pour les étapes suivantes ira ici.
}
```
## Étape 3 : Obtenez la première diapositive
Récupérer la première diapositive de la présentation :
```csharp
ISlide slide = pres.Slides[0];
```
## Étape 4 : instancier l'image
Chargez l'image que vous souhaitez utiliser :
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Étape 5 : Ajouter une forme automatique rectangulaire
Créer une forme automatique de type Rectangle :
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Étape 6 : Définir le type de remplissage et le mode de remplissage de l'image
Configurez le type de remplissage de la forme et le mode de remplissage de l'image :
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Étape 7 : Définir l'image pour remplir la forme
Spécifiez l'image pour remplir la forme :
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Étape 8 : Spécifier les décalages d'étirement
Définissez les décalages de l'image à partir des bords correspondants du cadre de délimitation de la forme :
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Étape 9 : Enregistrer la présentation
Écrivez le fichier PPTX sur le disque :
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Félicitations ! Vous avez ajouté avec succès un décalage d'étirement à gauche pour un cadre photo avec Aspose.Slides pour .NET.
## Conclusion
Dans ce tutoriel, nous avons exploré la manipulation des cadres d'image dans les présentations PowerPoint avec Aspose.Slides pour .NET. En suivant ce guide étape par étape, vous avez appris à manipuler les images, les formes et les décalages.
## Questions fréquemment posées
### Q : Puis-je appliquer des décalages d’étirement à d’autres formes en plus des rectangles ?
R : Bien que ce didacticiel se concentre sur les rectangles, les décalages d’étirement peuvent être appliqués à diverses formes prises en charge par Aspose.Slides.
### Q : Comment puis-je ajuster les décalages d’étirement pour différents effets ?
A : Expérimentez différentes valeurs de décalage pour obtenir l'impact visuel souhaité. Ajustez les valeurs selon vos besoins spécifiques.
### Q : Aspose.Slides est-il compatible avec le dernier framework .NET ?
: Aspose.Slides est régulièrement mis à jour pour garantir la compatibilité avec les dernières versions du framework .NET.
### Q : Où puis-je trouver des exemples et des ressources supplémentaires pour Aspose.Slides ?
A : Explorez le [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) pour des exemples complets et des conseils.
### Q : Puis-je appliquer plusieurs décalages d’étirement à une seule forme ?
R : Oui, vous pouvez combiner plusieurs décalages d’étirement pour obtenir des effets visuels complexes et personnalisés.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
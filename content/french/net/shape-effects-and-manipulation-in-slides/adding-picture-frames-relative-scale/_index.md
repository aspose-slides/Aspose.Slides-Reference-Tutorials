---
title: Ajout de cadres photo avec une hauteur d'échelle relative dans Aspose.Slides
linktitle: Ajout de cadres photo avec une hauteur d'échelle relative dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos présentations en ajoutant des cadres photo avec une hauteur d'échelle relative à l'aide d'Aspose.Slides pour .NET. Créez sans effort des diapositives visuellement attrayantes.
type: docs
weight: 17
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

## Introduction

Dans le monde dynamique des présentations, les éléments visuels jouent un rôle central dans la transmission efficace des informations. Aspose.Slides pour .NET vous permet d'aller au-delà des bases et d'améliorer vos présentations en incorporant des cadres photo avec une hauteur d'échelle relative. Ce guide vous guidera pas à pas tout au long du processus, vous fournissant les compétences nécessaires pour créer des diapositives visuellement captivantes et qui se démarquent. Que vous soyez un développeur chevronné ou que vous débutiez tout juste avec Aspose.Slides, ce guide vous aidera à maîtriser l'art de l'ajout de cadres photo avec une hauteur d'échelle relative.

## Ajout de cadres photo avec une hauteur d'échelle relative dans Aspose.Slides

Lorsqu'il s'agit d'ajouter des cadres photo avec une hauteur d'échelle relative dans Aspose.Slides, le processus est remarquablement intuitif. Suivez ces étapes pour améliorer vos présentations :

### Étape 1 : initialiser la présentation

Commencez par initialiser l'objet de présentation à l'aide du code suivant :

```csharp
Presentation presentation = new Presentation();
```

### Étape 2 : ajouter une diapositive

Pour ajouter une nouvelle diapositive, utilisez l'extrait de code suivant :

```csharp
ISlide slide = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
```

### Étape 3 : Insérer une image

Il est maintenant temps d'insérer l'image dans la diapositive. Le code suivant montre comment y parvenir :

```csharp
byte[] imageBytes = File.ReadAllBytes("image.jpg");
IPPImage image = presentation.Images.AddImage(imageBytes);
slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, image.Width, image.Height, image);
```

### Étape 4 : Ajuster la hauteur de l'échelle

Pour créer une hauteur d'échelle relative pour le cadre photo, utilisez l'extrait de code ci-dessous :

```csharp
IPictureFrame pictureFrame = (IPictureFrame)slide.Shapes[0];
pictureFrame.PictureFormat.Picture.ImageScale.HeightScale = 50; // Ajustez le pourcentage d’échelle comme vous le souhaitez
```

## FAQ

### Comment puis-je modifier la hauteur de l'échelle du cadre photo ?

 Pour modifier la hauteur de l'échelle du cadre photo, vous pouvez utiliser le`PictureFormat.Picture.ImageScale.HeightScale` propriété et attribuez-lui une valeur de pourcentage souhaitée.

### Puis-je ajouter plusieurs cadres photo à une seule diapositive ?

Oui, vous pouvez ajouter plusieurs cadres photo à une seule diapositive en suivant les étapes mentionnées précédemment pour chaque cadre photo que vous souhaitez insérer.

### Est-il possible d'animer les cadres photo dans une présentation ?

Absolument! Aspose.Slides offre de puissantes capacités d'animation. Vous pouvez appliquer des animations aux cadres d'image à l'aide de divers effets d'animation disponibles dans la bibliothèque.

### Quels formats d'image sont pris en charge pour l'insertion ?

Aspose.Slides prend en charge une large gamme de formats d'image, notamment JPEG, PNG, GIF, BMP, etc. Vous pouvez insérer en toute transparence des images de ces formats dans vos diapositives.

### Comment puis-je définir la position du cadre photo sur la diapositive ?

 Vous pouvez définir la position du cadre photo en spécifiant les coordonnées X et Y lors de l'ajout du cadre photo à l'aide du`slide.Shapes.AddPictureFrame` méthode.

### Est-il possible de personnaliser l'apparence du cadre photo ?

Oui, vous pouvez personnaliser l'apparence du cadre photo à l'aide de propriétés telles que la couleur de la bordure, la couleur de remplissage, etc. Reportez-vous à la documentation Aspose.Slides pour des informations détaillées.

## Conclusion

L'intégration de cadres photo avec une hauteur relative dans vos présentations peut grandement améliorer leur attrait visuel et leur engagement. Avec Aspose.Slides pour .NET, le processus devient simple et personnalisable, vous permettant de créer de superbes diapositives qui laissent un impact durable. Que vous créiez du contenu éducatif, des présentations commerciales ou des vitrines créatives, la maîtrise de cette fonctionnalité améliorera sans aucun doute votre jeu de présentation.

N'oubliez pas que la clé réside dans l'expérimentation et la créativité. En exploitant la puissance d'Aspose.Slides, vous ne vous contentez pas de créer des diapositives ; vous créez des expériences immersives pour votre public.
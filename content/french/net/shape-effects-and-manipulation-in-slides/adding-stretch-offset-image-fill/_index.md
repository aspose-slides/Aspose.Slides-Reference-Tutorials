---
title: Ajout d'un décalage d'étirement pour le remplissage d'image dans les diapositives avec Aspose.Slides
linktitle: Ajout d'un décalage d'étirement pour le remplissage d'image dans les diapositives
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape couvre l'ajout d'un décalage d'étirement pour le remplissage de l'image, la création de visuels dynamiques et l'optimisation de la conception.
type: docs
weight: 18
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

Dans les présentations modernes, les visuels jouent un rôle crucial dans la transmission efficace des messages. Aspose.Slides, une API puissante pour travailler avec des fichiers de présentation dans .NET, propose une fonctionnalité appelée « Stretch Offset » qui vous permet de contrôler avec précision la façon dont les images sont remplies dans les formes. Cet article vous guidera tout au long du processus d'ajout d'un décalage d'étirement pour le remplissage d'images dans les diapositives de présentation à l'aide d'Aspose.Slides pour .NET.

## Introduction au décalage d'étirement

Stretch Offset est une technique précieuse lorsque vous devez personnaliser la façon dont les images sont affichées dans les formes. Il vous permet de contrôler la position et l'alignement de l'image dans une forme, permettant ainsi des conceptions de diapositives créatives et visuellement attrayantes. En utilisant l'API Aspose.Slides, vous pouvez implémenter par programme le décalage d'étirement et donner vie à vos présentations.

## Configuration de votre environnement de développement

 Avant de plonger dans l’implémentation, assurez-vous que Aspose.Slides pour .NET est installé dans votre environnement de développement. Vous pouvez le télécharger sur le site Aspose[lien de téléchargement](https://releases.aspose.com/slides/net/)Une fois téléchargé, suivez les instructions d'installation pour configurer l'API de votre projet.

## Ajouter une image à une diapositive

Pour démontrer la fonctionnalité de décalage d'étirement, commençons par ajouter une image à une diapositive à l'aide d'Aspose.Slides. L'extrait de code suivant montre comment y parvenir :

```csharp
// Instancier un objet Présentation
Presentation presentation = new Presentation();

// Accédez à la première diapositive
ISlide slide = presentation.Slides[0];

// Définir le chemin du fichier image
string imagePath = "path_to_your_image.jpg";

// Ajouter une image à la diapositive
byte[] imageBytes = File.ReadAllBytes(imagePath);
IPictureFillFormat pictureFill = slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, 400, 300).FillFormat.PictureFillFormat;
pictureFill.Picture.Image = presentation.Images.AddImage(imageBytes);

// Enregistrez la présentation
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Application du décalage d'étirement aux images

 Maintenant qu’une image est ajoutée à une diapositive, explorons comment lui appliquer un décalage d’étirement. Le décalage d'étirement est contrôlé par deux propriétés :`StretchX` et`StretchY`. Ces propriétés déterminent le décalage de l'image dans la forme, respectivement horizontalement et verticalement.

Voici comment implémenter le décalage d'étirement à l'aide d'Aspose.Slides :

```csharp
// Accéder au format de remplissage d'image
IPictureFillFormat pictureFill = slide.Shapes[0].FillFormat.PictureFillFormat;

// Appliquer le décalage d'étirement
pictureFill.StretchX = 0.5; // Décalage horizontal de 50 %
pictureFill.StretchY = -0.2; // Décalage vertical de -20%
```

Dans cet exemple, nous avons défini un décalage horizontal de 50 % et un décalage vertical de -20 %. La valeur négative du décalage vertical déplace l’image vers le haut dans la forme.

## Ajustement des valeurs de décalage d'étirement

 Trouver les valeurs de décalage d'étirement parfaites peut nécessiter quelques essais et erreurs pour obtenir l'effet visuel souhaité. Ajustez les valeurs de`StretchX` et`StretchY` pour s'adapter à vos préférences de conception et d'alignement. Expérimentez avec des valeurs positives et négatives pour voir comment le placement de l'image change.

## Utilisation du décalage d'étirement avec différentes formes

 Le décalage d'étirement peut être appliqué à différents types de formes, notamment les rectangles, les ellipses, etc. La méthode d'accès au`PictureFillFormat` reste cohérent dans toutes les formes. N'hésitez pas à explorer et expérimenter différentes formes pour créer des compositions de diapositives uniques.

## Techniques avancées et astuces

- Combinez le décalage étiré avec d'autres fonctionnalités de formatage pour des conceptions complexes.
- Utilisez le décalage d'étirement pour mettre en valeur des parties spécifiques d'une image dans une forme.
-  Utiliser le`PictureFillFormat.TileAsTexture`propriété permettant de mosaïquer des images dans des formes au lieu de les étirer.

## Conclusion

L'intégration du décalage étiré pour le remplissage d'images dans les diapositives de présentation à l'aide d'Aspose.Slides ouvre un monde de possibilités créatives. Avec un contrôle précis du positionnement des images, vous pouvez améliorer l'impact visuel de vos présentations. En suivant les étapes décrites dans cet article, vous avez appris à exploiter efficacement cette fonctionnalité.

## FAQ

### Comment puis-je télécharger Aspose.Slides pour .NET ?

 Vous pouvez télécharger Aspose.Slides pour .NET à partir du site Web Aspose.[lien de téléchargement](https://releases.aspose.com/slides/net/).

### Puis-je utiliser le décalage d’étirement avec n’importe quel type d’image ?

Oui, le décalage étiré peut être appliqué à des images de différents formats, notamment JPG, PNG, etc.

###  Que se passe-t-il si je définis les deux`StretchX` and `StretchY` to the same value?

La définition des deux propriétés sur la même valeur permet de conserver les proportions de l'image tout en décalant sa position dans la forme.

### Le décalage d'étirement est-il compatible avec les animations ?

Oui, le décalage étiré fonctionne parfaitement avec les animations de diapositives, vous permettant de créer des présentations dynamiques.

### Comment puis-je accéder aux options avancées de décalage d’étirement ?

Explorez la documentation Aspose.Slides pour obtenir des informations détaillées sur les techniques et propriétés avancées de décalage par étirement.
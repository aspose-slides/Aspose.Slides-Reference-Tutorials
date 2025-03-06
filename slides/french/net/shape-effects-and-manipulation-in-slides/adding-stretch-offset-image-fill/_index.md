---
title: Ajout d'un décalage d'étirement pour le remplissage d'image dans les présentations PowerPoint
linktitle: Ajout d'un décalage d'étirement pour le remplissage d'image dans les diapositives
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer les présentations PowerPoint avec Aspose.Slides pour .NET. Suivez un guide étape par étape pour ajouter un décalage d'étirement pour le remplissage de l'image.
weight: 18
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajout d'un décalage d'étirement pour le remplissage d'image dans les présentations PowerPoint

## Introduction
Dans le monde dynamique des présentations, les visuels jouent un rôle central pour capter l'attention du public. Aspose.Slides pour .NET permet aux développeurs d'améliorer leurs présentations PowerPoint en fournissant un ensemble robuste de fonctionnalités. L'une de ces fonctionnalités est la possibilité d'ajouter un décalage d'étirement pour le remplissage de l'image, permettant ainsi des diapositives créatives et visuellement attrayantes.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Aspose.Slides pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir du[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).
2. Environnement de développement : assurez-vous que vous disposez d'un environnement de développement .NET fonctionnel.
Commençons maintenant par le guide étape par étape.
## Importer des espaces de noms
Tout d'abord, importez les espaces de noms nécessaires pour exploiter la fonctionnalité Aspose.Slides dans votre application .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Étape 1 : Configurez votre projet
Créez un nouveau projet .NET dans votre environnement de développement préféré. Assurez-vous qu’Aspose.Slides pour .NET est correctement référencé.
## Étape 2 : initialiser la classe de présentation
 Instancier le`Presentation` classe pour représenter le fichier PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Votre code va ici
}
```
## Étape 3 : Obtenez la première diapositive
Récupérez la première diapositive de la présentation avec laquelle travailler.
```csharp
ISlide sld = pres.Slides[0];
```
## Étape 4 : Instancier la classe ImageEx
 Créez une instance du`ImageEx`classe pour gérer l’image que vous souhaitez ajouter à la diapositive.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Étape 5 : ajouter un cadre photo
 Utiliser le`AddPictureFrame` méthode pour ajouter un cadre photo à la diapositive. Spécifiez les dimensions et la position du cadre.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Étape 6 : Enregistrez la présentation
Enregistrez la présentation modifiée sur le disque.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
C'est ça! Vous avez ajouté avec succès un décalage d'étirement pour le remplissage d'image dans les diapositives à l'aide d'Aspose.Slides pour .NET.
## Conclusion
Améliorer vos présentations PowerPoint est désormais plus facile que jamais avec Aspose.Slides pour .NET. En suivant ce didacticiel, vous avez appris à intégrer le décalage d'étirement pour le remplissage de l'image, apportant ainsi un nouveau niveau de créativité à vos diapositives.
## FAQ
### Puis-je utiliser Aspose.Slides pour .NET dans mes applications Web ?
Oui, Aspose.Slides pour .NET convient aux applications de bureau et Web.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
 Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l’assistance pour Aspose.Slides pour .NET ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien de la communauté.
### Où puis-je trouver la documentation complète d’Aspose.Slides pour .NET ?
 Se référer au[Documentation](https://reference.aspose.com/slides/net/) pour des informations détaillées.
### Puis-je acheter Aspose.Slides pour .NET ?
 Oui, vous pouvez acheter le produit[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

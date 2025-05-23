---
"description": "Découvrez comment améliorer vos présentations PowerPoint avec Aspose.Slides pour .NET. Suivez un guide étape par étape pour ajouter un décalage d'étirement au remplissage de l'image."
"linktitle": "Ajout d'un décalage d'étirement pour le remplissage d'image dans les diapositives"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Ajout d'un décalage d'étirement pour le remplissage d'image dans les présentations PowerPoint"
"url": "/fr/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajout d'un décalage d'étirement pour le remplissage d'image dans les présentations PowerPoint

## Introduction
Dans l'univers dynamique des présentations, les visuels jouent un rôle essentiel pour capter l'attention du public. Aspose.Slides pour .NET permet aux développeurs d'améliorer leurs présentations PowerPoint grâce à un ensemble de fonctionnalités performantes. L'une d'elles est la possibilité d'ajouter un décalage d'étirement pour le remplissage des images, permettant ainsi de créer des diapositives créatives et visuellement attrayantes.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
1. Bibliothèque Aspose.Slides pour .NET : téléchargez et installez la bibliothèque à partir du [Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).
2. Environnement de développement : assurez-vous que vous disposez d’un environnement de développement .NET fonctionnel.
Maintenant, commençons par le guide étape par étape.
## Importer des espaces de noms
Tout d’abord, importez les espaces de noms nécessaires pour exploiter la fonctionnalité Aspose.Slides dans votre application .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Étape 1 : Configurez votre projet
Créez un projet .NET dans votre environnement de développement préféré. Assurez-vous qu'Aspose.Slides pour .NET est correctement référencé.
## Étape 2 : Initialiser la classe de présentation
Instancier le `Presentation` classe pour représenter le fichier PowerPoint.
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
## Étape 4 : instancier la classe ImageEx
Créer une instance de `ImageEx` classe pour gérer l'image que vous souhaitez ajouter à la diapositive.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Étape 5 : Ajouter un cadre photo
Utilisez le `AddPictureFrame` Méthode pour ajouter un cadre photo à la diapositive. Spécifiez les dimensions et la position du cadre.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Étape 6 : Enregistrer la présentation
Enregistrez la présentation modifiée sur le disque.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Et voilà ! Vous avez ajouté avec succès un décalage d'étirement pour le remplissage d'image dans les diapositives avec Aspose.Slides pour .NET.
## Conclusion
Améliorer vos présentations PowerPoint est désormais plus facile que jamais avec Aspose.Slides pour .NET. En suivant ce tutoriel, vous avez appris à intégrer le décalage d'étirement pour le remplissage des images, apportant ainsi une nouvelle dimension créative à vos diapositives.
## FAQ
### Puis-je utiliser Aspose.Slides pour .NET dans mes applications Web ?
Oui, Aspose.Slides pour .NET convient aux applications de bureau et Web.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?
Visitez le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien de la communauté.
### Où puis-je trouver la documentation complète d'Aspose.Slides pour .NET ?
Se référer à la [documentation](https://reference.aspose.com/slides/net/) pour des informations détaillées.
### Puis-je acheter Aspose.Slides pour .NET ?
Oui, vous pouvez acheter le produit [ici](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
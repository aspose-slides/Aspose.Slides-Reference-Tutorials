---
title: Création de formes rectangulaires avec Aspose.Slides pour .NET
linktitle: Création d'une forme rectangulaire simple dans des diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Explorez le monde des présentations PowerPoint dynamiques avec Aspose.Slides pour .NET. Apprenez à créer des formes rectangulaires attrayantes dans des diapositives avec ce guide étape par étape.
weight: 12
url: /fr/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Si vous souhaitez améliorer vos applications .NET avec des présentations PowerPoint dynamiques et visuellement attrayantes, Aspose.Slides for .NET est votre solution incontournable. Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'une forme de rectangle simple dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
- Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur de développement.
-  Aspose.Slides pour .NET : téléchargez et installez la bibliothèque Aspose.Slides pour .NET à partir de[ici](https://releases.aspose.com/slides/net/).
- Connaissances de base en C# : Une connaissance du langage de programmation C# est essentielle.
## Importer des espaces de noms
Dans votre projet C#, commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Slides :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Étape 1 : configurer le projet
Commencez par créer un nouveau projet C# dans Visual Studio. Assurez-vous qu'Aspose.Slides for .NET est correctement référencé dans votre projet.
## Étape 2 : initialiser l'objet de présentation
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Votre code pour les prochaines étapes sera ici.
}
```
## Étape 3 : Obtenez la première diapositive
```csharp
ISlide sld = pres.Slides[0];
```
## Étape 4 : ajouter une forme automatique rectangulaire
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Ce code ajoute une forme de rectangle aux coordonnées (50, 150) avec une largeur de 150 et une hauteur de 50.
## Étape 5 : Enregistrez la présentation
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Cette étape enregistre la présentation avec la forme rectangulaire ajoutée dans le répertoire spécifié.
## Conclusion
Toutes nos félicitations! Vous avez réussi à créer une forme de rectangle simple dans une diapositive de présentation à l'aide d'Aspose.Slides pour .NET. Ce n'est que le début – Aspose.Slides offre un large éventail de fonctionnalités pour personnaliser et améliorer davantage vos présentations.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Slides pour .NET dans les environnements Windows et Linux ?
Oui, Aspose.Slides pour .NET est indépendant de la plate-forme et peut être utilisé dans les environnements Windows et Linux.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
 Oui, vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l’assistance pour Aspose.Slides pour .NET ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien de la communauté.
### Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?
 Oui, vous pouvez acheter une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver la documentation d’Aspose.Slides pour .NET ?
 Se référer à la documentation[ici](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

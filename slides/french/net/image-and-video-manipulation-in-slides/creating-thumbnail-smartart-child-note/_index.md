---
title: Création d'une vignette pour la note enfant SmartArt dans Aspose.Slides
linktitle: Création d'une vignette pour la note enfant SmartArt dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment créer des vignettes SmartArt Child Note captivantes à l’aide d’Aspose.Slides pour .NET. Élevez vos présentations avec des visuels dynamiques !
weight: 15
url: /fr/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Création d'une vignette pour la note enfant SmartArt dans Aspose.Slides

## Introduction
Dans le domaine des présentations dynamiques, Aspose.Slides pour .NET se distingue comme un outil puissant, offrant aux développeurs la possibilité de manipuler et d'améliorer les présentations PowerPoint par programme. Une fonctionnalité intéressante est la possibilité de générer des vignettes pour SmartArt Child Notes, ajoutant ainsi une couche d'attrait visuel à vos présentations. Ce guide étape par étape vous guidera tout au long du processus de création de vignettes pour SmartArt Child Notes à l'aide d'Aspose.Slides pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides est intégrée à votre projet .NET. Sinon, téléchargez-le depuis le[page des versions](https://releases.aspose.com/slides/net/).
- Environnement de développement : mettre en place un environnement de développement .NET fonctionnel et avoir une compréhension de base de la programmation C#.
- Exemple de présentation : créez ou obtenez une présentation PowerPoint contenant SmartArt avec Child Notes à des fins de test.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet C#. Ces espaces de noms donnent accès aux classes et méthodes nécessaires pour travailler avec Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Étape 1 : Instancier un cours de présentation
 Commencez par instancier le`Presentation` classe, représentant le fichier PPTX avec lequel vous allez travailler.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Étape 2 : Ajouter un SmartArt
 Maintenant, ajoutez SmartArt à une diapositive dans la présentation. Dans cet exemple, nous utilisons le`BasicCycle` mise en page.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Étape 3 : Obtenir la référence du nœud
Pour travailler avec un nœud spécifique dans le SmartArt, obtenez sa référence à l'aide de son index.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Étape 4 : Obtenir une vignette
Récupérez l’image miniature de la note enfant dans le nœud SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Étape 5 : Enregistrer la vignette
Enregistrez l'image miniature générée dans un répertoire spécifié.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Répétez ces étapes pour chaque nœud SmartArt de votre présentation, en personnalisant la mise en page et les styles selon vos besoins.
## Conclusion
En conclusion, Aspose.Slides pour .NET permet aux développeurs de créer facilement des présentations attrayantes. La possibilité de générer des vignettes pour SmartArt Child Notes améliore l'attrait visuel de vos présentations, offrant une expérience utilisateur dynamique et interactive.
## Questions fréquemment posées
### Q : Puis-je personnaliser la taille et le format de la vignette générée ?
R : Oui, vous pouvez ajuster les dimensions et le format de la vignette en modifiant les paramètres correspondants dans le code.
### Q : Aspose.Slides prend-il en charge d’autres mises en page SmartArt ?
R : Absolument ! Aspose.Slides propose une variété de mises en page SmartArt, vous permettant de choisir celle qui correspond le mieux à vos besoins de présentation.
### Q : Une licence temporaire est-elle disponible à des fins de test ?
 R : Oui, vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/) pour les tests et l'évaluation.
### Q : Où puis-je demander de l'aide ou me connecter à la communauté Aspose.Slides ?
 R : Visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour interagir avec la communauté, poser des questions et trouver des solutions.
### Q : Puis-je acheter Aspose.Slides pour .NET ?
 R : Certainement ! Explorez les options d'achat[ici](https://purchase.aspose.com/buy) pour libérer tout le potentiel d’Aspose.Slides dans vos projets.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

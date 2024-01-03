---
title: Créez facilement une forme d'ellipse avec Aspose.Slides .NET
linktitle: Création d'une forme d'ellipse simple dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à créer de superbes formes d'ellipse dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Des étapes faciles pour un design dynamique !
type: docs
weight: 11
url: /fr/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---
## Introduction
Dans le monde dynamique de la conception de présentations, l’incorporation de formes telles que des ellipses peut ajouter une touche de créativité et de professionnalisme. Aspose.Slides pour .NET offre une solution puissante pour manipuler les fichiers de présentation par programme. Ce didacticiel vous guidera tout au long du processus de création d'une forme d'ellipse simple dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.Slides pour .NET : assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour .NET. Vous pouvez le télécharger depuis le[page des versions](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de développement .NET sur votre machine.
## Importer des espaces de noms
Dans votre projet .NET, commencez par importer les espaces de noms nécessaires :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Ces espaces de noms fournissent les classes et méthodes essentielles requises pour travailler avec des diapositives et des formes de présentation.
## Étape 1 : configurer la présentation
Commencez par créer une nouvelle présentation et accédez à la première diapositive. Ajoutez le code suivant pour y parvenir :
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instancier la classe de présentation
using (Presentation pres = new Presentation())
{
    // Obtenez la première diapositive
    ISlide sld = pres.Slides[0];
```
Ce code initialise une nouvelle présentation et sélectionne la première diapositive pour une manipulation ultérieure.
## Étape 2 : ajouter une forme d'ellipse
Maintenant, ajoutons une forme d'ellipse à la diapositive à l'aide du`AddAutoShape` méthode:
```csharp
// Ajouter une forme automatique de type ellipse
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Cette ligne de code crée une forme d'ellipse aux coordonnées (50, 150) avec une largeur de 150 unités et une hauteur de 50 unités.
## Étape 3 : Enregistrez la présentation
Enfin, enregistrez la présentation modifiée sur le disque avec un nom de fichier spécifié en utilisant le code suivant :
```csharp
// Écrivez le fichier PPTX sur le disque
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Cette étape garantit que vos modifications sont conservées et que vous pouvez afficher la présentation résultante avec la forme d'ellipse nouvellement ajoutée.
## Conclusion
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## FAQ
### Puis-je personnaliser davantage la forme de l’ellipse ?
Oui, vous pouvez modifier diverses propriétés de la forme de l'ellipse, telles que la couleur, la taille et la position, pour répondre à vos exigences de conception spécifiques.
### Aspose.Slides est-il compatible avec les derniers frameworks .NET ?
Oui, Aspose.Slides est régulièrement mis à jour pour garantir la compatibilité avec les derniers frameworks .NET.
### Où puis-je trouver plus de didacticiels et d’exemples pour Aspose.Slides ?
 Visiter le[Documentation](https://reference.aspose.com/slides/net/) pour des guides et des exemples complets.
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
 Suivre la[lien de licence temporaire](https://purchase.aspose.com/temporary-license/) demander une licence temporaire à des fins de tests.
### Besoin d'aide ou avez des questions spécifiques ?
 Visiter le[Forum d'assistance Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir l'aide de la communauté et des experts.
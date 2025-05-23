---
"description": "Apprenez à créer de superbes formes elliptiques dans vos diapositives de présentation avec Aspose.Slides pour .NET. Étapes faciles pour une conception dynamique !"
"linktitle": "Créer une forme elliptique simple dans une présentation avec Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Créez facilement une forme elliptique avec Aspose.Slides .NET"
"url": "/fr/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Créez facilement une forme elliptique avec Aspose.Slides .NET

## Introduction
Dans le monde dynamique de la conception de présentations, l'intégration de formes comme des ellipses peut apporter une touche de créativité et de professionnalisme. Aspose.Slides pour .NET offre une solution puissante pour manipuler les fichiers de présentation par programmation. Ce tutoriel vous guidera dans la création d'une forme elliptique simple dans vos diapositives de présentation avec Aspose.Slides pour .NET.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Aspose.Slides pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour .NET. Vous pouvez la télécharger depuis le [page des communiqués](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de développement .NET sur votre machine.
## Importer des espaces de noms
Dans votre projet .NET, commencez par importer les espaces de noms nécessaires :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Ces espaces de noms fournissent les classes et méthodes essentielles requises pour travailler avec des diapositives et des formes de présentation.
## Étape 1 : Configurer la présentation
Commencez par créer une nouvelle présentation et accédez à la première diapositive. Ajoutez le code suivant pour y parvenir :
```csharp
// Le chemin vers le répertoire des documents.
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
## Étape 2 : ajouter une forme d’ellipse
Maintenant, ajoutons une forme d'ellipse à la diapositive en utilisant le `AddAutoShape` méthode:
```csharp
// Ajouter une forme automatique de type ellipse
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Cette ligne de code crée une forme d'ellipse aux coordonnées (50, 150) avec une largeur de 150 unités et une hauteur de 50 unités.
## Étape 3 : Enregistrer la présentation
Enfin, enregistrez la présentation modifiée sur le disque avec un nom de fichier spécifié à l'aide du code suivant :
```csharp
// Écrire le fichier PPTX sur le disque
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Cette étape garantit que vos modifications sont conservées et que vous pouvez visualiser la présentation résultante avec la forme d’ellipse nouvellement ajoutée.
## Conclusion
Félicitations ! Vous avez réussi à créer une forme elliptique simple dans une diapositive de présentation avec Aspose.Slides pour .NET. Ce tutoriel vous explique les bases de l'utilisation des formes, de la configuration des présentations et de l'enregistrement des fichiers modifiés.
---
## FAQ
### Puis-je personnaliser davantage la forme de l'ellipse ?
Oui, vous pouvez modifier diverses propriétés de la forme de l'ellipse, telles que la couleur, la taille et la position, pour répondre à vos exigences de conception spécifiques.
### Aspose.Slides est-il compatible avec les derniers frameworks .NET ?
Oui, Aspose.Slides est régulièrement mis à jour pour assurer la compatibilité avec les derniers frameworks .NET.
### Où puis-je trouver plus de tutoriels et d'exemples pour Aspose.Slides ?
Visitez le [documentation](https://reference.aspose.com/slides/net/) pour des guides et des exemples complets.
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
Suivez le [lien de licence temporaire](https://purchase.aspose.com/temporary-license/) pour demander une licence temporaire à des fins de test.
### Besoin d'aide ou avez des questions spécifiques ?
Visitez le [Forum d'assistance Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir de l'aide de la communauté et des experts.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
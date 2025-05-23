---
"description": "Explorez l'univers des présentations PowerPoint dynamiques avec Aspose.Slides pour .NET. Apprenez à créer des formes rectangulaires attrayantes dans vos diapositives grâce à ce guide étape par étape."
"linktitle": "Création d'une forme rectangulaire simple dans les diapositives de présentation à l'aide d'Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Création de formes rectangulaires avec Aspose.Slides pour .NET"
"url": "/fr/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Création de formes rectangulaires avec Aspose.Slides pour .NET

## Introduction
Si vous souhaitez enrichir vos applications .NET avec des présentations PowerPoint dynamiques et attrayantes, Aspose.Slides pour .NET est la solution idéale. Dans ce tutoriel, nous vous guiderons dans la création d'un rectangle simple dans vos diapositives de présentation avec Aspose.Slides pour .NET.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Visual Studio : assurez-vous que Visual Studio est installé sur votre machine de développement.
- Aspose.Slides pour .NET : téléchargez et installez la bibliothèque Aspose.Slides pour .NET depuis [ici](https://releases.aspose.com/slides/net/).
- Connaissances de base en C# : La connaissance du langage de programmation C# est essentielle.
## Importer des espaces de noms
Dans votre projet C#, commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.Slides :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Étape 1 : Configurer le projet
Commencez par créer un projet C# dans Visual Studio. Assurez-vous qu'Aspose.Slides pour .NET est correctement référencé dans votre projet.
## Étape 2 : Initialiser l'objet de présentation
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Votre code pour les prochaines étapes ira ici.
}
```
## Étape 3 : Obtenez la première diapositive
```csharp
ISlide sld = pres.Slides[0];
```
## Étape 4 : Ajouter une forme automatique rectangulaire
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Ce code ajoute une forme rectangulaire aux coordonnées (50, 150) avec une largeur de 150 et une hauteur de 50.
## Étape 5 : Enregistrer la présentation
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Cette étape enregistre la présentation avec la forme rectangulaire ajoutée dans le répertoire spécifié.
## Conclusion
Félicitations ! Vous avez réussi à créer une forme rectangulaire simple dans une diapositive de présentation avec Aspose.Slides pour .NET. Ce n'est qu'un début : Aspose.Slides offre un large éventail de fonctionnalités pour personnaliser et améliorer vos présentations.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Slides pour .NET dans les environnements Windows et Linux ?
Oui, Aspose.Slides pour .NET est indépendant de la plate-forme et peut être utilisé dans les environnements Windows et Linux.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?
Visitez le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien de la communauté.
### Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?
Oui, vous pouvez acheter une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?
Se référer à la documentation [ici](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
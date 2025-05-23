---
"description": "Apprenez à masquer des formes dans vos diapositives PowerPoint avec Aspose.Slides pour .NET. Personnalisez vos présentations par programmation grâce à ce guide étape par étape."
"linktitle": "Masquer des formes dans les diapositives de présentation avec Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Masquer des formes dans PowerPoint avec Aspose.Slides .NET"
"url": "/fr/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Masquer des formes dans PowerPoint avec Aspose.Slides .NET

## Introduction
Dans l'univers dynamique des présentations, la personnalisation est essentielle. Aspose.Slides pour .NET offre une solution puissante pour manipuler les présentations PowerPoint par programmation. L'une des exigences courantes est de pouvoir masquer des formes spécifiques dans une diapositive. Ce tutoriel vous guidera dans le processus de masquage de formes dans les diapositives de présentation avec Aspose.Slides pour .NET.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Aspose.Slides pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.Slides. Vous pouvez la télécharger. [ici](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez votre environnement de développement préféré pour .NET.
- Connaissances de base de C# : Familiarisez-vous avec C# car les exemples de code fournis sont dans ce langage.
## Importer des espaces de noms
Pour commencer à utiliser Aspose.Slides, importez les espaces de noms nécessaires dans votre projet C#. Cela vous permettra d'accéder aux classes et méthodes requises.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Maintenant, décomposons l’exemple de code en plusieurs étapes pour une compréhension claire et concise.
## Étape 1 : Configurez votre projet
Créez un nouveau projet C# et assurez-vous d’inclure la bibliothèque Aspose.Slides.
## Étape 2 : Créer une présentation
Instancier le `Presentation` Classe représentant le fichier PowerPoint. Ajoutez une diapositive et obtenez une référence.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Étape 3 : ajouter des formes à la diapositive
Ajoutez des formes automatiques à la diapositive, telles que des rectangles et des lunes, avec des dimensions spécifiques.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Étape 4 : Masquer les formes en fonction du texte alternatif
Spécifiez un texte alternatif et masquez les formes qui correspondent à ce texte.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Étape 5 : Enregistrer la présentation
Enregistrez la présentation modifiée sur le disque au format PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusion
Félicitations ! Vous avez réussi à masquer des formes dans votre présentation avec Aspose.Slides pour .NET. Cela ouvre un monde de possibilités pour créer des diapositives dynamiques et personnalisées par programmation.
---
## FAQ
### Aspose.Slides est-il compatible avec .NET Core ?
Oui, Aspose.Slides prend en charge .NET Core, offrant ainsi une flexibilité dans votre environnement de développement.
### Puis-je masquer des formes en fonction de conditions autres que le texte alternatif ?
Absolument ! Vous pouvez personnaliser la logique de masquage en fonction de divers attributs comme le type de forme, la couleur ou la position.
### Où puis-je trouver de la documentation supplémentaire sur Aspose.Slides ?
Explorer la documentation [ici](https://reference.aspose.com/slides/net/) pour des informations détaillées et des exemples.
### Des licences temporaires sont-elles disponibles pour Aspose.Slides ?
Oui, vous pouvez obtenir un permis temporaire [ici](https://purchase.aspose.com/temporary-license/) à des fins de test.
### Comment puis-je obtenir le soutien de la communauté pour Aspose.Slides ?
Rejoignez la communauté Aspose.Slides sur le [forum](https://forum.aspose.com/c/slides/11) pour des discussions et de l'aide.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
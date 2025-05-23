---
"description": "Apprenez à ajuster les angles des lignes de connexion dans vos diapositives PowerPoint avec Aspose.Slides pour .NET. Améliorez vos présentations avec précision et simplicité."
"linktitle": "Réglage des angles des lignes de connexion dans les diapositives de présentation à l'aide d'Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Ajuster les angles des lignes de connexion dans PowerPoint avec Aspose.Slides"
"url": "/fr/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajuster les angles des lignes de connexion dans PowerPoint avec Aspose.Slides

## Introduction
Créer des diapositives de présentation visuellement attrayantes nécessite souvent des ajustements précis des lignes de connexion. Dans ce tutoriel, nous découvrirons comment ajuster les angles des lignes de connexion dans les diapositives de présentation avec Aspose.Slides pour .NET. Aspose.Slides est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PowerPoint par programmation, offrant des fonctionnalités étendues pour la création, la modification et la manipulation de présentations.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des éléments suivants :
- Connaissances de base du langage de programmation C#.
- Visual Studio ou tout autre environnement de développement C# installé.
- Bibliothèque Aspose.Slides pour .NET. Vous pouvez la télécharger. [ici](https://releases.aspose.com/slides/net/).
- Un fichier de présentation PowerPoint avec des lignes de connexion que vous souhaitez ajuster.
## Importer des espaces de noms
Pour commencer, assurez-vous d’inclure les espaces de noms nécessaires dans votre code C# :
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Étape 1 : Configurez votre projet
Créez un projet C# dans Visual Studio et installez le package NuGet Aspose.Slides. Configurez la structure du projet avec une référence à la bibliothèque Aspose.Slides.
## Étape 2 : Charger la présentation
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
Chargez votre fichier de présentation PowerPoint dans le `Presentation` objet. Remplacez « Votre répertoire de documents » par le chemin réel vers votre fichier.
## Étape 3 : Accéder à la diapositive et aux formes
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Accédez à la première diapositive de la présentation et initialisez une variable pour représenter les formes sur la diapositive.
## Étape 4 : Parcourir les formes
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Code de gestion des lignes de connexion
}
```
Parcourez chaque forme sur la diapositive pour identifier et traiter les lignes de connexion.
## Étape 5 : Ajuster les angles des lignes de connexion
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Code de gestion des formes automatiques
}
else if (shape is Connector)
{
    // Code de gestion des connecteurs
}
Console.WriteLine(dir);
```
Identifiez si la forme est une forme automatique ou un connecteur et ajustez les angles de la ligne du connecteur à l'aide des `getDirection` méthode.
## Étape 6 : Définir le `getDirection` Méthode
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Code de calcul de direction
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
Mettre en œuvre le `getDirection` méthode pour calculer l'angle de la ligne de connexion en fonction de ses dimensions et de son orientation.
## Conclusion
Grâce à ces étapes, vous pouvez ajuster par programmation les angles des lignes de connexion dans votre présentation PowerPoint avec Aspose.Slides pour .NET. Ce tutoriel vous aidera à améliorer l'esthétique de vos diapositives.
## FAQ
### Aspose.Slides est-il adapté aux applications Windows et Web ?
Oui, Aspose.Slides peut être utilisé dans les applications Windows et Web.
### Puis-je télécharger une version d'essai gratuite d'Aspose.Slides avant d'acheter ?
Oui, vous pouvez télécharger un essai gratuit [ici](https://releases.aspose.com/).
### Où puis-je trouver une documentation complète sur Aspose.Slides pour .NET ?
La documentation est disponible [ici](https://reference.aspose.com/slides/net/).
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
Vous pouvez obtenir un permis temporaire [ici](https://purchase.aspose.com/temporary-license/).
### Existe-t-il un forum d'assistance pour Aspose.Slides ?
Oui, vous pouvez visiter le forum d'assistance [ici](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
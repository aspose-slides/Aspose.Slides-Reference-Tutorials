---
"description": "Apprenez à convertir facilement un PPT en PPTX avec Aspose.Slides pour .NET. Guide étape par étape avec exemples de code pour une transformation de format fluide."
"linktitle": "Convertir un PPT en PPTX"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Convertir un PPT en PPTX"
"url": "/fr/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir un PPT en PPTX


Si vous avez déjà eu besoin de convertir des fichiers PowerPoint de l'ancien format PPT au nouveau format PPTX avec .NET, vous êtes au bon endroit. Dans ce tutoriel, nous vous guiderons pas à pas à travers le processus grâce à l'API Aspose.Slides pour .NET. Grâce à cette puissante bibliothèque, vous pourrez facilement gérer ces conversions. C'est parti !

## Prérequis

Avant de plonger dans le code, assurez-vous d'avoir configuré les éléments suivants :

- Visual Studio : assurez-vous que Visual Studio est installé et prêt pour le développement .NET.
- Aspose.Slides pour .NET : téléchargez et installez la bibliothèque Aspose.Slides pour .NET depuis [ici](https://releases.aspose.com/slides/net/).

## Mise en place du projet

1. Créer un nouveau projet : ouvrez Visual Studio et créez un nouveau projet C#.

2. Ajouter une référence à Aspose.Slides : faites un clic droit sur votre projet dans l’Explorateur de solutions, choisissez « Gérer les packages NuGet » et recherchez « Aspose.Slides ». Installez le package.

3. Importer les espaces de noms requis :

```csharp
using Aspose.Slides;
```

## Conversion de PPT en PPTX

Maintenant que notre projet est configuré, écrivons le code pour convertir un fichier PPT en PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// Instancier un objet Presentation qui représente un fichier PPT
Presentation pres = new Presentation(srcFileName);

// Enregistrer la présentation au format PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

Dans cet extrait de code :

- `dataDir` doit être remplacé par le chemin du répertoire où se trouve votre fichier PPT.
- `outPath` doit être remplacé par le répertoire dans lequel vous souhaitez enregistrer le fichier PPTX converti.
- `srcFileName` est le nom de votre fichier PPT d'entrée.
- `destFileName` est le nom souhaité pour le fichier PPTX de sortie.

## Conclusion

Félicitations ! Vous avez réussi à convertir une présentation PowerPoint du format PPT au format PPTX grâce à l'API Aspose.Slides pour .NET. Cette puissante bibliothèque simplifie ce type de tâches complexes et fluidifie votre expérience de développement .NET.

Si vous ne l'avez pas déjà fait, [télécharger Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/) et explorer davantage ses capacités.

Pour plus de tutoriels et de conseils, visitez notre [documentation](https://reference.aspose.com/slides/net/).

## Questions fréquemment posées

### 1. Qu'est-ce qu'Aspose.Slides pour .NET ?
Aspose.Slides pour .NET est une bibliothèque .NET qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint par programmation.

### 2. Puis-je convertir d'autres formats en PPTX à l'aide d'Aspose.Slides pour .NET ?
Oui, Aspose.Slides pour .NET prend en charge divers formats, notamment PPT, PPTX, ODP, etc.

### 3. L'utilisation d'Aspose.Slides pour .NET est-elle gratuite ?
Non, c'est une bibliothèque commerciale, mais vous pouvez explorer un [essai gratuit](https://releases.aspose.com/) pour évaluer ses caractéristiques.

### 4. Existe-t-il d'autres formats de documents pris en charge par Aspose.Slides pour .NET ?
Oui, Aspose.Slides pour .NET prend également en charge le travail avec des documents Word, des feuilles de calcul Excel et d’autres formats de fichiers.

### 5. Où puis-je obtenir de l'aide ou poser des questions sur Aspose.Slides pour .NET ?
Vous pouvez trouver des réponses à vos questions et demander de l'aide dans le [Forums Aspose.Slides](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
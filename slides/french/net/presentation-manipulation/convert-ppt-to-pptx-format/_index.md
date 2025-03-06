---
title: Convertir PPT au format PPTX
linktitle: Convertir PPT au format PPTX
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à convertir sans effort PPT en PPTX à l'aide d'Aspose.Slides pour .NET. Guide étape par étape avec des exemples de code pour une transformation de format transparente.
weight: 25
url: /fr/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Si vous avez déjà eu besoin de convertir des fichiers PowerPoint de l'ancien format PPT vers le nouveau format PPTX à l'aide de .NET, vous êtes au bon endroit. Dans ce didacticiel étape par étape, nous vous guiderons tout au long du processus à l'aide de l'API Aspose.Slides pour .NET. Avec cette puissante bibliothèque, vous pouvez gérer facilement de telles conversions sans effort. Commençons!

## Conditions préalables

Avant de plonger dans le code, assurez-vous d'avoir la configuration suivante :

- Visual Studio : assurez-vous que Visual Studio est installé et prêt pour le développement .NET.
-  Aspose.Slides pour .NET : téléchargez et installez la bibliothèque Aspose.Slides pour .NET à partir de[ici](https://releases.aspose.com/slides/net/).

## Mise en place du projet

1. Créer un nouveau projet : ouvrez Visual Studio et créez un nouveau projet C#.

2. Ajouter une référence à Aspose.Slides : cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions, choisissez "Gérer les packages NuGet" et recherchez "Aspose.Slides". Installez le paquet.

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

// Instancier un objet Présentation qui représente un fichier PPT
Presentation pres = new Presentation(srcFileName);

//Enregistrement de la présentation au format PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

Dans cet extrait de code :

- `dataDir` doit être remplacé par le chemin du répertoire où se trouve votre fichier PPT.
- `outPath` doit être remplacé par le répertoire dans lequel vous souhaitez enregistrer le fichier PPTX converti.
- `srcFileName` est le nom de votre fichier PPT d'entrée.
- `destFileName` est le nom souhaité pour le fichier PPTX de sortie.

## Conclusion

Toutes nos félicitations! Vous avez converti avec succès une présentation PowerPoint du format PPT au format PPTX à l'aide de l'API Aspose.Slides pour .NET. Cette puissante bibliothèque simplifie les tâches complexes comme celle-ci, rendant votre expérience de développement .NET plus fluide.

 Si vous ne l'avez pas déjà fait,[télécharger Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/) et explorer davantage ses capacités.

 Pour plus de tutoriels et de conseils, visitez notre[Documentation](https://reference.aspose.com/slides/net/).

## Questions fréquemment posées

### 1. Qu'est-ce qu'Aspose.Slides pour .NET ?
Aspose.Slides for .NET est une bibliothèque .NET qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint par programme.

### 2. Puis-je convertir d'autres formats en PPTX à l'aide d'Aspose.Slides pour .NET ?
Oui, Aspose.Slides pour .NET prend en charge divers formats, notamment PPT, PPTX, ODP, etc.

### 3. L’utilisation d’Aspose.Slides pour .NET est-elle gratuite ?
 Non, c'est une bibliothèque commerciale, mais vous pouvez explorer un[essai gratuit](https://releases.aspose.com/) pour évaluer ses caractéristiques.

### 4. Existe-t-il d'autres formats de documents pris en charge par Aspose.Slides pour .NET ?
Oui, Aspose.Slides pour .NET prend également en charge l'utilisation de documents Word, de feuilles de calcul Excel et d'autres formats de fichiers.

### 5. Où puis-je obtenir de l'aide ou poser des questions sur Aspose.Slides pour .NET ?
 Vous pouvez trouver des réponses à vos questions et demander de l'aide dans le[Forums Aspose.Slides](https://forum.aspose.com/).


{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

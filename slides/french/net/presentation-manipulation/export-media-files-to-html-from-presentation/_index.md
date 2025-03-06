---
title: Exporter des fichiers multimédias au format HTML à partir d'une présentation
linktitle: Exporter des fichiers multimédias au format HTML à partir d'une présentation
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Optimisez le partage de vos présentations avec Aspose.Slides pour .NET ! Découvrez comment exporter des fichiers multimédias au format HTML à partir de votre présentation dans ce guide étape par étape.
weight: 15
url: /fr/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exporter des fichiers multimédias au format HTML à partir d'une présentation


Dans ce didacticiel, nous vous guiderons tout au long du processus d'exportation de fichiers multimédias au format HTML à partir d'une présentation à l'aide d'Aspose.Slides pour .NET. Aspose.Slides est une API puissante qui vous permet de travailler avec des présentations PowerPoint par programme. À la fin de ce guide, vous serez en mesure de convertir facilement vos présentations au format HTML. Alors, commençons!

## 1. Introduction

Les présentations PowerPoint contiennent souvent des éléments multimédias tels que des vidéos, et vous devrez peut-être exporter ces présentations au format HTML pour des raisons de compatibilité Web. Aspose.Slides pour .NET fournit un moyen pratique d'accomplir cette tâche par programme.

## 2. Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Slides pour .NET : vous devez avoir installé la bibliothèque Aspose.Slides pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## 3. Chargement d'une présentation

Pour commencer, vous devez charger la présentation PowerPoint que vous souhaitez convertir en HTML. Vous devrez également spécifier le répertoire de sortie dans lequel le fichier HTML sera enregistré. Voici le code pour charger une présentation :

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Charger une présentation
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Votre code ici
}
```

## 4. Configuration des options HTML

Maintenant, configurons les options HTML pour la conversion. Nous allons configurer un contrôleur HTML, un formateur HTML et un format d'image de diapositive. Ce code garantira que votre fichier HTML contient les composants nécessaires à l'affichage des éléments multimédias.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.exemple.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// Définition des options HTML
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. Enregistrement du fichier HTML

 Une fois les options HTML configurées, vous pouvez maintenant enregistrer le fichier HTML. Le`Save` La méthode de l'objet de présentation générera le fichier HTML avec des éléments multimédia intégrés.

```csharp
// Enregistrer le fichier
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Conclusion

Toutes nos félicitations! Vous avez exporté avec succès des fichiers multimédias au format HTML à partir d'une présentation PowerPoint à l'aide d'Aspose.Slides pour .NET. Cela vous permet de partager facilement vos présentations en ligne et de garantir que les éléments multimédias sont correctement affichés.

## 7. FAQ

### Q1 : Aspose.Slides pour .NET est-il une bibliothèque gratuite ?
 A1 : Aspose.Slides pour .NET est une bibliothèque commerciale, mais vous pouvez obtenir un essai gratuit auprès de[ici](https://releases.aspose.com/) pour l'essayer.

### Q2 : Puis-je personnaliser davantage la sortie HTML ?
A2 : Oui, vous pouvez personnaliser la sortie HTML en modifiant les options HTML dans le code.

### Q3 : Aspose.Slides pour .NET prend-il en charge d'autres formats d'exportation ?
A3 : Oui, Aspose.Slides pour .NET prend en charge divers formats d'exportation, notamment PDF, formats d'image, etc.

### Q4 : Où puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?
 A4 : Vous pouvez trouver de l'aide et poser des questions sur les forums Aspose[ici](https://forum.aspose.com/).

### Q5 : Comment acheter une licence pour Aspose.Slides pour .NET ?
 A5 : Vous pouvez acheter une licence auprès de[ce lien](https://purchase.aspose.com/buy).

Maintenant que vous avez terminé ce didacticiel, vous disposez des compétences nécessaires pour exporter des fichiers multimédias au format HTML à partir de présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Profitez du partage en ligne de vos présentations riches en multimédia !
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

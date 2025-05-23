---
"description": "Apprenez à générer des vignettes à partir des diapositives de la section Notes de votre présentation avec Aspose.Slides pour .NET. Améliorez votre contenu visuel !"
"linktitle": "Générer une miniature à partir d'une diapositive dans les notes"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Générer une miniature à partir d'une diapositive dans les notes"
"url": "/fr/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Générer une miniature à partir d'une diapositive dans les notes


Dans le monde des présentations modernes, le contenu visuel est primordial. Créer des diapositives attrayantes est essentiel à une communication efficace. Pour optimiser vos présentations, générez des vignettes à partir des diapositives, notamment pour mettre en valeur des détails spécifiques ou partager un aperçu. Aspose.Slides pour .NET est un outil puissant qui vous permet d'y parvenir facilement. Dans ce guide étape par étape, nous vous expliquerons comment générer des vignettes à partir des diapositives de la section Notes d'une présentation avec Aspose.Slides pour .NET.

## Prérequis

Avant de plonger dans les détails, vous devez disposer des prérequis suivants :

### 1. Aspose.Slides pour .NET

Assurez-vous d'avoir installé et configuré Aspose.Slides pour .NET. Vous pouvez le télécharger ici. [ici](https://releases.aspose.com/slides/net/).

### 2. Environnement .NET

Vous devez disposer d’un environnement de développement .NET prêt sur votre système.

### 3. Un fichier de présentation

Avoir un fichier de présentation (par exemple, `ThumbnailFromSlideInNotes.pptx`) à partir duquel vous souhaitez générer des vignettes.

Maintenant, décomposons le processus en étapes :

## Étape 1 : Importer les espaces de noms

Tout d'abord, vous devez importer les espaces de noms nécessaires pour utiliser Aspose.Slides. Ajoutez le code suivant au début de votre script C# :

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Étape 2 : Charger la présentation

Ensuite, vous devrez charger le fichier de présentation contenant les diapositives annotées. Utilisez le code suivant pour instancier un `Presentation` classe:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Votre code va ici
}
```

## Étape 3 : Accéder à la diapositive

Vous pouvez choisir la diapositive de la présentation pour laquelle vous souhaitez générer une miniature. Dans cet exemple, nous allons accéder à la première diapositive :

```csharp
ISlide sld = pres.Slides[0];
```

## Étape 4 : Définir les dimensions souhaitées

Spécifiez les dimensions (largeur et hauteur) de la vignette à générer. Par exemple :

```csharp
int desiredX = 1200; // Largeur
int desiredY = 800;  // Hauteur
```

## Étape 5 : Calculer les facteurs d'échelle

Pour garantir que la vignette correspond aux dimensions souhaitées, calculez les facteurs d'échelle comme suit :

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Étape 6 : Créer une miniature

Créez maintenant une miniature d’image à grande échelle en utilisant les facteurs d’échelle calculés :

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Étape 7 : Enregistrer la miniature

Enfin, enregistrez la miniature générée sous forme d’image JPEG :

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Et voilà ! Vous avez réussi à générer une miniature à partir d'une diapositive de la section Notes de votre présentation avec Aspose.Slides pour .NET.

## Conclusion

L'intégration de vignettes à vos présentations peut améliorer considérablement leur attrait visuel et leur efficacité. Aspose.Slides pour .NET simplifie ce processus et vous permet de créer facilement des vignettes personnalisées à partir de vos diapositives.

## FAQ (Foire aux questions)

### Dans quels formats puis-je enregistrer les vignettes générées ?
Vous pouvez enregistrer les miniatures dans différents formats, notamment JPEG, PNG, etc., en fonction de vos besoins.

### Puis-je générer des miniatures pour plusieurs diapositives à la fois ?
Oui, vous pouvez parcourir les diapositives de votre présentation et générer des miniatures pour chacune d'elles.

### Aspose.Slides pour .NET est-il compatible avec différents frameworks .NET ?
Oui, Aspose.Slides pour .NET est compatible avec divers frameworks .NET, notamment .NET Core et .NET Framework.

### Puis-je personnaliser l'apparence des vignettes générées ?
Absolument ! Aspose.Slides pour .NET offre des options de personnalisation de l'apparence des vignettes, telles que les dimensions, la qualité, etc.

### Où puis-je obtenir de l'aide ou une assistance supplémentaire avec Aspose.Slides pour .NET ?
Vous pouvez trouver de l'aide et interagir avec la communauté Aspose sur le [Forum d'assistance Aspose](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Générer une vignette à partir d'une diapositive dans Notes
linktitle: Générer une vignette à partir d'une diapositive dans Notes
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment générer des vignettes à partir de diapositives dans la section notes de votre présentation à l'aide d'Aspose.Slides pour .NET. Améliorez votre contenu visuel !
weight: 12
url: /fr/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer une vignette à partir d'une diapositive dans Notes


Dans le monde des présentations modernes, le contenu visuel est roi. Créer des diapositives attrayantes est essentiel pour une communication efficace. Une façon d'améliorer vos présentations consiste à générer des vignettes à partir de diapositives, en particulier lorsque vous souhaitez mettre en valeur des détails spécifiques ou partager une vue d'ensemble. Aspose.Slides for .NET est un outil puissant qui peut vous aider à y parvenir de manière transparente. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de génération de vignettes à partir de diapositives dans la section notes d'une présentation à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables

Avant d’entrer dans les détails, vous devez avoir les conditions préalables suivantes en place :

### 1. Aspose.Slides pour .NET

 Assurez-vous que Aspose.Slides pour .NET est installé et configuré. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

### 2. Environnement .NET

Vous devez disposer d'un environnement de développement .NET prêt sur votre système.

### 3. Un dossier de présentation

 Disposer d'un dossier de présentation (ex.`ThumbnailFromSlideInNotes.pptx`) à partir duquel vous souhaitez générer des vignettes.

Maintenant, décomposons le processus en étapes :

## Étape 1 : Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires pour travailler avec Aspose.Slides. Ajoutez le code suivant au début de votre script C# :

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Étape 2 : Charger la présentation

 Ensuite, vous devrez charger le fichier de présentation contenant les diapositives avec des notes. Utilisez le code suivant pour instancier un`Presentation` classe:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Votre code va ici
}
```

## Étape 3 : accéder à la diapositive

Vous pouvez choisir la diapositive de la présentation pour laquelle vous souhaitez générer une vignette. Dans cet exemple, nous accéderons à la première diapositive :

```csharp
ISlide sld = pres.Slides[0];
```

## Étape 4 : Définir les dimensions souhaitées

Spécifiez les dimensions (largeur et hauteur) de la vignette que vous souhaitez générer. Par exemple:

```csharp
int desiredX = 1200; // Largeur
int desiredY = 800;  // Hauteur
```

## Étape 5 : Calculer les facteurs d'échelle

Pour vous assurer que la miniature correspond aux dimensions souhaitées, calculez les facteurs de mise à l'échelle comme suit :

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Étape 6 : Créer une vignette

Maintenant, créez une vignette d'image à grande échelle en utilisant les facteurs d'échelle calculés :

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Étape 7 : Enregistrez la vignette

Enfin, enregistrez la vignette générée sous forme d'image JPEG :

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

C'est ça! Vous avez généré avec succès une vignette à partir d'une diapositive dans la section notes de votre présentation à l'aide d'Aspose.Slides pour .NET.

## Conclusion

L'intégration de vignettes dans vos présentations peut améliorer considérablement leur attrait visuel et leur efficacité. Aspose.Slides for .NET simplifie ce processus, vous permettant de créer facilement des vignettes personnalisées à partir de vos diapositives.

## FAQ (Foire aux questions)

### Dans quels formats puis-je enregistrer les vignettes générées ?
Vous pouvez enregistrer les vignettes dans différents formats, notamment JPEG, PNG, etc., en fonction de vos besoins.

### Puis-je générer des miniatures pour plusieurs diapositives à la fois ?
Oui, vous pouvez parcourir les diapositives de votre présentation et générer des vignettes pour chacune d'entre elles.

### Aspose.Slides pour .NET est-il compatible avec différents frameworks .NET ?
Oui, Aspose.Slides pour .NET est compatible avec divers frameworks .NET, notamment .NET Core et .NET Framework.

### Puis-je personnaliser l'apparence des vignettes générées ?
Absolument! Aspose.Slides pour .NET fournit des options pour personnaliser l'apparence des vignettes, telles que les dimensions, la qualité, etc.

### Où puis-je obtenir de l’aide ou une assistance supplémentaire concernant Aspose.Slides pour .NET ?
 Vous pouvez trouver de l'aide et interagir avec la communauté Aspose à l'adresse[Forum d'assistance Aspose](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

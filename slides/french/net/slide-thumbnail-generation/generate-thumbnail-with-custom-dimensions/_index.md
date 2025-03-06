---
title: Générer une vignette dans des diapositives avec des dimensions personnalisées
linktitle: Générer une vignette avec des dimensions personnalisées
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment générer des images miniatures personnalisées à partir de présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Améliorez l’expérience utilisateur et les fonctionnalités.
weight: 13
url: /fr/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


La création d'images miniatures personnalisées de vos présentations PowerPoint peut être un atout précieux, que vous créiez une application interactive, amélioriez l'expérience utilisateur ou optimisiez le contenu pour diverses plates-formes. Dans ce didacticiel, nous vous guiderons tout au long du processus de génération d'images miniatures personnalisées à partir de présentations PowerPoint à l'aide de la bibliothèque Aspose.Slides pour .NET. Cette puissante bibliothèque vous permet de manipuler, convertir et améliorer des fichiers PowerPoint par programmation dans des applications .NET.

## Conditions préalables

Avant de commencer à générer des images miniatures personnalisées, assurez-vous que les conditions préalables suivantes sont remplies :

### 1. Aspose.Slides pour .NET

 Vous devez avoir la bibliothèque Aspose.Slides pour .NET installée dans votre projet. Si ce n'est pas déjà fait, vous pouvez trouver la documentation nécessaire et les liens de téléchargement[ici](https://reference.aspose.com/slides/net/).

### 2. Une présentation PowerPoint

Assurez-vous de disposer de la présentation PowerPoint à partir de laquelle vous souhaitez générer une image miniature personnalisée. Cette présentation doit être accessible dans le répertoire de votre projet.

### 3. Environnement de développement

Pour suivre ce didacticiel, vous devez avoir une connaissance pratique de la programmation .NET utilisant C# et un environnement de développement configuré, tel que Visual Studio.

Maintenant que nous avons couvert les conditions préalables, décomposons le processus de génération de vignettes personnalisées en instructions étape par étape.

## Importer des espaces de noms

Tout d’abord, vous devez inclure les espaces de noms requis dans votre code C#. Ces espaces de noms vous permettent de travailler avec Aspose.Slides et de manipuler des présentations PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Étape 1 : Charger la présentation

Pour commencer, chargez la présentation PowerPoint à partir de laquelle vous souhaitez générer une image miniature personnalisée. Ceci est réalisé en utilisant la bibliothèque Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instancier une classe Présentation qui représente le fichier de présentation
using (Presentation pres = new Presentation(srcFileName))
{
    // Votre code pour la génération de vignettes ira ici
}
```

## Étape 2 : accéder à la diapositive

Dans la présentation chargée, vous devez accéder à la diapositive spécifique à partir de laquelle vous souhaitez générer l'image miniature personnalisée. Vous pouvez choisir la diapositive par son index.

```csharp
// Accédez à la première diapositive (vous pouvez modifier l'index selon vos besoins)
ISlide sld = pres.Slides[0];
```

## Étape 3 : Définir les dimensions des vignettes personnalisées

Spécifiez les dimensions souhaitées pour votre image miniature personnalisée. Vous pouvez définir la largeur et la hauteur en pixels en fonction des exigences de votre application.

```csharp
int desiredX = 1200; // Largeur
int desiredY = 800;  // Hauteur
```

## Étape 4 : Calculer les facteurs d'échelle

Pour conserver les proportions de la diapositive, calculez les facteurs de mise à l'échelle pour les dimensions X et Y en fonction de la taille de la diapositive et des dimensions souhaitées.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Étape 5 : générer l’image miniature

Créez une image à grande échelle de la diapositive avec les dimensions personnalisées spécifiées et enregistrez-la sur le disque au format JPEG.

```csharp
// Créer une image à grande échelle
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Enregistrez l'image sur le disque au format JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Maintenant que vous avez suivi ces étapes, vous devriez avoir généré avec succès une image miniature personnalisée à partir de votre présentation PowerPoint.

## Conclusion

Générer des images miniatures personnalisées à partir de présentations PowerPoint à l'aide d'Aspose.Slides pour .NET est une compétence précieuse qui peut améliorer l'expérience utilisateur et les fonctionnalités de vos applications. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement créer des vignettes personnalisées répondant à vos besoins spécifiques.

---

## FAQ (Foire aux questions)

### Qu’est-ce qu’Aspose.Slides pour .NET ?
Aspose.Slides for .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations PowerPoint par programmation dans des applications .NET.

### Où puis-je trouver la documentation d’Aspose.Slides pour .NET ?
 Vous pouvez trouver la documentation[ici](https://reference.aspose.com/slides/net/).

### L’utilisation d’Aspose.Slides pour .NET est-elle gratuite ?
 Aspose.Slides pour .NET est une bibliothèque commerciale. Vous pouvez trouver des informations sur les prix et les licences[ici](https://purchase.aspose.com/buy).

### Ai-je besoin de compétences avancées en programmation pour utiliser Aspose.Slides pour .NET ?
Bien qu'une certaine connaissance de la programmation .NET soit bénéfique, Aspose.Slides pour .NET fournit une API conviviale qui simplifie l'utilisation des présentations PowerPoint.

### Un support technique est-il disponible pour Aspose.Slides pour .NET ?
 Oui, vous pouvez accéder au support technique et aux forums communautaires[ici](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

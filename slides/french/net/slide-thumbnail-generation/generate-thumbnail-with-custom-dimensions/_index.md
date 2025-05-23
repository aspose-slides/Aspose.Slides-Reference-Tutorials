---
"description": "Apprenez à générer des vignettes personnalisées à partir de présentations PowerPoint avec Aspose.Slides pour .NET. Améliorez l'expérience utilisateur et les fonctionnalités."
"linktitle": "Générer une miniature avec des dimensions personnalisées"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Générer une miniature dans les diapositives avec des dimensions personnalisées"
"url": "/fr/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Générer une miniature dans les diapositives avec des dimensions personnalisées


Créer des vignettes personnalisées pour vos présentations PowerPoint peut s'avérer précieux, que vous souhaitiez créer une application interactive, améliorer l'expérience utilisateur ou optimiser du contenu pour différentes plateformes. Dans ce tutoriel, nous vous guiderons dans la création de vignettes personnalisées à partir de présentations PowerPoint à l'aide de la bibliothèque Aspose.Slides pour .NET. Cette puissante bibliothèque vous permet de manipuler, convertir et améliorer vos fichiers PowerPoint par programmation dans des applications .NET.

## Prérequis

Avant de nous lancer dans la génération d’images miniatures personnalisées, assurez-vous de disposer des conditions préalables suivantes :

### 1. Aspose.Slides pour .NET

La bibliothèque Aspose.Slides pour .NET doit être installée dans votre projet. Si ce n'est pas déjà fait, vous trouverez la documentation nécessaire et les liens de téléchargement. [ici](https://reference.aspose.com/slides/net/).

### 2. Une présentation PowerPoint

Assurez-vous de disposer de la présentation PowerPoint à partir de laquelle vous souhaitez générer une miniature personnalisée. Cette présentation doit être accessible dans le répertoire de votre projet.

### 3. Environnement de développement

Pour suivre ce tutoriel, vous devez avoir une connaissance pratique de la programmation .NET à l'aide de C# et d'un environnement de développement configuré, tel que Visual Studio.

Maintenant que nous avons couvert les prérequis, décomposons le processus de génération de miniatures personnalisées en instructions étape par étape.

## Importer des espaces de noms

Tout d'abord, vous devez inclure les espaces de noms requis dans votre code C#. Ces espaces de noms vous permettent d'utiliser Aspose.Slides et de manipuler des présentations PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Étape 1 : Charger la présentation

Pour commencer, chargez la présentation PowerPoint à partir de laquelle vous souhaitez générer une miniature personnalisée. Pour ce faire, utilisez la bibliothèque Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instancier une classe Presentation qui représente le fichier de présentation
using (Presentation pres = new Presentation(srcFileName))
{
    // Votre code pour la génération de vignettes ira ici
}
```

## Étape 2 : Accéder à la diapositive

Dans la présentation chargée, vous devez accéder à la diapositive à partir de laquelle vous souhaitez générer la vignette personnalisée. Vous pouvez sélectionner la diapositive par son index.

```csharp
// Accédez à la première diapositive (vous pouvez modifier l'index selon vos besoins)
ISlide sld = pres.Slides[0];
```

## Étape 3 : Définir les dimensions personnalisées des vignettes

Spécifiez les dimensions souhaitées pour votre vignette personnalisée. Vous pouvez définir la largeur et la hauteur en pixels selon les besoins de votre application.

```csharp
int desiredX = 1200; // Largeur
int desiredY = 800;  // Hauteur
```

## Étape 4 : Calculer les facteurs d'échelle

Pour conserver le rapport hauteur/largeur de la diapositive, calculez les facteurs d'échelle pour les dimensions X et Y en fonction de la taille de la diapositive et des dimensions souhaitées.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Étape 5 : Générer l'image miniature

Créez une image grandeur nature de la diapositive avec les dimensions personnalisées spécifiées et enregistrez-la sur le disque au format JPEG.

```csharp
// Créer une image à grande échelle
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Enregistrez l'image sur le disque au format JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Maintenant que vous avez suivi ces étapes, vous devriez avoir réussi à générer une image miniature personnalisée à partir de votre présentation PowerPoint.

## Conclusion

Générer des vignettes personnalisées à partir de présentations PowerPoint avec Aspose.Slides pour .NET est une compétence précieuse qui peut améliorer l'expérience utilisateur et les fonctionnalités de vos applications. En suivant les étapes décrites dans ce tutoriel, vous pourrez facilement créer des vignettes personnalisées adaptées à vos besoins spécifiques.

---

## FAQ (Foire aux questions)

### Qu'est-ce qu'Aspose.Slides pour .NET ?
Aspose.Slides pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations PowerPoint par programmation dans des applications .NET.

### Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?
Vous pouvez trouver la documentation [ici](https://reference.aspose.com/slides/net/).

### Aspose.Slides pour .NET est-il gratuit à utiliser ?
Aspose.Slides pour .NET est une bibliothèque commerciale. Vous y trouverez des informations sur les tarifs et les licences. [ici](https://purchase.aspose.com/buy).

### Ai-je besoin de compétences avancées en programmation pour utiliser Aspose.Slides pour .NET ?
Bien qu'une certaine connaissance de la programmation .NET soit bénéfique, Aspose.Slides pour .NET fournit une API conviviale qui simplifie le travail avec les présentations PowerPoint.

### Un support technique est-il disponible pour Aspose.Slides pour .NET ?
Oui, vous pouvez accéder au support technique et aux forums communautaires [ici](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
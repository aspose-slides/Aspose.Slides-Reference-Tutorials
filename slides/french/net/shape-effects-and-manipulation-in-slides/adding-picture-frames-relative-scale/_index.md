---
"description": "Apprenez à ajouter des cadres d'image avec une hauteur d'échelle relative dans Aspose.Slides pour .NET. Suivez ce guide étape par étape pour des présentations fluides."
"linktitle": "Ajout de cadres photo avec une hauteur d'échelle relative dans Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Tutoriel sur l'ajout de cadres photo avec Aspose.Slides .NET"
"url": "/fr/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutoriel sur l'ajout de cadres photo avec Aspose.Slides .NET

## Introduction
Aspose.Slides pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir facilement des présentations PowerPoint dans leurs applications .NET. Dans ce tutoriel, nous allons découvrir comment ajouter des cadres d'image avec une hauteur d'échelle relative à l'aide d'Aspose.Slides pour .NET. Suivez ce guide étape par étape pour améliorer vos compétences en création de présentations.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
- Connaissances de base du langage de programmation C#.
- Visual Studio ou tout autre environnement de développement C# préféré installé.
- Bibliothèque Aspose.Slides pour .NET ajoutée à votre projet.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre code C#. Cette étape vous permet d'accéder aux classes et fonctionnalités fournies par la bibliothèque Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Étape 1 : Configurez votre projet
Commencez par créer un projet C# dans votre environnement de développement préféré. Assurez-vous d'ajouter la bibliothèque Aspose.Slides pour .NET à votre projet en y faisant référence.
## Étape 2 : Charger la présentation et l’image
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Charger l'image à ajouter à la collection d'images de présentation
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Dans cette étape, nous créons un nouvel objet de présentation et chargeons l’image que nous souhaitons ajouter à la présentation.
## Étape 3 : Ajouter un cadre photo à la diapositive
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Ajoutez maintenant un cadre photo à la première diapositive de la présentation. Ajustez les paramètres tels que le type de forme, la position et les dimensions selon vos besoins.
## Étape 4 : Définir la largeur et la hauteur de l'échelle relative
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Définissez la hauteur et la largeur de l'échelle relative du cadre photo pour obtenir l'effet de mise à l'échelle souhaité.
## Étape 5 : Enregistrer la présentation
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Enfin, enregistrez la présentation avec le cadre photo ajouté dans le format de sortie spécifié.
## Conclusion
Félicitations ! Vous avez appris à ajouter des cadres photo avec une hauteur d'échelle relative avec Aspose.Slides pour .NET. Testez différentes images, positions et échelles pour créer des présentations visuellement attrayantes et adaptées à vos besoins.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Slides pour .NET avec d’autres langages de programmation ?
Aspose.Slides prend principalement en charge les langages .NET, mais vous pouvez explorer d'autres produits Aspose pour la compatibilité avec différentes plates-formes.
### Où puis-je trouver une documentation détaillée pour Aspose.Slides pour .NET ?
Se référer à la [documentation](https://reference.aspose.com/slides/net/) pour des informations complètes et des exemples.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
Oui, vous pouvez obtenir un [essai gratuit](https://releases.aspose.com/) pour évaluer les capacités de la bibliothèque.
### Comment puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?
Visitez le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour demander l'aide de la communauté et des experts d'Aspose.
### Où puis-je acheter Aspose.Slides pour .NET ?
Vous pouvez acheter Aspose.Slides pour .NET auprès du [page d'achat](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
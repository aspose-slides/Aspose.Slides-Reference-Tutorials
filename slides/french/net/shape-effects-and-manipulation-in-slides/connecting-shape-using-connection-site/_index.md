---
title: Maîtrise de la connexion de forme avec Aspose.Slides pour .NET
linktitle: Forme de connexion à l'aide du site de connexion dans la présentation
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Créez des présentations captivantes avec Aspose.Slides pour .NET, reliant les formes de manière transparente. Suivez notre guide pour une expérience fluide et engageante.
weight: 30
url: /fr/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans le monde dynamique des présentations, la création de diapositives visuellement attrayantes avec des formes interconnectées est cruciale pour une communication efficace. Aspose.Slides pour .NET fournit une solution puissante pour y parvenir en vous permettant de connecter des formes à l'aide de sites de connexion. Ce didacticiel vous guidera étape par étape dans le processus de connexion des formes, garantissant que vos présentations se démarquent par des transitions visuelles fluides.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Une compréhension de base de la programmation C# et .NET.
-  Aspose.Slides pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/net/).
- Un environnement de développement intégré (IDE) comme Visual Studio mis en place.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre code C# :
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Étape 1 : Configurez votre répertoire de documents
Assurez-vous d'avoir un répertoire désigné pour votre document. S'il n'existe pas, créez-en un :
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Étape 2 : Créer une présentation
Instanciez la classe Présentation pour représenter votre fichier PPTX :
```csharp
using (Presentation presentation = new Presentation())
{
    // Votre code pour la présentation va ici
}
```
## Étape 3 : accéder et ajouter des formes
Accédez à la collection de formes pour la diapositive sélectionnée et ajoutez les formes nécessaires :
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Étape 4 : joindre des formes à l'aide de connecteurs
Connectez les formes à l'aide du connecteur :
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## Étape 5 : Définir le site de connexion souhaité
Spécifiez l'index du site de connexion souhaité pour le connecteur :
```csharp
uint wantedIndex = 6;
if (ellipse.ConnectionSiteCount > wantedIndex)
{
    connector.StartShapeConnectionSiteIndex = wantedIndex;
}
```
## Étape 6 : Enregistrez votre présentation
Enregistrez votre présentation avec les formes connectées :
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
Vous avez désormais réussi à connecter des formes à l’aide de sites de connexion dans votre présentation.
## Conclusion
Aspose.Slides pour .NET simplifie le processus de connexion des formes, vous permettant de créer sans effort des présentations visuellement attrayantes. En suivant ce guide étape par étape, vous pouvez améliorer l'attrait visuel de vos diapositives et transmettre efficacement votre message.
## Questions fréquemment posées
### Aspose.Slides est-il compatible avec Visual Studio 2019 ?
Oui, Aspose.Slides est compatible avec Visual Studio 2019. Assurez-vous que la version appropriée est installée.
### Puis-je connecter plus de deux formes dans un seul connecteur ?
Aspose.Slides vous permet de connecter deux formes avec un seul connecteur. Pour connecter plus de formes, vous aurez besoin de connecteurs supplémentaires.
### Comment gérer les exceptions lors de l’utilisation d’Aspose.Slides ?
Vous pouvez utiliser des blocs try-catch pour gérer les exceptions. Se référer au[Documentation](https://reference.aspose.com/slides/net/) pour les exceptions spécifiques et la gestion des erreurs.
### Existe-t-il une version d’essai d’Aspose.Slides disponible ?
 Oui, vous pouvez télécharger une version d'essai gratuite[ici](https://releases.aspose.com/).
### Où puis-je obtenir de l’aide pour Aspose.Slides ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

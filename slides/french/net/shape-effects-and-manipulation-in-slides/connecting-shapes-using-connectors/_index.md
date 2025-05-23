---
"description": "Découvrez la puissance d'Aspose.Slides pour .NET et connectez facilement des formes dans vos présentations. Optimisez vos diapositives grâce à des connecteurs dynamiques."
"linktitle": "Connecter des formes à l'aide de connecteurs dans une présentation"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides &#58; connectez des formes de manière transparente dans .NET"
"url": "/fr/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides : connectez des formes de manière transparente dans .NET

## Introduction
Dans l'univers dynamique des présentations, la possibilité de relier des formes à l'aide de connecteurs ajoute une touche de sophistication à vos diapositives. Aspose.Slides pour .NET permet aux développeurs d'y parvenir en toute simplicité. Ce tutoriel vous guidera tout au long du processus, en décomposant chaque étape pour une compréhension claire.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des éléments suivants :
- Connaissances de base de C# et du framework .NET.
- Aspose.Slides pour .NET est installé. Sinon, téléchargez-le. [ici](https://releases.aspose.com/slides/net/).
- Un environnement de développement mis en place.
## Importer des espaces de noms
Dans votre code C#, commencez par importer les espaces de noms nécessaires :
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Configurer le répertoire de documents
Commencez par définir le répertoire de votre document :
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Instancier la classe de présentation
Créez une instance de la classe Presentation pour représenter votre fichier PPTX :
```csharp
using (Presentation input = new Presentation())
{
    // Accéder à la collection de formes pour la diapositive sélectionnée
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Ajoutez des formes à la diapositive
Ajoutez les formes nécessaires à votre diapositive, telles qu'une ellipse et un rectangle :
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Ajouter une forme de connecteur
Inclure une forme de connecteur dans la collection de formes de la diapositive :
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Connectez les formes avec le connecteur
Spécifiez les formes à connecter par le connecteur :
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Rediriger le connecteur
Appelez la méthode de reroutement pour définir le chemin le plus court automatique entre les formes :
```csharp
connector.Reroute();
```
## 7. Enregistrer la présentation
Enregistrez votre présentation pour afficher les formes connectées :
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Conclusion
Félicitations ! Vous avez réussi à connecter des formes à l'aide de connecteurs dans vos diapositives de présentation avec Aspose.Slides pour .NET. Améliorez vos présentations grâce à cette fonctionnalité avancée et captivez votre public.
## FAQ
### Aspose.Slides pour .NET est-il compatible avec le dernier framework .NET ?
Oui, Aspose.Slides pour .NET est régulièrement mis à jour pour garantir la compatibilité avec les dernières versions du framework .NET.
### Puis-je connecter plus de deux formes à l'aide d'un seul connecteur ?
Absolument, vous pouvez connecter plusieurs formes en étendant la logique du connecteur dans votre code.
### Existe-t-il des limitations quant aux formes que je peux connecter ?
Aspose.Slides pour .NET prend en charge la connexion de diverses formes, notamment des formes de base, des illustrations intelligentes et des formes personnalisées.
### Comment puis-je personnaliser l'apparence du connecteur ?
Explorez la documentation Aspose.Slides pour connaître les méthodes permettant de personnaliser l’apparence du connecteur, telles que le style de ligne et la couleur.
### Existe-t-il un forum communautaire pour le support d'Aspose.Slides ?
Oui, vous pouvez trouver de l'aide et partager vos expériences dans le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
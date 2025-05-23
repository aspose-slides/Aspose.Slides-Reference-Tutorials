---
"description": "Apprenez à connecter des formes à l'aide de connecteurs dans des présentations PowerPoint avec Aspose.Slides pour Java. Tutoriel pas à pas pour débutants."
"linktitle": "Connecter des formes à l'aide de connecteurs dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Connecter des formes à l'aide de connecteurs dans PowerPoint"
"url": "/fr/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Connecter des formes à l'aide de connecteurs dans PowerPoint

## Introduction
Dans ce tutoriel, nous allons découvrir comment connecter des formes à l'aide de connecteurs dans des présentations PowerPoint, à l'aide d'Aspose.Slides pour Java. Suivez ces instructions étape par étape pour connecter efficacement des formes et créer des diapositives visuellement attrayantes.
## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
- Connaissances de base du langage de programmation Java.
- Installez Java Development Kit (JDK) sur votre système.
- Téléchargez et configurez Aspose.Slides pour Java. Si vous ne l'avez pas encore installé, vous pouvez le télécharger depuis [ici](https://releases.aspose.com/slides/java/).
- Un éditeur de code tel qu'Eclipse ou IntelliJ IDEA.

## Importer des packages
Tout d’abord, importez les packages nécessaires pour travailler avec Aspose.Slides dans votre projet Java.
```java
import com.aspose.slides.*;

```
## Étape 1 : instancier la classe de présentation
Instancier le `Presentation` classe, qui représente le fichier PPTX sur lequel vous travaillez.
```java
// Le chemin vers le répertoire des documents.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Étape 2 : Accéder à la collection de formes
Accédez à la collection de formes pour la diapositive sélectionnée dans laquelle vous souhaitez ajouter des formes et des connecteurs.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Étape 3 : ajouter des formes
Ajoutez les formes souhaitées à la diapositive. Dans cet exemple, nous ajouterons une ellipse et un rectangle.
```java
// Ajouter une forme automatique Ellipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Ajouter un rectangle de forme automatique
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Étape 4 : Ajouter un connecteur
Ajoutez une forme de connecteur à la collection de formes de diapositives.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Étape 5 : Joindre les formes aux connecteurs
Connectez les formes au connecteur.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Étape 6 : Rediriger le connecteur
Appelez reroute pour définir le chemin le plus court automatique entre les formes.
```java
connector.reroute();
```
## Étape 7 : Enregistrer la présentation
Enregistrez la présentation après avoir connecté les formes à l’aide de connecteurs.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Enfin, n'oubliez pas de vous débarrasser de l'objet Présentation.
```java
if (input != null) input.dispose();
```
Vous avez maintenant connecté avec succès des formes à l’aide de connecteurs dans PowerPoint à l’aide d’Aspose.Slides pour Java.

## Conclusion
Dans ce tutoriel, nous avons appris à relier des formes à l'aide de connecteurs dans des présentations PowerPoint avec Aspose.Slides pour Java. En suivant ces étapes simples, vous pourrez enrichir vos présentations avec des diagrammes et organigrammes visuellement attrayants.
## FAQ
### Puis-je personnaliser l'apparence des connecteurs dans Aspose.Slides pour Java ?
Oui, vous pouvez personnaliser diverses propriétés des connecteurs telles que la couleur, le style de ligne et l'épaisseur en fonction de vos besoins de présentation.
### Aspose.Slides pour Java est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides pour Java prend en charge divers formats PowerPoint, notamment PPTX, PPT et ODP.
### Puis-je connecter plus de deux formes avec un seul connecteur ?
Oui, vous pouvez connecter plusieurs formes à l’aide de connecteurs complexes fournis par Aspose.Slides pour Java.
### Aspose.Slides pour Java offre-t-il une prise en charge pour l'ajout de texte aux formes ?
Absolument, vous pouvez facilement ajouter du texte aux formes et aux connecteurs par programmation à l'aide d'Aspose.Slides pour Java.
### Existe-t-il un forum communautaire ou un canal d'assistance disponible pour les utilisateurs d'Aspose.Slides pour Java ?
Oui, vous pouvez trouver des ressources utiles, poser des questions et interagir avec d'autres utilisateurs sur le forum Aspose.Slides. [ici](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
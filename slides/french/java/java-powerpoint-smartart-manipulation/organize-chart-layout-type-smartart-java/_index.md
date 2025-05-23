---
"description": "Maîtrisez les types de mise en page de graphiques d'organisation dans SmartArt à l'aide de Java avec Aspose.Slides, améliorant ainsi sans effort les visuels de présentation."
"linktitle": "Organiser le type de disposition des graphiques dans SmartArt à l'aide de Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Organiser le type de disposition des graphiques dans SmartArt à l'aide de Java"
"url": "/fr/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Organiser le type de disposition des graphiques dans SmartArt à l'aide de Java

## Introduction
Dans ce tutoriel, nous allons vous expliquer comment organiser les types de présentations graphiques dans SmartArt à l'aide de Java, en exploitant notamment la bibliothèque Aspose.Slides. L'utilisation de SmartArt dans les présentations peut grandement améliorer l'attrait visuel et la clarté de vos données ; il est donc essentiel de maîtriser sa manipulation.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
1. Java Development Kit (JDK) installé sur votre système.
2. Bibliothèque Aspose.Slides téléchargée et configurée. Si ce n'est pas déjà fait, téléchargez-la depuis [ici](https://releases.aspose.com/slides/java/).
3. Compréhension de base de la programmation Java.

## Importer des packages
Tout d’abord, importez les packages nécessaires :
```java
import com.aspose.slides.*;
```
Décomposons l’exemple fourni en plusieurs étapes :
## Étape 1 : Initialiser l'objet de présentation
```java
Presentation presentation = new Presentation();
```
Créer un nouvel objet de présentation.
## Étape 2 : ajouter SmartArt à la diapositive
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Ajoutez SmartArt à la diapositive souhaitée avec les dimensions et le type de mise en page spécifiés.
## Étape 3 : Définir la disposition de l'organigramme
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Définissez le type de disposition de l'organigramme. Dans cet exemple, nous utilisons la disposition « Pendant à gauche ».
## Étape 4 : Enregistrer la présentation
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Enregistrez la présentation avec la mise en page du graphique organisée.

## Conclusion
Maîtriser l'organisation des types de présentations graphiques dans SmartArt avec Java vous permet de créer facilement des présentations visuellement attrayantes. Avec Aspose.Slides, le processus devient plus simple et plus efficace, vous permettant de vous concentrer sur la création de contenu percutant.
## FAQ
### Aspose.Slides est-il compatible avec différents environnements de développement Java ?
Oui, Aspose.Slides est compatible avec divers environnements de développement Java, garantissant ainsi la flexibilité des développeurs.
### Puis-je personnaliser l’apparence des éléments SmartArt à l’aide d’Aspose.Slides ?
Absolument, Aspose.Slides fournit de nombreuses options de personnalisation pour les éléments SmartArt, vous permettant de les adapter à vos besoins spécifiques.
### Aspose.Slides propose-t-il une documentation complète pour les développeurs ?
Oui, les développeurs peuvent se référer à la documentation détaillée fournie par Aspose.Slides pour Java, offrant un aperçu de ses fonctionnalités et de son utilisation.
### Existe-t-il une version d'essai disponible pour Aspose.Slides ?
Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Slides pour explorer ses fonctionnalités avant de prendre une décision d'achat.
### Où puis-je chercher de l'aide pour les requêtes liées à Aspose.Slides ?
Pour toute assistance ou question concernant Aspose.Slides, vous pouvez visiter le forum d'assistance [ici](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
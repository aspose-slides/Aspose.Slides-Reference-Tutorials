---
title: Organiser le type de disposition de graphique dans SmartArt à l'aide de Java
linktitle: Organiser le type de disposition de graphique dans SmartArt à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Maîtrisez les types de disposition d'organigrammes dans SmartArt à l'aide de Java avec Aspose.Slides, améliorant ainsi les visuels de présentation sans effort.
weight: 13
url: /fr/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans ce didacticiel, nous passerons en revue le processus d'organisation du type de disposition de graphique dans SmartArt à l'aide de Java, en tirant spécifiquement parti de la bibliothèque Aspose.Slides. SmartArt dans les présentations peut grandement améliorer l’attrait visuel et la clarté de vos données, ce qui rend essentiel la maîtrise de leur manipulation.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Bibliothèque Aspose.Slides téléchargée et configurée. Si vous ne l'avez pas déjà fait, téléchargez-le depuis[ici](https://releases.aspose.com/slides/java/).
3. Compréhension de base de la programmation Java.

## Importer des packages
Tout d'abord, importez les packages nécessaires :
```java
import com.aspose.slides.*;
```
Décomposons l'exemple fourni en plusieurs étapes :
## Étape 1 : initialiser l'objet de présentation
```java
Presentation presentation = new Presentation();
```
Créez un nouvel objet de présentation.
## Étape 2 : ajouter SmartArt à la diapositive
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Ajoutez SmartArt à la diapositive souhaitée avec les dimensions et le type de mise en page spécifiés.
## Étape 3 : Définir la présentation de l'organigramme
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Définissez le type de présentation de l'organigramme. Dans cet exemple, nous utilisons la disposition Left Hanging.
## Étape 4 : Enregistrer la présentation
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Enregistrez la présentation avec la mise en page du graphique organisé.

## Conclusion
Maîtriser l'organisation des types de présentation de graphiques dans SmartArt à l'aide de Java vous permet de créer facilement des présentations visuellement attrayantes. Avec Aspose.Slides, le processus devient rationalisé et efficace, vous permettant de vous concentrer sur la création de contenu percutant.
## FAQ
### Aspose.Slides est-il compatible avec différents environnements de développement Java ?
Oui, Aspose.Slides est compatible avec divers environnements de développement Java, garantissant ainsi la flexibilité des développeurs.
### Puis-je personnaliser l’apparence des éléments SmartArt à l’aide d’Aspose.Slides ?
Absolument, Aspose.Slides offre des options de personnalisation étendues pour les éléments SmartArt, vous permettant de les adapter à vos besoins spécifiques.
### Aspose.Slides propose-t-il une documentation complète pour les développeurs ?
Oui, les développeurs peuvent se référer à la documentation détaillée fournie par Aspose.Slides pour Java, offrant un aperçu de ses fonctionnalités et de son utilisation.
### Existe-t-il une version d’essai disponible pour Aspose.Slides ?
Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Slides pour explorer ses fonctionnalités avant de prendre une décision d'achat.
### Où puis-je demander de l'aide pour les requêtes liées à Aspose.Slides ?
 Pour toute assistance ou question concernant Aspose.Slides, vous pouvez visiter le forum d'assistance[ici](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

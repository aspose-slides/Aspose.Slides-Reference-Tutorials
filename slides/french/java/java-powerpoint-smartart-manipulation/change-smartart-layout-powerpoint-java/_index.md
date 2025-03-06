---
title: Modifier la mise en page SmartArt dans PowerPoint avec Java
linktitle: Modifier la mise en page SmartArt dans PowerPoint avec Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à manipuler les mises en page SmartArt dans les présentations PowerPoint à l'aide de Java avec Aspose.Slides pour Java.
weight: 19
url: /fr/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans ce didacticiel, nous verrons comment manipuler les mises en page SmartArt dans les présentations PowerPoint à l'aide de Java. SmartArt est une fonctionnalité puissante de PowerPoint qui permet aux utilisateurs de créer des graphiques visuellement attrayants à diverses fins, telles que l'illustration de processus, de hiérarchies, de relations, etc.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
1. Environnement de développement Java : assurez-vous que le kit de développement Java (JDK) est installé sur votre système.
2.  Bibliothèque Aspose.Slides : téléchargez et installez la bibliothèque Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/slides/java/).
3. Compréhension de base de Java : une connaissance des principes fondamentaux du langage de programmation Java sera utile.
4. Environnement de développement intégré (IDE) : choisissez un IDE de votre choix, tel qu'Eclipse ou IntelliJ IDEA.

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Étape 1 : Configurez votre environnement de projet Java
Assurez-vous que votre projet Java est correctement configuré dans l'IDE de votre choix. Créez un nouveau projet Java et incluez la bibliothèque Aspose.Slides dans les dépendances de votre projet.
## Étape 2 : Créer une nouvelle présentation
Instanciez un nouvel objet Présentation pour créer une nouvelle présentation PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Étape 3 : ajouter un graphique SmartArt
Ajoutez un graphique SmartArt à votre présentation. Spécifiez la position et les dimensions du graphique SmartArt sur la diapositive.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Étape 4 : Modifier la mise en page SmartArt
Modifiez la disposition du graphique SmartArt selon le type de disposition souhaité.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Étape 5 : Enregistrer la présentation
Enregistrez la présentation modifiée dans un répertoire spécifié sur votre système.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Conclusion
La manipulation des mises en page SmartArt dans les présentations PowerPoint à l'aide de Java est un processus simple avec Aspose.Slides pour Java. En suivant ce didacticiel, vous pouvez facilement modifier les graphiques SmartArt en fonction de vos besoins de présentation.
## FAQ
### Puis-je personnaliser l’apparence des graphiques SmartArt à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez personnaliser divers aspects des graphiques SmartArt, tels que les couleurs, les styles et les effets.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Aspose.Slides prend en charge les présentations PowerPoint créées dans différentes versions de PowerPoint, garantissant ainsi la compatibilité entre différentes plates-formes.
### Aspose.Slides offre-t-il la prise en charge d’autres langages de programmation ?
Oui, Aspose.Slides est disponible pour plusieurs langages de programmation, notamment .NET, Python et JavaScript.
### Puis-je créer des graphiques SmartArt à partir de zéro à l’aide d’Aspose.Slides ?
Absolument, vous pouvez créer des graphiques SmartArt par programme ou modifier ceux existants pour répondre à vos besoins.
### Existe-t-il un forum communautaire où je peux demander de l'aide concernant Aspose.Slides ?
 Oui, vous pouvez visiter le forum Aspose.Slides[ici](https://forum.aspose.com/c/slides/11) pour poser des questions et interagir avec la communauté.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

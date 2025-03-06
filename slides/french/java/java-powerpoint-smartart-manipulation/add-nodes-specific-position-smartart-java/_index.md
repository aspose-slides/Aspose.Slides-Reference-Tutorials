---
title: Ajouter des nœuds à une position spécifique dans SmartArt à l'aide de Java
linktitle: Ajouter des nœuds à une position spécifique dans SmartArt à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des nœuds à des positions spécifiques dans SmartArt à l'aide de Java avec Aspose.Slides. Créez des présentations dynamiques sans effort.
type: docs
weight: 16
url: /fr/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout de nœuds à des positions spécifiques dans SmartArt à l'aide de Java avec Aspose.Slides. SmartArt est une fonctionnalité de PowerPoint qui vous permet de créer des diagrammes et des graphiques visuellement attrayants.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Aspose.Slides pour la bibliothèque Java téléchargée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
3. Connaissance de base du langage de programmation Java.

## Importer des packages
Tout d'abord, importons les packages nécessaires dans notre code Java :
```java
import com.aspose.slides.*;
import java.io.File;
```
## Étape 1 : Créer une instance de présentation
Commencez par créer une instance de la classe Présentation :
```java
Presentation pres = new Presentation();
```
## Étape 2 : accéder à la diapositive de présentation
Accédez à la diapositive dans laquelle vous souhaitez ajouter le SmartArt :
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Étape 3 : ajouter une forme SmartArt
Ajoutez une forme SmartArt à la diapositive :
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Étape 4 : accéder au nœud SmartArt
Accédez au nœud SmartArt à l'index souhaité :
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Étape 5 : Ajouter un nœud enfant à une position spécifique
Ajoutez un nouveau nœud enfant à une position spécifique dans le nœud parent :
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Étape 6 : ajouter du texte au nœud
Définissez le texte du nœud nouvellement ajouté :
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Étape 7 : Enregistrez la présentation
Enregistrez la présentation modifiée :
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Dans ce didacticiel, vous avez appris à ajouter des nœuds à des positions spécifiques dans SmartArt à l'aide de Java avec Aspose.Slides. En suivant ces étapes, vous pouvez manipuler les formes SmartArt par programme pour créer des présentations dynamiques.
## FAQ
### Puis-je ajouter plusieurs nœuds à la fois ?
Oui, vous pouvez ajouter plusieurs nœuds par programme en itérant sur les positions souhaitées.
### Aspose.Slides est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides prend en charge différents formats PowerPoint, garantissant la compatibilité avec la plupart des versions.
### Puis-je personnaliser l’apparence des nœuds SmartArt ?
Oui, vous pouvez personnaliser l’apparence des nœuds, notamment leur taille, leur couleur et leur style.
### Aspose.Slides offre-t-il la prise en charge d’autres langages de programmation ?
Oui, Aspose.Slides fournit des bibliothèques pour plusieurs langages de programmation, notamment .NET et Python.
### Existe-t-il une version d’essai disponible pour Aspose.Slides ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
---
"description": "Découvrez comment ajouter des nœuds à des emplacements spécifiques dans SmartArt en Java avec Aspose.Slides. Créez des présentations dynamiques en toute simplicité."
"linktitle": "Ajouter des nœuds à une position spécifique dans SmartArt à l'aide de Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter des nœuds à une position spécifique dans SmartArt à l'aide de Java"
"url": "/fr/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des nœuds à une position spécifique dans SmartArt à l'aide de Java

## Introduction
Dans ce tutoriel, nous vous guiderons dans l'ajout de nœuds à des emplacements spécifiques dans SmartArt à l'aide de Java et d'Aspose.Slides. SmartArt est une fonctionnalité de PowerPoint qui permet de créer des diagrammes et des graphiques visuellement attrayants.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
1. Java Development Kit (JDK) installé sur votre système.
2. Bibliothèque Aspose.Slides pour Java téléchargée. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/slides/java/).
3. Connaissances de base du langage de programmation Java.

## Importer des packages
Tout d’abord, importons les packages nécessaires dans notre code Java :
```java
import com.aspose.slides.*;
import java.io.File;
```
## Étape 1 : Créer une instance de présentation
Commencez par créer une instance de la classe Presentation :
```java
Presentation pres = new Presentation();
```
## Étape 2 : Accéder à la diapositive de présentation
Accédez à la diapositive où vous souhaitez ajouter le SmartArt :
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Étape 3 : Ajouter une forme SmartArt
Ajoutez une forme SmartArt à la diapositive :
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Étape 4 : Accéder au nœud SmartArt
Accédez au nœud SmartArt à l'index souhaité :
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Étape 5 : Ajouter un nœud enfant à une position spécifique
Ajoutez un nouveau nœud enfant à une position spécifique dans le nœud parent :
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Étape 6 : Ajouter du texte au nœud
Définissez le texte du nœud nouvellement ajouté :
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Étape 7 : Enregistrer la présentation
Enregistrer la présentation modifiée :
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Dans ce tutoriel, vous avez appris à ajouter des nœuds à des emplacements spécifiques dans SmartArt en Java avec Aspose.Slides. En suivant ces étapes, vous pourrez manipuler des formes SmartArt par programmation pour créer des présentations dynamiques.
## FAQ
### Puis-je ajouter plusieurs nœuds à la fois ?
Oui, vous pouvez ajouter plusieurs nœuds par programmation en itérant sur les positions souhaitées.
### Aspose.Slides est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides prend en charge divers formats PowerPoint, garantissant la compatibilité avec la plupart des versions.
### Puis-je personnaliser l’apparence des nœuds SmartArt ?
Oui, vous pouvez personnaliser l’apparence des nœuds, y compris leur taille, leur couleur et leur style.
### Aspose.Slides offre-t-il un support pour d’autres langages de programmation ?
Oui, Aspose.Slides fournit des bibliothèques pour plusieurs langages de programmation, notamment .NET et Python.
### Existe-t-il une version d'essai disponible pour Aspose.Slides ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ici](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
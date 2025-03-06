---
title: Ajouter un nœud assistant à SmartArt dans Java PowerPoint
linktitle: Ajouter un nœud assistant à SmartArt dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter un nœud assistant à SmartArt dans les présentations Java PowerPoint à l'aide d'Aspose.Slides. Améliorez vos compétences en édition PowerPoint.
type: docs
weight: 17
url: /fr/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'un nœud assistant à SmartArt dans les présentations Java PowerPoint à l'aide d'Aspose.Slides.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système. Vous pouvez télécharger et installer le dernier JDK à partir de[ici](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides pour Java : téléchargez et installez la bibliothèque Aspose.Slides pour Java à partir de[ce lien](https://releases.aspose.com/slides/java/).

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre code Java :
```java
import com.aspose.slides.*;
```
## Étape 1 : Configurer la présentation
Commencez par créer une instance de présentation en utilisant le chemin d'accès à votre fichier PowerPoint :
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Étape 2 : Parcourir les formes
Parcourez chaque forme dans la première diapositive de la présentation :
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Étape 3 : Rechercher les formes SmartArt
Vérifiez si la forme est de type SmartArt :
```java
if (shape instanceof ISmartArt)
```
## Étape 4 : Parcourir les nœuds SmartArt
Parcourez tous les nœuds de la forme SmartArt :
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Étape 5 : Rechercher le nœud Assistant
Vérifiez si le nœud est un nœud assistant :
```java
if (node.isAssistant())
```
## Étape 6 : définissez le nœud Assistant sur Normal
Si le nœud est un nœud assistant, définissez-le sur un nœud normal :
```java
node.setAssistant(false);
```
## Étape 7 : Enregistrer la présentation
Enregistrez la présentation modifiée :
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Toutes nos félicitations! Vous avez ajouté avec succès un nœud assistant à SmartArt dans votre présentation Java PowerPoint à l'aide d'Aspose.Slides.

## FAQ
### Puis-je ajouter plusieurs nœuds assistants à un SmartArt dans la présentation ?
Oui, vous pouvez ajouter plusieurs nœuds assistants en répétant le processus pour chaque nœud.
### Ce didacticiel fonctionne-t-il à la fois pour les modèles PowerPoint et PowerPoint ?
Oui, vous pouvez appliquer ce didacticiel aux présentations et aux modèles PowerPoint.
### Aspose.Slides est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides prend en charge les versions PowerPoint de 97 à 2003 jusqu'à la dernière version.
### Puis-je personnaliser l’apparence du nœud assistant ?
Oui, vous pouvez personnaliser l'apparence à l'aide de diverses propriétés et méthodes fournies par Aspose.Slides.
### Y a-t-il une limite au nombre de nœuds dans un SmartArt ?
SmartArt dans PowerPoint prend en charge un grand nombre de nœuds, mais il est recommandé de le conserver à un niveau raisonnable pour une meilleure lisibilité.
---
"description": "Apprenez à ajouter un nœud assistant à SmartArt dans vos présentations PowerPoint Java avec Aspose.Slides. Améliorez vos compétences en édition PowerPoint."
"linktitle": "Ajouter un nœud assistant à SmartArt dans Java PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter un nœud assistant à SmartArt dans Java PowerPoint"
"url": "/fr/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un nœud assistant à SmartArt dans Java PowerPoint

## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'un nœud assistant à SmartArt dans les présentations PowerPoint Java à l'aide d'Aspose.Slides.
## Prérequis
Avant de commencer, assurez-vous que les conditions préalables suivantes sont en place :
1. Kit de développement Java (JDK) : Assurez-vous que Java est installé sur votre système. Vous pouvez télécharger et installer la dernière version du JDK depuis [ici](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides pour Java : Téléchargez et installez la bibliothèque Aspose.Slides pour Java depuis [ce lien](https://releases.aspose.com/slides/java/).

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre code Java :
```java
import com.aspose.slides.*;
```
## Étape 1 : Configurer la présentation
Commencez par créer une instance de présentation en utilisant le chemin d’accès à votre fichier PowerPoint :
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Étape 2 : Traverser les formes
Parcourez chaque forme à l’intérieur de la première diapositive de la présentation :
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Étape 3 : Rechercher les formes SmartArt
Vérifiez si la forme est de type SmartArt :
```java
if (shape instanceof ISmartArt)
```
## Étape 4 : parcourir les nœuds SmartArt
Parcourez tous les nœuds de la forme SmartArt :
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Étape 5 : Rechercher le nœud assistant
Vérifiez si le nœud est un nœud assistant :
```java
if (node.isAssistant())
```
## Étape 6 : définir le nœud assistant sur Normal
Si le nœud est un nœud assistant, définissez-le sur un nœud normal :
```java
node.setAssistant(false);
```
## Étape 7 : Enregistrer la présentation
Enregistrer la présentation modifiée :
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Félicitations ! Vous avez ajouté avec succès un nœud assistant à SmartArt dans votre présentation PowerPoint Java avec Aspose.Slides.

## FAQ
### Puis-je ajouter plusieurs nœuds assistants à un SmartArt dans la présentation ?
Oui, vous pouvez ajouter plusieurs nœuds assistants en répétant le processus pour chaque nœud.
### Ce tutoriel fonctionne-t-il à la fois pour PowerPoint et les modèles PowerPoint ?
Oui, vous pouvez appliquer ce tutoriel aux présentations et aux modèles PowerPoint.
### Aspose.Slides est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides prend en charge les versions PowerPoint de 97 à 2003 jusqu'à la dernière version.
### Puis-je personnaliser l’apparence du nœud assistant ?
Oui, vous pouvez personnaliser l’apparence à l’aide de diverses propriétés et méthodes fournies par Aspose.Slides.
### Existe-t-il une limite au nombre de nœuds dans un SmartArt ?
SmartArt dans PowerPoint prend en charge un grand nombre de nœuds, mais il est recommandé de le garder raisonnable pour une meilleure lisibilité.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
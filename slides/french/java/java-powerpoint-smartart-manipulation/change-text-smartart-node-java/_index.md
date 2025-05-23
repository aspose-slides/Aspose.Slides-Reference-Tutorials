---
"description": "Découvrez comment mettre à jour le texte du nœud SmartArt dans PowerPoint à l’aide de Java avec Aspose.Slides, améliorant ainsi la personnalisation de la présentation."
"linktitle": "Modifier le texte sur le nœud SmartArt à l'aide de Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Modifier le texte sur le nœud SmartArt à l'aide de Java"
"url": "/fr/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Modifier le texte sur le nœud SmartArt à l'aide de Java

## Introduction
SmartArt dans PowerPoint est une fonctionnalité puissante pour créer des diagrammes visuellement attrayants. Aspose.Slides pour Java offre une prise en charge complète de la manipulation des éléments SmartArt par programmation. Dans ce tutoriel, nous vous guiderons dans la modification du texte d'un nœud SmartArt avec Java.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
- Java Development Kit (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java téléchargée et référencée dans votre projet Java.
- Compréhension de base de la programmation Java.

## Importer des packages
Tout d’abord, importez les packages nécessaires pour accéder à la fonctionnalité Aspose.Slides dans votre code Java.
```java
import com.aspose.slides.*;
```
Décomposons l’exemple en plusieurs étapes :
## Étape 1 : Initialiser l'objet de présentation
```java
Presentation presentation = new Presentation();
```
Créer une nouvelle instance du `Presentation` cours pour travailler avec une présentation PowerPoint.
## Étape 2 : ajouter SmartArt à la diapositive
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
Ajoutez un SmartArt à la première diapositive. Dans cet exemple, nous utilisons `BasicCycle` mise en page.
## Étape 3 : Accéder au nœud SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Obtenez une référence au deuxième nœud racine du SmartArt.
## Étape 4 : Définir le texte sur le nœud
```java
node.getTextFrame().setText("Second root node");
```
Définissez le texte du nœud SmartArt sélectionné.
## Étape 5 : Enregistrer la présentation
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Enregistrez la présentation modifiée dans un emplacement spécifié.

## Conclusion
Dans ce tutoriel, nous avons montré comment modifier le texte d'un nœud SmartArt à l'aide de Java et d'Aspose.Slides. Grâce à ces connaissances, vous pouvez manipuler dynamiquement les éléments SmartArt dans vos présentations PowerPoint, améliorant ainsi leur attrait visuel et leur clarté.
## FAQ
### Puis-je modifier la mise en page du SmartArt après l’avoir ajouté à la diapositive ?
Oui, vous pouvez modifier la mise en page en accédant au `SmartArt.setAllNodes(LayoutType)` méthode.
### Aspose.Slides est-il compatible avec Java 11 ?
Oui, Aspose.Slides pour Java est compatible avec Java 11 et les versions plus récentes.
### Puis-je personnaliser l’apparence des nœuds SmartArt par programmation ?
Bien sûr, vous pouvez modifier diverses propriétés telles que la couleur, la taille et la forme à l'aide de l'API Aspose.Slides.
### Aspose.Slides prend-il en charge d’autres types de mises en page SmartArt ?
Oui, Aspose.Slides prend en charge une large gamme de mises en page SmartArt, vous permettant de choisir celle qui correspond le mieux à vos besoins de présentation.
### Où puis-je trouver plus de ressources et d'assistance pour Aspose.Slides ?
Vous pouvez visiter le [Documentation Aspose.Slides](https://reference.aspose.com/slides/java/) pour des références API détaillées et des tutoriels. Vous pouvez également demander de l'aide au [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) ou envisagez d'acheter un [permis temporaire](https://purchase.aspose.com/temporary-license/) pour un soutien professionnel.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
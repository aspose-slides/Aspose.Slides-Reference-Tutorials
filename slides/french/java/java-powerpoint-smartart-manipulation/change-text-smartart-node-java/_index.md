---
title: Modifier le texte sur le nœud SmartArt à l'aide de Java
linktitle: Modifier le texte sur le nœud SmartArt à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment mettre à jour le texte du nœud SmartArt dans PowerPoint à l'aide de Java avec Aspose.Slides, améliorant ainsi la personnalisation de la présentation.
weight: 22
url: /fr/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
SmartArt dans PowerPoint est une fonctionnalité puissante pour créer des diagrammes visuellement attrayants. Aspose.Slides pour Java fournit une prise en charge complète pour manipuler les éléments SmartArt par programme. Dans ce didacticiel, nous vous guiderons tout au long du processus de modification du texte sur un nœud SmartArt à l'aide de Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Kit de développement Java (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java téléchargée et référencée dans votre projet Java.
- Compréhension de base de la programmation Java.

## Importer des packages
Tout d’abord, importez les packages nécessaires pour accéder à la fonctionnalité Aspose.Slides dans votre code Java.
```java
import com.aspose.slides.*;
```
Décomposons l'exemple en plusieurs étapes :
## Étape 1 : initialiser l'objet de présentation
```java
Presentation presentation = new Presentation();
```
 Créez une nouvelle instance du`Presentation` classe pour travailler avec une présentation PowerPoint.
## Étape 2 : ajouter SmartArt à la diapositive
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 Ajoutez SmartArt à la première diapositive. Dans cet exemple, nous utilisons le`BasicCycle` mise en page.
## Étape 3 : accéder au nœud SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Obtenez une référence au deuxième nœud racine du SmartArt.
## Étape 4 : définir le texte sur le nœud
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
Dans ce didacticiel, nous avons montré comment modifier le texte sur un nœud SmartArt à l'aide de Java et Aspose.Slides. Grâce à ces connaissances, vous pouvez manipuler dynamiquement les éléments SmartArt dans vos présentations PowerPoint, améliorant ainsi leur attrait visuel et leur clarté.
## FAQ
### Puis-je modifier la disposition du SmartArt après l’avoir ajouté à la diapositive ?
 Oui, vous pouvez modifier la mise en page en accédant au`SmartArt.setAllNodes(LayoutType)` méthode.
### Aspose.Slides est-il compatible avec Java 11 ?
Oui, Aspose.Slides pour Java est compatible avec Java 11 et les versions plus récentes.
### Puis-je personnaliser l’apparence des nœuds SmartArt par programme ?
Certes, vous pouvez modifier diverses propriétés telles que la couleur, la taille et la forme à l'aide de l'API Aspose.Slides.
### Aspose.Slides prend-il en charge d’autres types de mises en page SmartArt ?
Oui, Aspose.Slides prend en charge un large éventail de mises en page SmartArt, vous permettant de choisir celle qui correspond le mieux à vos besoins de présentation.
### Où puis-je trouver plus de ressources et d’assistance pour Aspose.Slides ?
 Vous pouvez visiter le[Documentation Aspose.Slides](https://reference.aspose.com/slides/java/) pour des références API détaillées et des didacticiels. De plus, vous pouvez demander de l'aide auprès du[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) ou envisagez d'acheter un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour un accompagnement professionnel.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

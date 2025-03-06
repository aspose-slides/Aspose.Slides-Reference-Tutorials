---
title: Obtenir du texte à partir du nœud SmartArt dans Java PowerPoint
linktitle: Obtenir du texte à partir du nœud SmartArt dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment extraire du texte à partir de nœuds SmartArt dans des présentations Java PowerPoint à l'aide d'Aspose.Slides. Guide simple, étape par étape, pour les développeurs.
weight: 14
url: /fr/java/java-powerpoint-text-alignment-formatting/get-text-from-smartart-node-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir du texte à partir du nœud SmartArt dans Java PowerPoint

## Introduction
Dans ce didacticiel, nous explorerons comment extraire du texte à partir de nœuds SmartArt dans des présentations Java PowerPoint à l'aide d'Aspose.Slides. Aspose.Slides est une puissante bibliothèque Java qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint par programme. L'extraction de texte à partir de nœuds SmartArt peut être utile pour diverses applications telles que l'extraction de données, l'analyse de contenu, etc. À la fin de ce guide, vous comprendrez clairement comment récupérer efficacement du texte à partir de nœuds SmartArt à l'aide d'Aspose.Slides en Java.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1. Kit de développement Java (JDK) : Aspose.Slides pour Java nécessite JDK 8 ou supérieur.
2.  Aspose.Slides pour la bibliothèque Java : vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : utilisez IntelliJ IDEA, Eclipse ou tout autre IDE de votre choix avec prise en charge Java.
4. Fichier de présentation : disposez d'un fichier PowerPoint (.pptx) avec SmartArt dont vous souhaitez extraire le texte.
## Importer des packages
Pour commencer, importez les classes Aspose.Slides nécessaires dans votre fichier Java :
```java
import com.aspose.slides.*;
```
## Étape 1 : Configurez votre projet
Commencez par configurer votre projet Java et en incluant Aspose.Slides for Java dans les dépendances de votre projet. Assurez-vous d'avoir ajouté le fichier JAR Aspose.Slides à votre chemin de construction ou aux dépendances Maven/Gradle.
## Étape 2 : Charger la présentation
Chargez le fichier de présentation PowerPoint à l'aide d'Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Presentation.pptx");
```
## Étape 3 : accéder à SmartArt sur une diapositive
Récupérez la première diapositive de la présentation et accédez à l'objet SmartArt.
```java
ISlide slide = presentation.getSlides().get_Item(0);
ISmartArt smartArt = (ISmartArt) slide.getShapes().get_Item(0);
```
## Étape 4 : Récupérer les nœuds SmartArt
Accédez à tous les nœuds du SmartArt pour parcourir les formes de chaque nœud.
```java
ISmartArtNodeCollection smartArtNodes = smartArt.getAllNodes();
for (ISmartArtNode smartArtNode : (Iterable<ISmartArtNode>) smartArtNodes) {
    for (ISmartArtShape nodeShape : smartArtNode.getShapes()) {
        if (nodeShape.getTextFrame() != null)
            System.out.println(nodeShape.getTextFrame().getText());
    }
}
```
## Étape 5 : Supprimer l'objet de présentation
Il est recommandé de jeter l'objet de présentation une fois que vous avez fini de l'utiliser.
```java
finally {
    if (presentation != null) presentation.dispose();
}
```
## Conclusion
Dans ce didacticiel, nous avons expliqué comment extraire du texte à partir de nœuds SmartArt dans des présentations Java PowerPoint à l'aide d'Aspose.Slides. En suivant ces étapes, vous pouvez récupérer efficacement le contenu textuel des objets SmartArt par programmation, facilitant ainsi diverses tâches de traitement de documents dans vos applications Java.

## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une API robuste qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint par programme à l'aide de Java.
### Comment puis-je télécharger Aspose.Slides pour Java ?
 Vous pouvez télécharger Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/slides/java/).
### Aspose.Slides pour Java est-il adapté à un usage commercial ?
 Oui, Aspose.Slides pour Java peut être utilisé commercialement. Vous pouvez acheter des licences[ici](https://purchase.aspose.com/buy).
### Aspose.Slides pour Java propose-t-il un essai gratuit ?
 Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour Java[ici](https://releases.aspose.com/).
### Où puis-je trouver de l’assistance pour Aspose.Slides pour Java ?
 Pour une assistance technique et un soutien communautaire, visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

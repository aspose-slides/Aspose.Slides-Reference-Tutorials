---
title: Changer l'état SmartArt dans PowerPoint avec Java
linktitle: Changer l'état SmartArt dans PowerPoint avec Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment modifier les états SmartArt dans les présentations PowerPoint à l'aide de Java et Aspose.Slides. Améliorez vos compétences en automatisation de présentation.
weight: 21
url: /fr/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans ce didacticiel, vous apprendrez à manipuler des objets SmartArt dans des présentations PowerPoint à l'aide de Java avec la bibliothèque Aspose.Slides. SmartArt est une fonctionnalité puissante de PowerPoint qui vous permet de créer des diagrammes et des graphiques visuellement attrayants.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système. Vous pouvez le télécharger depuis le[Site Web d'Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides pour Java : téléchargez et installez la bibliothèque Aspose.Slides pour Java à partir du[site web](https://releases.aspose.com/slides/java/).

## Importer des packages
Pour commencer à travailler avec Aspose.Slides dans votre projet Java, importez les packages nécessaires :
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
Décomposons maintenant l'exemple de code fourni en plusieurs étapes :
## Étape 1 : initialiser l'objet de présentation
```java
Presentation presentation = new Presentation();
```
 Ici, nous créons un nouveau`Presentation` objet, qui représente une présentation PowerPoint.
## Étape 2 : ajouter un objet SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 Cette étape ajoute un objet SmartArt à la première diapositive de la présentation. Nous précisons la position et les dimensions de l'objet SmartArt, ainsi que le type de mise en page (dans ce cas,`BasicProcess`).
## Étape 3 : définir l'état de SmartArt
```java
smart.setReversed(true);
```
Ici, nous définissons l'état de l'objet SmartArt. Dans cet exemple, nous inversons la direction du SmartArt.
## Étape 4 : Vérifier l'état de SmartArt
```java
boolean flag = smart.isReversed();
```
 Nous pouvons également vérifier l'état actuel de l'objet SmartArt. Cette ligne récupère si le SmartArt est inversé ou non et le stocke dans le`flag` variable.
## Étape 5 : Enregistrer la présentation
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
Enfin, nous enregistrons la présentation modifiée dans un emplacement spécifié sur le disque.

## Conclusion
Dans ce didacticiel, nous avons appris à modifier l'état des objets SmartArt dans les présentations PowerPoint à l'aide de Java et de la bibliothèque Aspose.Slides. Grâce à ces connaissances, vous pouvez créer des présentations dynamiques et attrayantes par programmation.
## FAQ
### Puis-je modifier d’autres propriétés de SmartArt à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez modifier divers aspects des objets SmartArt, tels que les couleurs, les styles et les mises en page, à l'aide d'Aspose.Slides.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Oui, Aspose.Slides prend en charge les présentations PowerPoint dans différentes versions, garantissant une compatibilité et une intégration transparente.
### Puis-je créer des mises en page SmartArt personnalisées avec Aspose.Slides ?
Absolument! Aspose.Slides fournit des API pour créer des mises en page SmartArt personnalisées adaptées à vos besoins spécifiques.
### Aspose.Slides offre-t-il la prise en charge d'autres formats de fichiers que PowerPoint ?
Oui, Aspose.Slides prend en charge un large éventail de formats de fichiers, notamment PPTX, PPT, PDF, etc.
### Existe-t-il un forum communautaire où je peux obtenir de l'aide pour les questions liées à Aspose.Slides ?
 Oui, vous pouvez visiter le forum Aspose.Slides à l'adresse[ici](https://forum.aspose.com/c/slides/11) pour de l'aide et des discussions.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

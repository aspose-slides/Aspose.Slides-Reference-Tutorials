---
title: Appliquer des effets bicolores sur les images dans PowerPoint
linktitle: Appliquer des effets bicolores sur les images dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment appliquer des effets Duotone aux images dans PowerPoint à l'aide d'Aspose.Slides pour Java avec notre guide étape par étape. Améliorez vos présentations.
weight: 20
url: /fr/java/java-powerpoint-animation-shape-manipulation/apply-duotone-effects-images-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
L'ajout d'effets visuels à vos présentations PowerPoint peut améliorer considérablement leur attrait et leur efficacité. L'un de ces effets convaincants est l'effet Duotone, qui applique deux couleurs contrastées à une image, lui donnant un aspect moderne et professionnel. Dans ce guide complet, nous vous guiderons tout au long du processus d'application des effets Duotone aux images dans PowerPoint à l'aide d'Aspose.Slides pour Java.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre ordinateur. Vous pouvez le télécharger depuis le[Site Web Oracle JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Bibliothèque Aspose.Slides pour Java : vous pouvez télécharger la bibliothèque à partir du[Page de téléchargement d'Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : un IDE comme IntelliJ IDEA ou Eclipse pour écrire et exécuter votre code Java.
4.  Fichier image : un fichier image (par exemple,`aspose-logo.jpg`) pour appliquer l'effet Duotone.
## Importer des packages
Tout d'abord, vous devrez importer les packages nécessaires dans votre programme Java. Voici comment procéder :
```java
import com.aspose.slides.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## Étape 1 : Créer une nouvelle présentation
Commencez par créer un nouvel objet de présentation. Ce sera le canevas sur lequel vous ajouterez votre image et appliquerez l'effet Duotone.
```java
Presentation presentation = new Presentation();
```
## Étape 2 : Lire le fichier image
Ensuite, lisez le fichier image de votre répertoire. Cette image sera ajoutée à la présentation et se verra appliquer l'effet Duotone.
```java
try {
    byte[] imageBytes = Files.readAllBytes(Paths.get("Your Document Directory/aspose-logo.jpg"));
```
## Étape 3 : ajouter l'image à la présentation
Ajoutez l'image à la collection d'images de la présentation. Cette étape rend l’image disponible pour une utilisation dans la présentation.
```java
    IPPImage backgroundImage = presentation.getImages().addImage(imageBytes);
```
## Étape 4 : définir l'image comme arrière-plan de la diapositive
Maintenant, définissez l’image comme arrière-plan de la première diapositive. Cela implique de configurer le type d’arrière-plan et le format de remplissage.
```java
    presentation.getSlides().get_Item(0).getBackground().setType(BackgroundType.OwnBackground);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().setFillType(FillType.Picture);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().setImage(backgroundImage);
```
## Étape 5 : Ajouter l'effet Duotone
Ajoutez un effet Duotone à l'image d'arrière-plan. Cette étape consiste à créer un objet Duotone et à définir ses propriétés.
```java
    IDuotone duotone = presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().getImageTransform().addDuotoneEffect();
```
## Étape 6 : Définir les propriétés bichromes
Configurez l'effet Duotone en définissant les couleurs. Ici, nous utilisons des couleurs de schéma pour l'effet Duotone.
```java
    duotone.getColor1().setColorType(ColorType.Scheme);
    duotone.getColor1().setSchemeColor(SchemeColor.Accent1);
    duotone.getColor2().setColorType(ColorType.Scheme);
    duotone.getColor2().setSchemeColor(SchemeColor.Dark2);
```
## Étape 7 : Récupérer et afficher les valeurs de bichromie efficaces
Pour vérifier l'effet, récupérez les valeurs effectives de l'effet Duotone et imprimez-les sur la console.
```java
    IDuotoneEffectiveData duotoneEffective = duotone.getEffective();
    System.out.println("Duotone effective color1: " + duotoneEffective.getColor1());
    System.out.println("Duotone effective color2: " + duotoneEffective.getColor2());
} catch(IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Conclusion
L'application d'un effet Duotone aux images dans PowerPoint peut donner à vos présentations un aspect élégant et professionnel. Avec Aspose.Slides pour Java, ce processus est simple et hautement personnalisable. Suivez les étapes décrites dans ce didacticiel pour ajouter un effet Duotone à vos images et faire ressortir vos présentations.
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de créer, modifier et manipuler des présentations PowerPoint par programme.
### Comment installer Aspose.Slides pour Java ?
 Vous pouvez télécharger Aspose.Slides pour Java à partir du[page de téléchargement](https://releases.aspose.com/slides/java/). Suivez les instructions d'installation fournies dans la documentation.
### Puis-je utiliser Aspose.Slides pour Java avec n’importe quel IDE ?
Oui, Aspose.Slides pour Java est compatible avec tous les principaux IDE, notamment IntelliJ IDEA, Eclipse et NetBeans.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour Java ?
 Oui, vous pouvez bénéficier d'un essai gratuit auprès du[Page d'essai gratuit d'Aspose.Slides](https://releases.aspose.com/).
### Où puis-je trouver plus d’exemples et de documentation pour Aspose.Slides pour Java ?
 Vous pouvez trouver une documentation complète et des exemples sur le[Page de documentation Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

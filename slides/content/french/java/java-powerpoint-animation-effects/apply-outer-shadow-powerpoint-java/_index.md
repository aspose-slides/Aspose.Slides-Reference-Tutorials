---
title: Appliquer Outer Shadow dans PowerPoint avec Java
linktitle: Appliquer Outer Shadow dans PowerPoint avec Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment appliquer un effet d'ombre extérieure dans PowerPoint à l'aide de Java avec Aspose.Slides. Améliorez vos présentations avec de la profondeur et un attrait visuel.
type: docs
weight: 13
url: /fr/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---
## Introduction
Créer des présentations PowerPoint visuellement attrayantes implique souvent l'ajout de divers effets aux formes et au texte. L’un de ces effets est l’ombre extérieure, qui peut faire ressortir les éléments et ajouter de la profondeur à vos diapositives. Dans ce didacticiel, vous apprendrez à appliquer un effet d'ombre extérieure à une forme dans PowerPoint à l'aide de Java avec Aspose.Slides.
## Conditions préalables

Avant de commencer ce didacticiel, assurez-vous de disposer des prérequis suivants :

1. Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système. Vous pouvez télécharger et installer la dernière version de JDK à partir du site Web d'Oracle.

2.  Aspose.Slides pour Java : téléchargez et installez Aspose.Slides pour Java à partir du[page de téléchargement](https://releases.aspose.com/slides/java/).

3. Environnement de développement intégré (IDE) : choisissez votre IDE Java préféré tel qu'Eclipse, IntelliJ IDEA ou NetBeans pour coder et exécuter des applications Java.

4. Connaissances de base de Java : La connaissance des principes fondamentaux du langage de programmation Java et des concepts orientés objet sera utile pour comprendre les exemples de code.

## Importer des packages

Tout d’abord, importez les packages nécessaires pour travailler avec Aspose.Slides et les fonctionnalités associées dans votre projet Java :

```java
import com.aspose.slides.*;
```

Décomposons maintenant l'exemple de code en plusieurs étapes pour appliquer l'effet d'ombre extérieure à une forme dans PowerPoint à l'aide de Java avec Aspose.Slides :

## Étape 1 : Configurez l'environnement de votre projet

Créez un nouveau projet Java dans votre IDE préféré et ajoutez la bibliothèque Aspose.Slides for Java au chemin de construction de votre projet.

## Étape 2 : initialiser l'objet Présentation

 Créez une instance du`Presentation` classe, qui représente un fichier de présentation PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Étape 3 : Ajouter une diapositive et une forme

Obtenez une référence à la diapositive dans laquelle vous souhaitez ajouter la forme, puis ajoutez une forme automatique (par exemple, un rectangle) à la diapositive.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Étape 4 : Personnalisez la forme

Définissez le type de remplissage de la forme sur « NoFill » et ajoutez du texte à la forme.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Étape 5 : Personnalisez le texte

Accédez aux propriétés de texte de la forme et personnalisez la taille de la police.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Étape 6 : Activer l’effet Ombre extérieure

Activez l'effet d'ombre extérieure pour la partie de texte.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Étape 7 : Définir les paramètres de l'ombre

Définissez les paramètres de l'effet d'ombre externe, tels que le rayon de flou, la direction, la distance et la couleur de l'ombre.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Étape 8 : Enregistrez la présentation

Enregistrez la présentation modifiée avec l'effet d'ombre extérieure appliqué à la forme.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Conclusion

Toutes nos félicitations! Vous avez appliqué avec succès un effet d'ombre extérieure à une forme dans PowerPoint à l'aide de Java avec Aspose.Slides. Expérimentez avec différents paramètres pour obtenir les effets visuels souhaités dans vos présentations.

## FAQ

### Puis-je appliquer l’effet d’ombre extérieure à d’autres formes que les rectangles ?
Oui, vous pouvez appliquer l'effet d'ombre extérieure à diverses formes prises en charge par Aspose.Slides, telles que des cercles, des triangles et des formes personnalisées.

### Est-il possible de personnaliser la couleur et l'intensité de l'ombre ?
Absolument! Vous avez un contrôle total sur les paramètres de l'ombre, notamment la couleur, le rayon de flou, la direction et la distance.

### Puis-je appliquer plusieurs effets à la même forme ?
Oui, vous pouvez combiner plusieurs effets comme l’ombre extérieure, l’ombre intérieure, la lueur et la réflexion pour améliorer l’attrait visuel des formes et du texte dans vos présentations.

### Aspose.Slides prend-il en charge l’application d’effets aux éléments de texte ?
Oui, vous pouvez appliquer des effets non seulement aux formes, mais également à des portions de texte individuelles au sein des formes, vous offrant ainsi une grande flexibilité dans la conception de vos diapositives.

### Où puis-je trouver plus de ressources et d’assistance pour Aspose.Slides ?
 Vous pouvez vous référer au[Documentation](https://reference.aspose.com/slides/java/) pour des références API détaillées et explorez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.
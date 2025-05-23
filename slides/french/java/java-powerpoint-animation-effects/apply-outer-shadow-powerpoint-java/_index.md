---
"description": "Apprenez à appliquer un effet d'ombre extérieure dans PowerPoint avec Java et Aspose.Slides. Améliorez vos présentations en leur apportant profondeur et attrait visuel."
"linktitle": "Appliquer Outer Shadow dans PowerPoint avec Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Appliquer Outer Shadow dans PowerPoint avec Java"
"url": "/fr/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Appliquer Outer Shadow dans PowerPoint avec Java

## Introduction
Créer des présentations PowerPoint visuellement attrayantes implique souvent d'ajouter divers effets aux formes et au texte. L'ombre extérieure est l'un de ces effets, qui permet de mettre en valeur les éléments et d'ajouter de la profondeur à vos diapositives. Dans ce tutoriel, vous apprendrez à appliquer un effet d'ombre extérieure à une forme dans PowerPoint en utilisant Java avec Aspose.Slides.
## Prérequis

Avant de commencer ce tutoriel, assurez-vous de disposer des prérequis suivants :

1. Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système. Vous pouvez télécharger et installer la dernière version du JDK depuis le site web d'Oracle.

2. Aspose.Slides pour Java : Téléchargez et installez Aspose.Slides pour Java à partir du [page de téléchargement](https://releases.aspose.com/slides/java/).

3. Environnement de développement intégré (IDE) : choisissez votre IDE Java préféré tel qu'Eclipse, IntelliJ IDEA ou NetBeans pour coder et exécuter des applications Java.

4. Connaissances de base de Java : la familiarité avec les fondamentaux du langage de programmation Java et les concepts orientés objet sera bénéfique pour comprendre les exemples de code.

## Importer des packages

Tout d’abord, importez les packages nécessaires pour travailler avec Aspose.Slides et les fonctionnalités associées dans votre projet Java :

```java
import com.aspose.slides.*;
```

Décomposons maintenant l'exemple de code en plusieurs étapes pour appliquer l'effet d'ombre extérieure à une forme dans PowerPoint à l'aide de Java avec Aspose.Slides :

## Étape 1 : Configurez l’environnement de votre projet

Créez un nouveau projet Java dans votre IDE préféré et ajoutez la bibliothèque Aspose.Slides pour Java au chemin de génération de votre projet.

## Étape 2 : Initialiser l’objet Présentation

Créer une instance de `Presentation` classe, qui représente un fichier de présentation PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Étape 3 : ajouter une diapositive et une forme

Obtenez une référence à la diapositive dans laquelle vous souhaitez ajouter la forme, puis ajoutez une forme automatique (par exemple, un rectangle) à la diapositive.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Étape 4 : Personnaliser la forme

Définissez le type de remplissage de la forme sur « Aucun remplissage » et ajoutez du texte à la forme.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Étape 5 : Personnaliser le texte

Accédez aux propriétés de texte de la forme et personnalisez la taille de la police.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Étape 6 : Activer l'effet d'ombre extérieure

Activez l’effet d’ombre extérieure pour la partie texte.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Étape 7 : Définir les paramètres d’ombre

Définissez les paramètres de l'effet d'ombre extérieure, tels que le rayon de flou, la direction, la distance et la couleur de l'ombre.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Étape 8 : Enregistrer la présentation

Enregistrez la présentation modifiée avec l’effet d’ombre extérieure appliqué à la forme.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Conclusion

Félicitations ! Vous avez appliqué avec succès un effet d'ombre extérieure à une forme dans PowerPoint en Java avec Aspose.Slides. Testez différents paramètres pour obtenir les effets visuels souhaités dans vos présentations.

## FAQ

### Puis-je appliquer l'effet d'ombre extérieure à d'autres formes en plus des rectangles ?
Oui, vous pouvez appliquer l’effet d’ombre extérieure à diverses formes prises en charge par Aspose.Slides, telles que des cercles, des triangles et des formes personnalisées.

### Est-il possible de personnaliser la couleur et l'intensité de l'ombre ?
Absolument ! Vous avez un contrôle total sur les paramètres d'ombre, notamment la couleur, le rayon de flou, la direction et la distance.

### Puis-je appliquer plusieurs effets à la même forme ?
Oui, vous pouvez combiner plusieurs effets tels que l’ombre extérieure, l’ombre intérieure, la lueur et la réflexion pour améliorer l’attrait visuel des formes et du texte dans vos présentations.

### Aspose.Slides prend-il en charge l’application d’effets aux éléments de texte ?
Oui, vous pouvez appliquer des effets non seulement aux formes, mais également aux parties de texte individuelles au sein des formes, ce qui vous offre une grande flexibilité dans la conception de vos diapositives.

### Où puis-je trouver plus de ressources et d'assistance pour Aspose.Slides ?
Vous pouvez vous référer à la [documentation](https://reference.aspose.com/slides/java/) pour des références API détaillées et explorer le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
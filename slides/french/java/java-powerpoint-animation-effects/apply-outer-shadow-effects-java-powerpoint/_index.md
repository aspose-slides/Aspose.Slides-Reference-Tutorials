---
title: Appliquer des effets d'ombre extérieure dans Java PowerPoint
linktitle: Appliquer des effets d'ombre extérieure dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à appliquer facilement des effets d'ombre extérieure dans des présentations Java PowerPoint à l'aide d'Aspose.Slides grâce à notre guide détaillé étape par étape.
weight: 11
url: /fr/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Créer des présentations attrayantes nécessite souvent l'ajout de divers effets pour améliorer l'attrait visuel de vos diapositives. L’un de ces effets est l’ombre extérieure, qui peut faire ressortir vos éléments et ajouter de la profondeur à votre contenu. Dans ce didacticiel, nous allons parcourir le processus d'application d'effets d'ombre extérieure aux formes dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java.
## Conditions préalables
Avant de plonger dans le guide étape par étape, assurons-nous que vous disposez de tout ce dont vous avez besoin :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre ordinateur. Vous pouvez le télécharger depuis[Le site d'Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides pour la bibliothèque Java : téléchargez la dernière version à partir de[Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : utilisez un IDE comme IntelliJ IDEA ou Eclipse pour écrire et exécuter votre code Java.
4.  Une licence Asposer valide : vous pouvez acheter une licence auprès de[Aspose](https://purchase.aspose.com/buy) ou obtenez un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour évaluation.
## Importer des packages
Tout d’abord, vous devrez importer les packages nécessaires pour Aspose.Slides. Cela ouvre la voie à l’utilisation des puissantes fonctionnalités fournies par la bibliothèque.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Décomposons le processus d'application des effets d'ombre extérieure en étapes gérables :
## Étape 1 : configurer le répertoire du projet
Avant de commencer à écrire votre code, vous devez configurer le répertoire du projet dans lequel vos fichiers PowerPoint seront stockés et accessibles.
Assurez-vous que votre répertoire de projet existe. Si ce n'est pas le cas, créez-le à l'aide du code suivant :
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Étape 2 : initialiser la présentation
Nous devons maintenant initialiser la présentation dans laquelle nous ajouterons nos formes et nos effets.

 Créez une nouvelle instance du`Presentation` classe pour commencer à travailler avec un nouveau fichier PowerPoint.
```java
// Instancier une classe PPTX
Presentation pres = new Presentation();
```
## Étape 3 : ajouter une diapositive et une forme
Ensuite, ajoutez une diapositive à votre présentation, puis ajoutez une forme à laquelle vous appliquerez l'effet d'ombre.
### Obtenir une référence à la diapositive
Récupérez une référence à la première diapositive de la présentation.
```java
// Obtenir la référence de la diapositive
ISlide sld = pres.getSlides().get_Item(0);
```
### Ajouter une forme automatique
Ajoutez une forme automatique rectangulaire à la diapositive aux coordonnées spécifiées.
```java
// Ajouter une forme automatique de type Rectangle
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Étape 4 : Personnaliser la forme
Ajoutez du texte à votre forme et ajustez ses paramètres de remplissage pour rendre l'effet d'ombre plus visible.
### Ajouter TextFrame à la forme
Insérez du texte dans la forme du rectangle.
```java
// Ajouter TextFrame au rectangle
aShp.addTextFrame("Aspose TextBox");
```
### Désactiver le remplissage de forme
Désactivez le remplissage de la forme pour accentuer l'ombre du texte.
```java
// Désactivez le remplissage de forme au cas où nous voudrions obtenir une ombre de texte
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Étape 5 : Appliquer l’effet d’ombre extérieure
Il est maintenant temps d'appliquer l'effet d'ombre extérieure à la forme.
### Activer l'effet d'ombre extérieure
Activez l’effet d’ombre extérieure pour la forme.
```java
// Ajoutez une ombre extérieure et définissez tous les paramètres nécessaires
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Configurer les paramètres d'ombre
Définissez diverses propriétés de l'ombre telles que le rayon de flou, la direction, la distance, l'alignement et la couleur.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Étape 6 : Enregistrez la présentation
Enfin, enregistrez la présentation sur le disque.
```java
//Écrire la présentation sur le disque
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Étape 7 : Éliminer les ressources
Assurez-vous de libérer des ressources en supprimant l’objet de présentation.
```java
// Nettoyer les ressources
if (pres != null) pres.dispose();
```
## Conclusion
Et voila! Vous avez appliqué avec succès un effet d'ombre extérieure à une forme dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Cet effet peut améliorer considérablement l'attrait visuel de vos diapositives, faisant ainsi ressortir votre contenu.
 Si vous rencontrez des problèmes ou avez besoin d'aide supplémentaire, n'hésitez pas à consulter le[Documentation Aspose.Slides](https://reference.aspose.com/slides/java/) ou visitez le[forum d'entraide](https://forum.aspose.com/c/slides/11). Bon codage !
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides for Java est une bibliothèque puissante qui vous permet de créer, manipuler et convertir des présentations PowerPoint dans des applications Java.
### Comment puis-je obtenir un essai gratuit d’Aspose.Slides pour Java ?
 Vous pouvez télécharger un essai gratuit à partir du[Site Aspose](https://releases.aspose.com/).
### Puis-je utiliser Aspose.Slides pour Java avec n’importe quel IDE ?
Oui, vous pouvez utiliser Aspose.Slides pour Java avec n'importe quel IDE Java comme IntelliJ IDEA, Eclipse ou NetBeans.
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
 Vous pouvez obtenir une licence temporaire auprès du[Site Aspose](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver plus d’exemples et de documentation pour Aspose.Slides ?
 Vous pouvez trouver plus d'exemples et une documentation détaillée sur le[Page de documentation Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

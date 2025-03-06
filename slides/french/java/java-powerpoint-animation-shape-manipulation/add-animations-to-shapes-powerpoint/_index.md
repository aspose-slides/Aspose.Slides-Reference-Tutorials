---
title: Ajouter des animations aux formes dans PowerPoint
linktitle: Ajouter des animations aux formes dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des animations aux formes dans PowerPoint à l'aide d'Aspose.Slides pour Java avec ce didacticiel détaillé. Parfait pour créer des présentations attrayantes.
weight: 10
url: /fr/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Créer des présentations attrayantes nécessite souvent l'ajout d'animations aux formes et au texte. Les animations peuvent rendre vos diapositives plus dynamiques et captivantes, garantissant ainsi que votre public reste intéressé. Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'animations aux formes dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. À la fin de cet article, vous serez en mesure de créer des animations professionnelles sans effort.
## Conditions préalables
Avant de plonger dans le didacticiel, assurons-nous que vous disposez de tout ce dont vous avez besoin :
1.  Bibliothèque Aspose.Slides pour Java : vous devez avoir installé la bibliothèque Aspose.Slides pour Java. Tu peux[Télécharger les ici](https://releases.aspose.com/slides/java/).
2. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre ordinateur.
3. Environnement de développement intégré (IDE) : utilisez n'importe quel IDE Java comme IntelliJ IDEA, Eclipse ou NetBeans.
4. Connaissance de base de Java : ce didacticiel suppose que vous possédez une compréhension de base de la programmation Java.
## Importer des packages
Pour commencer, vous devrez importer les packages nécessaires pour Aspose.Slides et les autres classes Java requises.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## Étape 1 : Configurez votre répertoire de projets
Tout d’abord, créez un répertoire pour vos fichiers de projet.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Étape 2 : initialiser l'objet de présentation
 Ensuite, instanciez le`Presentation` classe pour représenter votre fichier PowerPoint.
```java
// Instancier la classe de présentation qui représente le PPTX
Presentation pres = new Presentation();
```
## Étape 3 : Accédez à la première diapositive
Accédez maintenant à la première diapositive de la présentation où vous ajouterez les animations.
```java
// Accédez à la première diapositive
ISlide sld = pres.getSlides().get_Item(0);
```
## Étape 4 : ajouter une forme à la diapositive
Ajoutez une forme de rectangle à la diapositive et insérez-y du texte.
```java
// Ajouter une forme de rectangle à la diapositive
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## Étape 5 : appliquer un effet d'animation
Appliquez l'effet d'animation "PathFootball" à la forme.
```java
// Ajouter un effet d'animation PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Étape 6 : Créer un déclencheur interactif
Créez une forme de bouton qui déclenchera l'animation lorsque vous cliquerez dessus.
```java
// Créer une forme "bouton" pour déclencher l'animation
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Étape 7 : Définir la séquence interactive
Définissez une séquence d'effets pour le bouton.
```java
// Créer une séquence d'effets pour le bouton
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## Étape 8 : ajouter un chemin utilisateur personnalisé
Ajoutez une animation de chemin utilisateur personnalisée à la forme.
```java
// Ajouter un effet d'animation de chemin utilisateur personnalisé
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// Créer un effet de mouvement
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// Définir les points du chemin
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## Étape 9 : Enregistrez la présentation
Enfin, enregistrez la présentation à l'emplacement souhaité.
```java
// Enregistrez la présentation en tant que fichier PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// Supprimer l'objet de présentation
if (pres != null) pres.dispose();
```
## Conclusion
Et voila! Vous avez ajouté avec succès des animations aux formes dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Cette puissante bibliothèque facilite l'amélioration de vos présentations avec des effets dynamiques, garantissant ainsi l'engagement de votre public. N'oubliez pas que la pratique rend parfait, alors continuez à expérimenter différents effets et déclencheurs pour voir ce qui fonctionne le mieux pour vos besoins.
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une API puissante pour créer, modifier et manipuler des présentations PowerPoint par programme.
### Puis-je utiliser Aspose.Slides gratuitement ?
 Vous pouvez essayer Aspose.Slides gratuitement avec un[permis temporaire](https://purchase.aspose.com/temporary-license/). Pour une utilisation continue, une licence payante est requise.
### Quelles versions Java sont compatibles avec Aspose.Slides ?
Aspose.Slides prend en charge Java SE 6 et supérieur.
### Comment ajouter différentes animations à plusieurs formes ?
Vous pouvez ajouter différentes animations à plusieurs formes en répétant les étapes pour chaque forme et en spécifiant différents effets selon vos besoins.
### Où puis-je trouver plus d’exemples et de documentation ?
 Vérifiez[Documentation](https://reference.aspose.com/slides/java/) et[forum d'entraide](https://forum.aspose.com/c/slides/11)pour plus d'exemples et d'aide.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

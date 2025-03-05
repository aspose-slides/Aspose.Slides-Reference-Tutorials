---
title: Créer une ellipse formatée dans PowerPoint
linktitle: Créer une ellipse formatée dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à créer une ellipse formatée dans PowerPoint à l'aide d'Aspose.Slides pour Java avec notre guide détaillé étape par étape.
type: docs
weight: 17
url: /fr/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---
## Introduction
Bienvenue dans ce didacticiel complet sur la création d'une ellipse formatée dans PowerPoint à l'aide d'Aspose.Slides pour Java. Aspose.Slides est une bibliothèque puissante qui permet aux développeurs de manipuler des fichiers PowerPoint par programme. Que vous automatisiez la génération de diapositives ou amélioriez des présentations avec des formes personnalisées, ce guide vous guidera à travers chaque étape, vous garantissant ainsi d'ajouter facilement une ellipse parfaitement formatée à vos diapositives. Allons-y et voyons comment nous pouvons y parvenir !
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK 1.6 ou supérieur est installé.
2.  Aspose.Slides pour Java : téléchargez la dernière version à partir de[Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : utilisez un IDE comme IntelliJ IDEA ou Eclipse.
4. Connaissance de base de Java : Une connaissance de la programmation Java est requise.
## Importer des packages
Pour commencer à utiliser Aspose.Slides, vous devez importer les packages nécessaires. Voici comment procéder :
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Étape 1 : Configurez votre répertoire de projets
Tout d’abord, vous avez besoin d’un répertoire pour stocker vos fichiers PowerPoint.
### Créer le répertoire
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Assurez-vous de remplacer`"Your Document Directory"` avec le chemin réel où vous souhaitez stocker vos fichiers.
## Étape 2 : initialiser la présentation
Maintenant, instanciez la classe Présentation, qui représente le fichier PowerPoint.
```java
// Instancier la classe de présentation qui représente le PPTX
Presentation pres = new Presentation();
```
## Étape 3 : Obtenez la première diapositive
Ensuite, récupérez la première diapositive de la présentation où vous ajouterez l’ellipse.
```java
// Obtenez la première diapositive
ISlide sld = pres.getSlides().get_Item(0);
```
## Étape 4 : ajouter une forme d'ellipse
Ajoutez une forme automatique de type ellipse à la diapositive.
```java
// Ajouter une forme automatique de type ellipse
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Ici,`50, 150, 150, 50` sont les coordonnées et la taille de l'ellipse (position x, position y, largeur, hauteur).
## Étape 5 : appliquer le formatage à l'ellipse
Maintenant, appliquez une mise en forme à l’ellipse. Nous allons définir une couleur de remplissage unie et une couleur de ligne.
### Définir la couleur de remplissage
```java
// Appliquer une mise en forme à la forme de l'ellipse
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Définir la couleur et la largeur de la ligne
```java
// Appliquer une mise en forme à la ligne d'Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Étape 6 : Enregistrez la présentation
Enfin, enregistrez la présentation dans le répertoire spécifié.
```java
// Écrivez le fichier PPTX sur le disque
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Étape 7 : éliminer l'objet de présentation
Supprimez l’objet de présentation pour libérer des ressources.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusion
Toutes nos félicitations! Vous avez créé avec succès une ellipse formatée dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Ce didacticiel vous a guidé tout au long de la configuration de votre projet, de l'ajout d'une ellipse, de l'application du formatage et de l'enregistrement de votre présentation. Grâce à ces compétences, vous pouvez désormais améliorer vos diapositives PowerPoint par programmation, rendant ainsi vos présentations plus dynamiques et visuellement attrayantes.
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de créer, modifier et gérer des présentations PowerPoint par programme.
### Puis-je utiliser Aspose.Slides pour Java avec n’importe quel IDE ?
Oui, vous pouvez utiliser Aspose.Slides pour Java avec n'importe quel IDE Java comme IntelliJ IDEA, Eclipse ou NetBeans.
### Ai-je besoin d’une licence pour Aspose.Slides ?
Oui, Aspose.Slides est un produit commercial et vous avez besoin d’une licence pour bénéficier de toutes les fonctionnalités. Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver plus de documentation sur Aspose.Slides pour Java ?
 Vous pouvez trouver une documentation détaillée sur Aspose.Slides pour Java[page de documentation](https://reference.aspose.com/slides/java/).
### Existe-t-il une assistance disponible pour Aspose.Slides ?
 Oui, Aspose offre une assistance via son[forum](https://forum.aspose.com/c/slides/11).
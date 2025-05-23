---
"description": "Apprenez à créer une ellipse formatée dans PowerPoint à l’aide d’Aspose.Slides pour Java avec notre guide détaillé étape par étape."
"linktitle": "Créer une ellipse formatée dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Créer une ellipse formatée dans PowerPoint"
"url": "/fr/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Créer une ellipse formatée dans PowerPoint

## Introduction
Bienvenue dans ce tutoriel complet sur la création d'une ellipse formatée dans PowerPoint avec Aspose.Slides pour Java. Aspose.Slides est une bibliothèque puissante qui permet aux développeurs de manipuler des fichiers PowerPoint par programmation. Que vous automatisiez la génération de diapositives ou que vous amélioriez vos présentations avec des formes personnalisées, ce guide vous guidera pas à pas pour vous permettre d'ajouter facilement une ellipse parfaitement formatée à vos diapositives. Découvrons ensemble comment y parvenir !
## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK 1.6 ou supérieur est installé.
2. Aspose.Slides pour Java : téléchargez la dernière version depuis [Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : utilisez un IDE comme IntelliJ IDEA ou Eclipse.
4. Connaissances de base de Java : Une connaissance de la programmation Java est requise.
## Importer des packages
Pour commencer à utiliser Aspose.Slides, vous devez importer les packages nécessaires. Voici comment procéder :
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Étape 1 : Configurez votre répertoire de projet
Tout d’abord, vous avez besoin d’un répertoire pour stocker vos fichiers PowerPoint.
### Créer un répertoire
```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
Assurez-vous de remplacer `"Your Document Directory"` avec le chemin réel où vous souhaitez stocker vos fichiers.
## Étape 2 : Initialiser la présentation
Maintenant, instanciez la classe Presentation, qui représente le fichier PowerPoint.
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
## Étape 4 : ajouter une forme d’ellipse
Ajoutez une forme automatique de type ellipse à la diapositive.
```java
// Ajouter une forme automatique de type ellipse
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Ici, `50, 150, 150, 50` sont les coordonnées et la taille de l'ellipse (position x, position y, largeur, hauteur).
## Étape 5 : Appliquer la mise en forme à l'ellipse
Appliquez maintenant un formatage à l'ellipse. Nous allons définir une couleur de remplissage unie et une couleur de trait.
### Définir la couleur de remplissage
```java
// Appliquer une mise en forme à la forme de l'ellipse
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Définir la couleur et la largeur de la ligne
```java
// Appliquer un formatage à la ligne d'Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Étape 6 : Enregistrer la présentation
Enfin, enregistrez la présentation dans le répertoire spécifié.
```java
// Écrire le fichier PPTX sur le disque
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Étape 7 : Éliminer l’objet de présentation
Supprimez l'objet de présentation pour libérer des ressources.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusion
Félicitations ! Vous avez réussi à créer une ellipse formatée dans une présentation PowerPoint avec Aspose.Slides pour Java. Ce tutoriel vous a expliqué comment configurer votre projet, ajouter une ellipse, appliquer la mise en forme et enregistrer votre présentation. Grâce à ces compétences, vous pouvez désormais améliorer vos diapositives PowerPoint par programmation, rendant ainsi vos présentations plus dynamiques et visuellement plus attrayantes.
## FAQ
### Qu'est-ce qu'Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de créer, modifier et gérer des présentations PowerPoint par programmation.
### Puis-je utiliser Aspose.Slides pour Java avec n'importe quel IDE ?
Oui, vous pouvez utiliser Aspose.Slides pour Java avec n’importe quel IDE Java comme IntelliJ IDEA, Eclipse ou NetBeans.
### Ai-je besoin d'une licence pour Aspose.Slides ?
Oui, Aspose.Slides est un produit commercial ; une licence est nécessaire pour bénéficier de toutes ses fonctionnalités. Vous pouvez obtenir une licence temporaire. [ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver plus de documentation sur Aspose.Slides pour Java ?
Vous trouverez une documentation détaillée sur Aspose.Slides pour Java [page de documentation](https://reference.aspose.com/slides/java/).
### Existe-t-il un support disponible pour Aspose.Slides ?
Oui, Aspose offre un support via son [forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
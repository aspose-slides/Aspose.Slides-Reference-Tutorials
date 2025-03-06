---
title: Créer un rectangle formaté dans PowerPoint
linktitle: Créer un rectangle formaté dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à créer et formater un rectangle dans PowerPoint à l'aide d'Aspose.Slides pour Java avec ce guide étape par étape.
type: docs
weight: 18
url: /fr/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un rectangle formaté dans une diapositive PowerPoint à l'aide d'Aspose.Slides pour Java. Nous détaillerons chaque étape, afin que vous puissiez la suivre et la mettre en œuvre dans vos propres projets.
## Conditions préalables
Avant de plonger dans le code, couvrons les prérequis. Vous aurez besoin des éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2. Bibliothèque Aspose.Slides pour Java : téléchargez et incluez la bibliothèque Aspose.Slides pour Java dans votre projet.
3. Environnement de développement intégré (IDE) : un IDE comme IntelliJ IDEA ou Eclipse rendra votre expérience de codage plus fluide.
4. Connaissance de base de Java : La familiarité avec la programmation Java vous aidera à suivre ce tutoriel.
## Importer des packages
Pour commencer, vous devrez importer les packages nécessaires depuis la bibliothèque Aspose.Slides. Voici comment procéder :
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
Ces importations sont cruciales car elles apportent les classes nécessaires pour créer et formater des formes dans votre présentation PowerPoint.
## Étape 1 : configuration du répertoire du projet
Tout d'abord, vous devez créer un répertoire pour votre projet. Ce répertoire stockera vos fichiers PowerPoint.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Ce code vérifie si le répertoire existe et le crée si ce n'est pas le cas. C'est une bonne pratique de garder vos fichiers de projet organisés.
## Étape 2 : Instancier la classe de présentation
 Ensuite, vous allez instancier le`Presentation` classe, qui représente votre fichier PowerPoint.
```java
Presentation pres = new Presentation();
```
Cette ligne de code crée une nouvelle présentation vide à laquelle vous pouvez commencer à ajouter du contenu.
## Étape 3 : ajouter une diapositive à la présentation
Maintenant, ajoutons une diapositive à votre présentation. Par défaut, une nouvelle présentation contient une diapositive, nous allons donc travailler avec cela.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
Cet extrait de code obtient la première diapositive de la présentation.
## Étape 4 : ajouter une forme rectangulaire
Nous allons maintenant ajouter un rectangle à la diapositive.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Ici, nous ajoutons un rectangle avec des dimensions (largeur, hauteur) et une position (x, y) spécifiées à la diapositive.
## Étape 5 : Formater le rectangle
Appliquons une mise en forme pour rendre le rectangle visuellement attrayant.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
Ce code définit le type de remplissage sur solide et la couleur de remplissage sur chocolat.
## Formater la bordure du rectangle
Ensuite, nous formaterons la bordure du rectangle.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
Ce code définit la couleur de la bordure sur noir et la largeur de la bordure sur 5.
## Étape 6 : Enregistrez la présentation
Enfin, sauvegardons la présentation dans le répertoire de votre projet.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Cette ligne de code enregistre la présentation sous forme de fichier PPTX dans votre répertoire spécifié.
## Étape 7 : Nettoyer les ressources
 C'est une bonne pratique de jeter le`Presentation` s’opposer à libérer des ressources.
```java
if (pres != null) pres.dispose();
```
Cela garantit que toutes les ressources sont correctement libérées.
## Conclusion
Créer et formater des formes dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java est un processus simple. En suivant les étapes décrites dans ce didacticiel, vous pouvez automatiser facilement la création de diapositives visuellement attrayantes. Que vous développiez des applications de reporting commercial, de contenu éducatif ou de présentations dynamiques, Aspose.Slides for Java offre les outils dont vous avez besoin pour réussir.
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque qui permet aux développeurs de créer, modifier et convertir des présentations PowerPoint par programme.
### Puis-je utiliser Aspose.Slides pour Java avec n’importe quel IDE ?
Oui, vous pouvez utiliser Aspose.Slides pour Java avec n'importe quel IDE compatible Java tel que IntelliJ IDEA, Eclipse ou NetBeans.
### Comment puis-je obtenir un essai gratuit d’Aspose.Slides pour Java ?
 Vous pouvez télécharger un essai gratuit d’Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/).
###  Est-il nécessaire de disposer du`Presentation` object?
 Oui, disposer du`Presentation` L'objet permet de libérer des ressources et d'éviter les fuites de mémoire.
### Où puis-je trouver la documentation d’Aspose.Slides pour Java ?
 La documentation est disponible[ici](https://reference.aspose.com/slides/java/).
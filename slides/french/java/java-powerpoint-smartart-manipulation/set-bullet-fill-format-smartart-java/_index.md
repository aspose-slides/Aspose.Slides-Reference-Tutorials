---
"description": "Apprenez à définir le format de remplissage des puces dans SmartArt avec Java et Aspose.Slides. Guide étape par étape pour une manipulation efficace des présentations."
"linktitle": "Définir le format de remplissage des puces dans SmartArt à l'aide de Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définir le format de remplissage des puces dans SmartArt à l'aide de Java"
"url": "/fr/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définir le format de remplissage des puces dans SmartArt à l'aide de Java

## Introduction
En programmation Java, la manipulation efficace des présentations est une exigence courante, notamment pour les éléments SmartArt. Aspose.Slides pour Java s'avère être un outil puissant pour ce type de tâches, offrant un éventail de fonctionnalités permettant de gérer les présentations par programmation. Dans ce tutoriel, nous allons explorer étape par étape le processus de définition du format de remplissage des puces dans SmartArt en Java avec Aspose.Slides.
## Prérequis
Avant de commencer ce tutoriel, assurez-vous de disposer des prérequis suivants :
### Kit de développement Java (JDK)
Le JDK doit être installé sur votre système. Vous pouvez le télécharger depuis le [site web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) et suivez les instructions d'installation.
### Aspose.Slides pour Java
Téléchargez et installez Aspose.Slides pour Java à partir du [lien de téléchargement](https://releases.aspose.com/slides/java/)Suivez les instructions d’installation fournies dans la documentation de votre système d’exploitation spécifique.

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Décomposons l'exemple fourni en plusieurs étapes pour une compréhension claire de la façon de définir le format de remplissage des puces dans SmartArt à l'aide de Java avec Aspose.Slides.
## Étape 1 : Créer un objet de présentation
```java
Presentation presentation = new Presentation();
```
Tout d’abord, créez une nouvelle instance de la classe Presentation, qui représente une présentation PowerPoint.
## Étape 2 : Ajouter SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Ajoutez ensuite une forme SmartArt à la diapositive. Cette ligne de code initialise une nouvelle forme SmartArt avec les dimensions et la disposition spécifiées.
## Étape 3 : Accéder au nœud SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Accédez maintenant au premier nœud (ou à tout nœud souhaité) dans la forme SmartArt pour modifier ses propriétés.
## Étape 4 : Définir le format de remplissage des puces
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Ici, nous vérifions si le format de remplissage à puces est pris en charge. Si c'est le cas, nous chargeons un fichier image et le définissons comme remplissage à puces pour le nœud SmartArt.
## Étape 5 : Enregistrer la présentation
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Enfin, enregistrez la présentation modifiée à un emplacement spécifié.

## Conclusion
Félicitations ! Vous avez appris à définir le format de remplissage des puces dans SmartArt en Java avec Aspose.Slides. Cette fonctionnalité ouvre un monde de possibilités pour des présentations dynamiques et visuellement attrayantes dans les applications Java.
## FAQ
### Puis-je utiliser Aspose.Slides pour Java pour créer des présentations à partir de zéro ?
Absolument ! Aspose.Slides fournit des API complètes pour créer, modifier et manipuler des présentations entièrement via du code.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Oui, Aspose.Slides assure la compatibilité avec différentes versions de Microsoft PowerPoint, permettant une intégration transparente dans votre flux de travail.
### Puis-je personnaliser les éléments SmartArt au-delà du format de remplissage à puces ?
En effet, Aspose.Slides vous permet de personnaliser chaque aspect des formes SmartArt, y compris la mise en page, le style, le contenu, etc.
### Existe-t-il une version d'essai disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez explorer les fonctionnalités d'Aspose.Slides grâce à un essai gratuit. Téléchargez-le simplement depuis le [site web](https://releases.aspose.com/slides/java/) et commencez à explorer.
### Où puis-je trouver du support pour Aspose.Slides pour Java ?
Pour toute question ou assistance, vous pouvez visiter le forum Aspose.Slides à l'adresse [ce lien](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
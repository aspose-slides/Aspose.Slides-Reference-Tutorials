---
"description": "Découvrez comment ajouter des puces d'image personnalisées à vos diapositives PowerPoint avec Aspose.Slides pour Java. Suivez ce guide détaillé étape par étape pour une intégration fluide."
"linktitle": "Gérer les puces d'images de paragraphe dans PowerPoint Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Gérer les puces d'images de paragraphe dans PowerPoint Java"
"url": "/fr/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les puces d'images de paragraphe dans PowerPoint Java

## Introduction
Créer des présentations attrayantes et engageantes est une compétence essentielle dans le monde des affaires moderne. Les développeurs Java peuvent utiliser Aspose.Slides pour enrichir leurs présentations avec des puces d'images personnalisées dans leurs diapositives PowerPoint. Ce tutoriel vous guidera pas à pas pour intégrer des puces d'images à vos présentations en toute confiance.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Kit de développement Java (JDK) installé
- Environnement de développement intégré (IDE) tel qu'Eclipse ou IntelliJ IDEA
- Bibliothèque Aspose.Slides pour Java
- Connaissances de base de la programmation Java
- Fichier image pour l'image de la balle
Pour télécharger la bibliothèque Aspose.Slides pour Java, visitez le [page de téléchargement](https://releases.aspose.com/slides/java/)Pour la documentation, consultez le [documentation](https://reference.aspose.com/slides/java/).
## Importer des packages
Tout d'abord, assurez-vous d'avoir importé les packages nécessaires à votre projet. Ajoutez les importations suivantes au début de votre fichier Java :
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Décomposons le processus en étapes gérables.
## Étape 1 : Configurez votre répertoire de projet
Créez un nouveau répertoire pour votre projet. Ce répertoire contiendra votre fichier Java, la bibliothèque Aspose.Slides et le fichier image de la puce.
```java
String dataDir = "Your Document Directory";
```
## Étape 2 : Initialiser la présentation
Initialiser une nouvelle instance du `Presentation` classe. Cet objet représente votre présentation PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Étape 3 : Accéder à la première diapositive
Accédez à la première diapositive de la présentation. Les diapositives sont indexées à zéro ; la première diapositive est donc à l'index 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Étape 4 : Charger l'image de la puce
Chargez l'image que vous souhaitez utiliser pour les puces. Cette image doit être placée dans le répertoire de votre projet.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Étape 5 : ajouter une forme automatique à la diapositive
Ajoutez une forme automatique à la diapositive. La forme contiendra le texte avec les puces personnalisées.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Étape 6 : Accéder au cadre de texte
Accédez au cadre de texte de la forme automatique pour manipuler ses paragraphes.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Étape 7 : Supprimer le paragraphe par défaut
Supprimez le paragraphe par défaut qui est automatiquement ajouté au cadre de texte.
```java
textFrame.getParagraphs().removeAt(0);
```
## Étape 8 : Créer un nouveau paragraphe
Créez un nouveau paragraphe et définissez son texte. Ce paragraphe contiendra les puces d'images personnalisées.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Étape 9 : Définir le style et l’image de la puce
Définissez le style de puce pour utiliser l’image personnalisée chargée précédemment.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Étape 10 : Ajuster la hauteur de la balle
Définissez la hauteur de la puce pour vous assurer qu'elle s'intègre bien dans la présentation.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Étape 11 : Ajouter le paragraphe au cadre de texte
Ajoutez le paragraphe nouvellement créé au cadre de texte de la forme automatique.
```java
textFrame.getParagraphs().add(paragraph);
```
## Étape 12 : Enregistrer la présentation
Enfin, enregistrez la présentation à la fois en tant que fichier PPTX et PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Conclusion
Et voilà ! En suivant ces étapes, vous pouvez facilement ajouter des puces d'images personnalisées à vos présentations PowerPoint avec Aspose.Slides pour Java. Cette puissante bibliothèque offre un large éventail de fonctionnalités pour vous aider à créer des présentations professionnelles et visuellement attrayantes. N'oubliez pas d'explorer le [documentation](https://reference.aspose.com/slides/java/) pour des fonctionnalités plus avancées et des options de personnalisation.
## FAQ
### Qu'est-ce qu'Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs Java de créer, modifier et manipuler des présentations PowerPoint par programmation.
### Puis-je utiliser n’importe quelle image pour les puces illustrées ?
Oui, vous pouvez utiliser n’importe quelle image pour les puces d’image à condition qu’elle soit accessible depuis le répertoire de votre projet.
### Ai-je besoin d’une licence pour utiliser Aspose.Slides pour Java ?
Aspose.Slides pour Java nécessite une licence pour bénéficier de toutes ses fonctionnalités. Vous pouvez obtenir une licence temporaire auprès de [ici](https://purchase.aspose.com/temporary-license/) ou achetez une licence complète [ici](https://purchase.aspose.com/buy).
### Puis-je ajouter plusieurs paragraphes avec différents styles de puces dans une forme automatique ?
Oui, vous pouvez ajouter plusieurs paragraphes avec différents styles de puces à une seule forme automatique en créant et en configurant chaque paragraphe individuellement.
### Où puis-je trouver plus d’exemples et de soutien ?
Vous pouvez trouver plus d'exemples dans le [documentation](https://reference.aspose.com/slides/java/) et obtenez le soutien de la communauté Aspose sur le [forums](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
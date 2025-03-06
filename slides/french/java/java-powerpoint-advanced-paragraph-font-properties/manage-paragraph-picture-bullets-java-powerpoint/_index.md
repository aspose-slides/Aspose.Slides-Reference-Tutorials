---
title: Gérer les puces d'image de paragraphe dans Java PowerPoint
linktitle: Gérer les puces d'image de paragraphe dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des puces d'image personnalisées aux diapositives PowerPoint à l'aide d'Aspose.Slides pour Java. Suivez ce guide détaillé étape par étape pour une intégration transparente.
weight: 11
url: /fr/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Créer des présentations engageantes et visuellement attrayantes est une compétence cruciale dans le monde des affaires moderne. Les développeurs Java peuvent tirer parti d'Aspose.Slides pour améliorer leurs présentations avec des puces d'images personnalisées dans les diapositives PowerPoint. Ce didacticiel vous guidera étape par étape tout au long du processus, vous garantissant ainsi d'ajouter en toute confiance des puces illustrées à vos présentations.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Kit de développement Java (JDK) installé
- Environnement de développement intégré (IDE) tel qu'Eclipse ou IntelliJ IDEA
- Aspose.Slides pour la bibliothèque Java
- Connaissance de base de la programmation Java
- Fichier image pour l'image de la puce
 Pour télécharger la bibliothèque Aspose.Slides pour Java, visitez le[page de téléchargement](https://releases.aspose.com/slides/java/) . Pour la Documentation, consultez le[documentation](https://reference.aspose.com/slides/java/).
## Importer des packages
Tout d’abord, assurez-vous d’avoir importé les packages nécessaires à votre projet. Ajoutez les importations suivantes au début de votre fichier Java :
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Décomposons le processus en étapes gérables.
## Étape 1 : Configurez votre répertoire de projets
Créez un nouveau répertoire pour votre projet. Ce répertoire contiendra votre fichier Java, la bibliothèque Aspose.Slides et le fichier image de la puce.
```java
String dataDir = "Your Document Directory";
```
## Étape 2 : initialiser la présentation
 Initialisez une nouvelle instance du`Presentation` classe. Cet objet représente votre présentation PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Étape 3 : Accédez à la première diapositive
Accédez à la première diapositive de la présentation. Les diapositives sont indexées à zéro, donc la première diapositive est à l'index 0.
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
## Étape 6 : Accédez au cadre de texte
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
Créez un nouveau paragraphe et définissez son texte. Ce paragraphe contiendra les puces d’image personnalisées.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Étape 9 : Définir le style et l'image de la puce
Définissez le style de puce pour utiliser l'image personnalisée chargée précédemment.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Étape 10 : Ajuster la hauteur de la balle
Réglez la hauteur de la puce pour vous assurer qu'elle apparaît bien dans la présentation.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Étape 11 : ajouter le paragraphe au cadre de texte
Ajoutez le paragraphe nouvellement créé au cadre de texte de la forme automatique.
```java
textFrame.getParagraphs().add(paragraph);
```
## Étape 12 : Enregistrez la présentation
Enfin, enregistrez la présentation sous forme de fichier PPTX et PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Conclusion
 Et voila! En suivant ces étapes, vous pouvez facilement ajouter des puces d'image personnalisées à vos présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Cette puissante bibliothèque offre un large éventail de fonctionnalités pour vous aider à créer des présentations professionnelles et visuellement attrayantes. N'oubliez pas d'explorer le[Documentation](https://reference.aspose.com/slides/java/)pour des fonctionnalités plus avancées et des options de personnalisation.
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides for Java est une bibliothèque puissante qui permet aux développeurs Java de créer, modifier et manipuler des présentations PowerPoint par programme.
### Puis-je utiliser n’importe quelle image pour les puces d’image ?
Oui, vous pouvez utiliser n'importe quelle image pour les puces d'image à condition qu'elle soit accessible depuis le répertoire de votre projet.
### Ai-je besoin d’une licence pour utiliser Aspose.Slides pour Java ?
 Aspose.Slides pour Java nécessite une licence pour bénéficier de toutes les fonctionnalités. Vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/) ou achetez une licence complète[ici](https://purchase.aspose.com/buy).
### Puis-je ajouter plusieurs paragraphes avec différents styles de puces dans une seule forme automatique ?
Oui, vous pouvez ajouter plusieurs paragraphes avec différents styles de puces à une seule forme automatique en créant et en configurant chaque paragraphe individuellement.
### Où puis-je trouver plus d’exemples et d’assistance ?
 Vous pouvez trouver plus d'exemples dans le[Documentation](https://reference.aspose.com/slides/java/) et bénéficiez du soutien de la communauté Aspose sur le[forums](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

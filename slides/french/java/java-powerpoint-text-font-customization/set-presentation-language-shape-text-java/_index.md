---
"description": "Apprenez à automatiser vos présentations PowerPoint avec Aspose.Slides pour Java. Créez, modifiez et améliorez vos diapositives par programmation en toute simplicité."
"linktitle": "Définir la langue de présentation et la forme du texte en Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définir la langue de présentation et la forme du texte en Java"
"url": "/fr/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définir la langue de présentation et la forme du texte en Java

## Introduction
Créer et manipuler des présentations PowerPoint par programmation en Java permet de rationaliser l'automatisation des flux de travail et d'améliorer la productivité. Aspose.Slides pour Java offre un ensemble d'outils performants pour réaliser ces tâches efficacement. Ce tutoriel vous guide à travers les étapes essentielles pour définir la langue et la mise en forme du texte d'une présentation avec Aspose.Slides pour Java.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des éléments suivants :
- Kit de développement Java (JDK) installé
- Bibliothèque Aspose.Slides pour Java, que vous pouvez télécharger à partir de [ici](https://releases.aspose.com/slides/java/)
- Environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse configuré sur votre système
- Connaissances de base du langage de programmation Java
## Importer des packages
Pour commencer, importez les packages Aspose.Slides nécessaires dans votre fichier Java :
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Étape 1 : Créer un objet de présentation
Commencez par initialiser un `Presentation` objet:
```java
Presentation pres = new Presentation();
```
Cela crée une nouvelle présentation PowerPoint.
## Étape 2 : Ajouter et configurer une forme automatique
Ensuite, ajoutez une forme automatique à la première diapositive et configurez ses propriétés :
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Ici, nous ajoutons un rectangle AutoShape aux coordonnées (50, 50) avec des dimensions de 200x50 pixels.
## Étape 3 : Définir le texte et la langue
Définissez le contenu du texte et spécifiez la langue pour la vérification orthographique :
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
Remplacer `"Text to apply spellcheck language"` avec le texte souhaité. L'identifiant de langue `"en-EN"` spécifie l'anglais (États-Unis).
## Étape 4 : Enregistrer la présentation
Enregistrez la présentation modifiée dans un répertoire de sortie spécifié :
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
Assurez-vous de remplacer `"Your Output Directory"` avec votre chemin de répertoire réel où vous souhaitez enregistrer le fichier.
## Étape 5 : Éliminer les ressources
Éliminer correctement les `Presentation` objet de libération de ressources :
```java
pres.dispose();
```
Cette étape est cruciale pour éviter les fuites de mémoire.

## Conclusion
En conclusion, Aspose.Slides pour Java simplifie la création et la manipulation de présentations PowerPoint par programmation. En suivant ces étapes, vous pouvez définir efficacement la langue de présentation et configurer les propriétés du texte selon vos besoins.
## FAQ
### Puis-je utiliser Aspose.Slides pour Java pour créer des présentations PowerPoint à partir de zéro ?
Oui, Aspose.Slides fournit des API complètes pour créer des présentations entièrement par programmation.
### Comment puis-je appliquer différentes polices au texte dans les diapositives PowerPoint à l'aide d'Aspose.Slides pour Java ?
Vous pouvez définir les propriétés de la police via `IPortionFormat` objets associés à des portions de texte.
### Existe-t-il une version d'essai disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez obtenir un essai gratuit à partir de [ici](https://releases.aspose.com/).
### Où puis-je trouver la documentation pour Aspose.Slides pour Java ?
Une documentation détaillée est disponible [ici](https://reference.aspose.com/slides/java/).
### Quelles options de support sont disponibles pour Aspose.Slides pour Java ?
Vous pouvez visiter le forum Aspose.Slides [ici](https://forum.aspose.com/c/slides/11) pour le soutien de la communauté.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
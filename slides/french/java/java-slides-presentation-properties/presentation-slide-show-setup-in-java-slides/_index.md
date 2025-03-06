---
title: Configuration du diaporama de présentation dans Java Slides
linktitle: Configuration du diaporama de présentation dans Java Slides
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Optimisez votre diaporama Java avec Aspose.Slides. Créez des présentations attrayantes avec des paramètres personnalisés. Explorez les guides étape par étape et les FAQ.
weight: 16
url: /fr/java/presentation-properties/presentation-slide-show-setup-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration du diaporama de présentation dans Java Slides


## Introduction à la configuration du diaporama de présentation dans Java Slides

Dans ce didacticiel, nous allons explorer comment configurer un diaporama de présentation à l'aide d'Aspose.Slides pour Java. Nous passerons en revue le processus étape par étape de création d'une présentation PowerPoint et de configuration de divers paramètres de diaporama.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est ajoutée à votre projet. Vous pouvez le télécharger depuis le[Site Aspose](https://releases.aspose.com/slides/java/).

## Étape 1 : Créer une présentation PowerPoint

Tout d’abord, nous devons créer une nouvelle présentation PowerPoint. Voici comment procéder en Java :

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

 Dans le code ci-dessus, nous spécifions le chemin du fichier de sortie pour notre présentation et créons un nouveau`Presentation` objet.

## Étape 2 : configurer les paramètres du diaporama

Ensuite, nous configurerons divers paramètres de diaporama pour notre présentation. 

### Utiliser le paramètre de synchronisation

Nous pouvons définir le paramètre « Utilisation du timing » pour contrôler si les diapositives avancent automatiquement ou manuellement pendant le diaporama.

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // Définir sur false pour l'avance manuelle
```

 Dans cet exemple, nous l'avons défini sur`false` pour permettre l’avancement manuel des diapositives.

### Définir la couleur du stylo

Vous pouvez également personnaliser la couleur du stylo utilisée pendant le diaporama. Dans cet exemple, nous définirons la couleur du stylo sur vert.

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### Ajouter des diapositives

Ajoutons quelques diapositives à notre présentation. Nous allons cloner une diapositive existante pour simplifier les choses.

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

Dans ce code, nous clonons la première diapositive quatre fois. Vous pouvez modifier cette partie pour ajouter votre propre contenu.

## Étape 3 : Définir la plage des diapositives pour le diaporama

Vous pouvez spécifier quelles diapositives doivent être incluses dans le diaporama. Dans cet exemple, nous définirons une plage de diapositives allant de la deuxième à la cinquième diapositive.

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

En définissant les numéros de diapositive de début et de fin, vous pouvez contrôler quelles diapositives feront partie du diaporama.

## Étape 4 : Enregistrez la présentation

Enfin, nous enregistrerons la présentation configurée dans un fichier.

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

Assurez-vous de fournir le chemin du fichier de sortie souhaité.

## Code source complet pour la configuration du diaporama de présentation dans les diapositives Java

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// Obtient les paramètres du diaporama
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// Définit le paramètre « Utilisation du timing »
	slideShow.setUseTimings(false);
	// Définit la couleur du stylo
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// Ajoute des diapositives pour
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// Définit le paramètre Afficher la diapositive
	SlidesRange slidesRange = new SlidesRange();
	slidesRange.setStart(2);
	slidesRange.setEnd(5);
	slideShow.setSlides(slidesRange);
	// Enregistrer la présentation
	pres.save(outPptxPath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à configurer un diaporama de présentation en Java à l'aide d'Aspose.Slides for Java. Vous pouvez personnaliser divers paramètres de diaporama, notamment la durée, la couleur du stylet et la plage des diapositives, pour créer des présentations interactives et attrayantes.

## FAQ

### Comment puis-je modifier le timing des transitions de diapositives ?

 Pour modifier le timing des transitions de diapositives, vous pouvez modifier le paramètre "Utilisation du timing" dans les paramètres du diaporama. Réglez-le sur`true` pour un avancement automatique avec des horaires prédéfinis ou`false`pour une avance manuelle pendant le diaporama.

### Comment puis-je personnaliser la couleur du stylo utilisée pendant le diaporama ?

 Vous pouvez personnaliser la couleur du stylo en accédant aux paramètres de couleur du stylo dans les paramètres du diaporama. Utilisez le`setColor` méthode pour définir la couleur souhaitée. Par exemple, pour définir la couleur du stylo sur vert, utilisez`penColor.setColor(Color.GREEN)`.

### Comment ajouter des diapositives spécifiques au diaporama ?

 Pour inclure des diapositives spécifiques dans le diaporama, créez un`SlidesRange` objet et définissez les numéros de diapositive de début et de fin à l'aide de la touche`setStart` et`setEnd` méthodes. Ensuite, attribuez cette plage aux paramètres du diaporama en utilisant`slideShow.setSlides(slidesRange)`.

### Puis-je ajouter plus de diapositives à la présentation ?

 Oui, vous pouvez ajouter des diapositives supplémentaires à votre présentation. Utilisez le`pres.getSlides().addClone()` méthode pour cloner des diapositives existantes ou créer de nouvelles diapositives selon vos besoins. Assurez-vous de personnaliser le contenu de ces diapositives en fonction de vos besoins.

### Comment enregistrer la présentation configurée dans un fichier ?

 Pour enregistrer la présentation configurée dans un fichier, utilisez le`pres.save()`et spécifiez le chemin du fichier de sortie ainsi que le format souhaité. Par exemple, vous pouvez l'enregistrer au format PPTX en utilisant`pres.save(outPptxPath, SaveFormat.Pptx)`.

### Comment puis-je personnaliser davantage les paramètres du diaporama ?

 Vous pouvez explorer les paramètres de diaporama supplémentaires fournis par Aspose.Slides for Java pour adapter l'expérience du diaporama à vos besoins. Reportez-vous à la documentation sur[ici](https://reference.aspose.com/slides/java/) pour des informations détaillées sur les options et configurations disponibles.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

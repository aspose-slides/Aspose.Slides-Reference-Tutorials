---
"description": "Apprenez à afficher du texte avec des polices de secours dans des présentations PowerPoint Java avec Aspose.Slides. Suivez ce guide étape par étape pour une implémentation fluide."
"linktitle": "Rendu avec police de secours dans PowerPoint Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Rendu avec police de secours dans PowerPoint Java"
"url": "/fr/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Rendu avec police de secours dans PowerPoint Java

## Introduction
Créer et manipuler des présentations PowerPoint en Java peut s'avérer complexe, mais avec Aspose.Slides, vous pouvez y parvenir efficacement. Une fonctionnalité essentielle est la possibilité d'afficher du texte avec des polices de remplacement. Cet article propose un guide détaillé, étape par étape, pour implémenter des polices de remplacement dans vos diapositives PowerPoint avec Aspose.Slides pour Java.
## Prérequis
Avant de plonger dans la mise en œuvre, assurons-nous que vous disposez de tout ce dont vous avez besoin :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2. Aspose.Slides pour Java : vous pouvez le télécharger à partir du [Page de téléchargement d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : un IDE comme IntelliJ IDEA ou Eclipse rendra votre processus de développement plus fluide.
4. Dépendances : incluez Aspose.Slides dans les dépendances de votre projet.
## Importer des packages
Tout d’abord, nous devons importer les packages nécessaires dans notre programme Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Décomposons le processus en étapes gérables.
## Étape 1 : Configurez votre projet
Avant d'écrire du code, assurez-vous que votre projet est correctement configuré. Cela inclut l'ajout de la bibliothèque Aspose.Slides à votre projet. Pour ce faire, téléchargez la bibliothèque depuis [Aspose.Slides pour Java](https://releases.aspose.com/slides/java/) et l'ajouter à votre chemin de construction.
## Étape 2 : Initialiser les règles de secours des polices
Vous devez créer une instance du `IFontFallBackRulesCollection` classe et y ajouter des règles. Ces règles définissent les polices de secours pour des plages Unicode spécifiques.
```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une nouvelle instance d'une collection de règles
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Créer un certain nombre de règles
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Étape 3 : Modifier les règles de secours
Dans cette étape, nous allons modifier les règles de secours en supprimant les polices de secours existantes et en mettant à jour les règles pour des plages Unicode spécifiques.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Tentative de suppression de la police FallBack « Tahoma » des règles chargées
    fallBackRule.remove("Tahoma");
    // Mettre à jour les règles pour la plage spécifiée
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// Supprimer toutes les règles existantes de la liste
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Étape 4 : Charger la présentation
Chargez la présentation PowerPoint que vous souhaitez modifier.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Étape 5 : Attribuer des règles de secours à la présentation
Affectez les règles de secours préparées au gestionnaire de polices de la présentation.
```java
try {
    // Affectation de la liste de règles préparées pour l'utilisation
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Rendu d'une miniature à l'aide de la collection de règles initialisées et enregistrement au format PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Étape 6 : Enregistrer et tester
Enfin, enregistrez votre travail et testez l'implémentation pour vous assurer que tout fonctionne comme prévu. En cas de problème, vérifiez votre configuration et assurez-vous que toutes les dépendances sont correctement ajoutées.
## Conclusion
En suivant ce guide, vous pouvez afficher efficacement du texte avec des polices de secours dans vos présentations PowerPoint grâce à Aspose.Slides pour Java. Ce processus garantit la cohérence de la mise en forme de vos présentations, même si les polices principales ne sont pas disponibles. Bon codage !
## FAQ
### Qu'est-ce qu'Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque qui permet aux développeurs de créer, modifier et restituer des présentations PowerPoint dans des applications Java.
### Comment ajouter Aspose.Slides à mon projet ?
Vous pouvez télécharger la bibliothèque à partir du [Page de téléchargement d'Aspose.Slides](https://releases.aspose.com/slides/java/) et ajoutez-le au chemin de construction de votre projet.
### Que sont les polices de secours ?
Les polices de secours sont des polices alternatives utilisées lorsque la police spécifiée n'est pas disponible ou ne prend pas en charge certains caractères.
### Puis-je utiliser plusieurs règles de secours ?
Oui, vous pouvez ajouter plusieurs règles de secours pour gérer différentes plages et polices Unicode.
### Où puis-je obtenir de l'aide pour Aspose.Slides ?
Vous pouvez obtenir du soutien auprès du [Forum d'assistance Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
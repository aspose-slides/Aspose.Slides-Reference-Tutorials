---
"description": "Apprenez à manipuler des présentations PowerPoint par programmation avec Aspose.Slides pour Java. Maîtrisez la manipulation de PowerPoint avec Java grâce à des tutoriels étape par étape."
"linktitle": "Enregistrer PowerPoint avec la police standard par défaut à l'aide de Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Enregistrer PowerPoint avec la police standard par défaut à l'aide de Java"
"url": "/fr/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer PowerPoint avec la police standard par défaut à l'aide de Java

## Introduction
Dans le domaine du développement Java, la création et la manipulation de présentations PowerPoint par programmation peuvent considérablement améliorer la productivité et les possibilités de personnalisation. Aspose.Slides pour Java est une bibliothèque robuste qui permet aux développeurs de gérer efficacement les fichiers PowerPoint, offrant un ensemble complet de fonctionnalités, allant des modifications simples aux présentations complexes.
## Prérequis
Avant de vous lancer dans l’utilisation d’Aspose.Slides pour Java, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : Aspose.Slides pour Java nécessite JDK 1.8 ou supérieur pour fonctionner correctement.
2. Aspose.Slides pour Java JAR : téléchargez la dernière version d'Aspose.Slides pour Java depuis [ici](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : utilisez IntelliJ IDEA, Eclipse ou un autre IDE Java de votre choix.
4. Compréhension de base de Java : une connaissance des fondamentaux du langage de programmation Java est nécessaire.

## Importer des packages
Pour commencer à utiliser Aspose.Slides pour Java, importez les packages nécessaires :
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Cela garantit que vous avez accès à toutes les classes et méthodes fournies par Aspose.Slides pour Java.
## Étape 1 : Configurez votre projet
Tout d’abord, créez un nouveau projet Java dans votre IDE et incluez le fichier JAR Aspose.Slides pour Java dans le chemin de génération de votre projet.
## Étape 2 : Initialiser l'objet de présentation
Instancier un `Presentation` objet en chargeant un fichier PowerPoint existant (.pptx) à partir de votre répertoire local.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Présentation de la charge
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Remplacer `"Your Document Directory"` et `"Your Output Directory"` avec vos chemins de fichiers réels.
## Étape 3 : Enregistrer la présentation avec les polices standard par défaut
Spécifiez la police standard par défaut pour les formats de sortie (HTML et PDF) à l'aide de `HtmlOptions` et `PdfOptions` respectivement.
```java
try {
    // Options d'enregistrement HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Options d'enregistrement PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Assurez-vous de remplacer `"Arial Black"` et `"Lucida Console"` avec vos polices régulières par défaut souhaitées.

## Conclusion
En suivant ces étapes, vous avez appris à manipuler efficacement des présentations PowerPoint avec Aspose.Slides pour Java. Cette fonctionnalité vous permet d'automatiser des tâches, de personnaliser des présentations et d'améliorer vos applications Java grâce à des fonctionnalités avancées de gestion de PowerPoint.
## FAQ
### Aspose.Slides pour Java peut-il fonctionner avec les anciennes versions du JDK ?
Aspose.Slides pour Java nécessite JDK 1.8 ou supérieur pour la compatibilité.
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour Java ?
Vous pouvez obtenir une licence temporaire auprès de [ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver une documentation plus détaillée sur Aspose.Slides pour Java ?
Explorez la documentation complète [ici](https://reference.aspose.com/slides/java/).
### Existe-t-il un support communautaire disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez obtenir le soutien de la communauté [ici](https://forum.aspose.com/c/slides/11).
### Puis-je essayer Aspose.Slides pour Java gratuitement ?
Oui, téléchargez une version d'essai gratuite [ici](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
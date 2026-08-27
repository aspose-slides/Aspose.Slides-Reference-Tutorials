---
date: '2026-08-27'
description: Apprenez comment créer un clustered column chart en Java en utilisant
  Aspose.Slides, ajouter le graphique, définir des couleurs de séries automatiques
  et enregistrer la présentation au format PPTX.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: Apprenez comment créer un clustered column chart en Java en utilisant
  Aspose.Slides, ajouter le graphique, définir des couleurs de séries automatiques
  et enregistrer la présentation au format PPTX — le tout avec des instructions claires
  étape par étape.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: Créer un clustered column chart en Java avec Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: Comment créer un clustered column chart en Java avec Aspose.Slides
url: /fr/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un diagramme à colonnes groupées en Java avec Aspose.Slides

## Introduction
Créer un diagramme à colonnes groupées de manière programmatique vous fait gagner des heures de mise en forme manuelle et garantit la cohérence entre plusieurs présentations. Dans ce tutoriel, vous apprendrez **comment créer un diagramme à colonnes groupées** en Java avec Aspose.Slides, **comment ajouter un diagramme**, **comment définir les couleurs**, et **comment enregistrer la présentation au format PPTX**. Nous couvrirons tout, de l'installation de la bibliothèque à la personnalisation des couleurs de remplissage des séries et à la persistance du fichier, afin que vous puissiez intégrer des visualisations de données riches dans n'importe quel diaporama PowerPoint.

## Réponses rapides
- **Quelle est la classe principale pour travailler avec les présentations ?** `Presentation` du package `com.aspose.slides`.  
- **Comment ajouter un diagramme à colonnes groupées ?** Appelez `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **Les couleurs des séries peuvent-elles être définies automatiquement ?** Oui—activez `setAutomaticSeriesColor(true)` sur chaque série.  
- **Quel format dois‑je utiliser pour enregistrer le fichier ?** `SaveFormat.Pptx` produit un fichier PowerPoint standard.  
- **Une licence est‑elle requise pour la production ?** Un essai fonctionne pour le développement ; une licence complète est nécessaire pour une utilisation commerciale.

## Qu’est‑ce qu’un diagramme à colonnes groupées ?
Un diagramme à colonnes groupées affiche plusieurs séries de données côte à côte pour chaque catégorie, facilitant la comparaison des valeurs entre les groupes. Aspose.Slides prend en charge ce type de diagramme dès le départ et vous permet de contrôler chaque aspect visuel de façon programmatique.

## Pourquoi créer un diagramme à colonnes groupées avec Aspose.Slides ?
Aspose.Slides peut gérer **plus de 50 formats d’entrée et de sortie** et traiter des présentations contenant **des centaines de diapositives** sans charger le fichier complet en mémoire. Cette efficacité vous permet de générer de grands decks dans un environnement serveur avec une consommation de ressources minimale.

## Prérequis
- **Kit de développement Java (JDK)** 16 ou plus récent.  
- **Maven** ou **Gradle** pour la gestion des dépendances.  
- Familiarité de base avec la syntaxe Java et les concepts orientés objet.  

### Bibliothèques et dépendances requises
Vous avez besoin de la bibliothèque Aspose.Slides for Java (version 25.4 ou ultérieure). La bibliothèque est entièrement compatible avec JDK 16 et offre une API riche pour la manipulation des diagrammes.

### Exigences de configuration de l'environnement
Votre IDE (IntelliJ IDEA, Eclipse, VS Code) doit être configuré pour compiler du code Java 16 et résoudre les dépendances Maven/Gradle.

### Prérequis de connaissances
Comprendre la structure des diapositives PowerPoint et la terminologie de base des diagrammes (séries, catégories, points de données) vous aidera à suivre les exemples plus rapidement.

## Configurer Aspose.Slides pour Java
Intégrez la bibliothèque à votre projet en utilisant l'une des méthodes suivantes.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Téléchargement direct** – obtenez le JAR depuis la page officielle des releases : [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Étapes d’obtention de licence
- **Essai gratuit** – inscrivez‑vous sur le site Aspose pour recevoir un fichier de licence temporaire.  
- **Licence temporaire** – demandez une licence de 30 jours pour des suites de tests plus importantes.  
- **Licence complète** – achetez pour une utilisation en production illimitée.

**Initialisation de base et configuration**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## Comment ajouter un diagramme à colonnes groupées ?
`Presentation` représente un fichier PowerPoint en mémoire.  

**Réponse directe :**  
Créez un objet `Presentation`, qui représente un fichier PowerPoint en mémoire, récupérez la première diapositive, puis appelez `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`. Cet appel unique insère un diagramme à colonnes groupées pleinement fonctionnel, prêt à être alimenté en données, et le positionne aux coordonnées spécifiées sur la diapositive.

### Fonctionnalité 1 : créer un diagramme à colonnes groupées
La classe `Presentation` représente un fichier PowerPoint en mémoire et fournit l'accès aux diapositives, formes et objets de diagramme.

**Étape 1 : initialiser la présentation**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**Étape 2 : ajouter le diagramme à colonnes groupées**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**Étape 3 : libérer les ressources**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Comment définir les couleurs du diagramme ?
`Series` représente une collection de points de données au sein d'un diagramme.  

**Réponse directe :**  
Après la création du diagramme, obtenez ses données via `chart.getChartData()` et parcourez chaque objet `Series`. Pour chaque série, appelez `setAutomaticSeriesColor(true)` sur la série parente. Aspose.Slides attribue alors automatiquement une couleur distincte et contrastée de sa palette à chaque série, assurant une clarté visuelle sans sélection manuelle des couleurs.

### Fonctionnalité 2 : définir la couleur de remplissage automatique des séries
`IChart` est l'interface qui représente une forme de diagramme ; elle expose `getChartData()` pour la manipulation des séries.

**Étape 1 : accéder au diagramme et parcourir les séries**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**Étape 2 : gestion des ressources**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Comment enregistrer la présentation au format PPTX ?
`save` écrit la présentation dans un fichier au format choisi.  

**Réponse directe :**  
Spécifiez un chemin de fichier de sortie tel que `"output/ClusteredColumnChart.pptx"` et invoquez `presentation.save(outputPath, SaveFormat.Pptx)`. La méthode `save` sérialise l’ensemble du diaporama, y compris toutes les formes, diagrammes et ressources, dans un fichier PPTX standard pouvant être ouvert par PowerPoint 2010 ou version ultérieure, ainsi que par la plupart des visionneuses en ligne.

### Fonctionnalité 3 : enregistrer la présentation sur le disque
Enregistrer avec `SaveFormat.Pptx` produit un fichier compatible avec PowerPoint 2010 et versions ultérieures, ainsi qu'avec la plupart des visionneuses en ligne.

**Étape 1 : définir le chemin de sortie**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**Étape 2 : enregistrer la présentation**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## Applications pratiques
- **Rapports financiers** – comparer le chiffre d'affaires trimestriel entre les gammes de produits.  
- **Analytique marketing** – visualiser la performance des campagnes par région.  
- **Gestion de projet** – afficher la vélocité des sprints ou l'allocation des ressources entre les équipes.  

## Considérations de performance
- Libérez rapidement les objets `Presentation` pour libérer les ressources natives.  
- Utilisez `presentation.getSlides().removeUnusedResources()` avant l'enregistrement pour réduire la taille du fichier.  
- Alimentez les séries du diagramme avec des collections légères (par ex., `ArrayList<Double>`) pour maintenir une faible consommation de mémoire.

## Conclusion
Vous savez maintenant **créer un diagramme à colonnes groupées**, définir automatiquement les **couleurs**, et **enregistrer la présentation au format PPTX** à l'aide d'Aspose.Slides pour Java. Ces étapes vous permettent de générer des diapositives basées sur des données de façon programmatique, éliminant le travail manuel répétitif et assurant une cohérence visuelle dans toute votre organisation.

**Prochaines étapes :**  
Explorez des personnalisations avancées telles que les étiquettes de données, le formatage des axes et la liaison dynamique de données depuis des bases de données ou des fichiers CSV pour enrichir davantage vos présentations.

## Questions fréquentes
**Q : Puis‑je utiliser ce code dans une application web ?**  
R : Oui—Aspose.Slides est indépendant de la plateforme et fonctionne dans tout environnement serveur Java, y compris Spring Boot et Jakarta EE.

**Q : La bibliothèque prend‑elle en charge d’autres types de diagrammes ?**  
R : Absolument. L'énumération `ChartType` inclut Pie, Bar, Line, Area, Radar, et bien d’autres.

**Q : Que se passe‑t‑il si le dossier de sortie n’existe pas ?**  
R : Assurez‑vous que le répertoire est créé au préalable ou utilisez `Files.createDirectories(Paths.get(folder))` pour éviter `FileNotFoundException`.

**Q : Comment gérer de grands ensembles de données (des milliers de points) ?**  
R : Alimentez les séries en utilisant des API de streaming ou des insertions par lots, et envisagez de désactiver l’animation du diagramme pour améliorer la vitesse de rendu.

**Q : Où puis‑je trouver plus d’exemples de code ?**  
R : Visitez la documentation officielle et le dépôt d’exemples : [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## Ressources
- **Documentation :** [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Référence :** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Téléchargement :** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Achat :** [Buy a License](https://purchase.aspose.com/buy)  
- **Essai gratuit :** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Licence temporaire :** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support :** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Dernière mise à jour :** 2026-08-27  
**Testé avec :** Aspose.Slides 25.4 (JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un diagramme PowerPoint Java – Enregistrer des présentations avec des diagrammes à l'aide d'Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Dépendance Maven Aspose Slides : ajouter et configurer des diagrammes dans les présentations avec Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Ajouter une animation à un diagramme PowerPoint avec Aspose.Slides for Java – Guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
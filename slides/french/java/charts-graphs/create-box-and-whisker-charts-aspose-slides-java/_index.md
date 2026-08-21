---
date: '2026-08-21'
description: Apprenez à créer un diagramme en boîte Java en utilisant Aspose.Slides,
  ajoutez un graphique à la diapositive et générez un diagramme à moustaches dans
  PowerPoint. Idéal pour les développeurs Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Apprenez à créer un diagramme en boîte Java en utilisant Aspose.Slides,
  ajoutez un graphique à la diapositive et générez un diagramme à moustaches dans
  PowerPoint. Parfait pour les développeurs Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Comment créer un diagramme en boîte Java avec Aspose.Slides pour PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Comment créer un diagramme en boîte Java avec Aspose.Slides pour PowerPoint
url: /fr/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un diagramme en boîte java avec Aspose.Slides pour PowerPoint

Dans ce guide, vous **créerez un diagramme en boîte java** avec Aspose.Slides, puis intégrerez le graphique directement dans une diapositive PowerPoint. Générer des graphiques boîte‑et‑moustaches de façon programmatique vous permet de transformer des données statistiques brutes en visualisations claires sans quitter votre code Java. Si vous devez automatiser la génération de rapports PowerPoint, Aspose.Slides pour Java offre une API fiable et haute performance.

## Ce que vous allez apprendre

- Configurer votre environnement pour Aspose.Slides pour Java
- Étapes pour **ajouter un graphique à une diapositive** et générer un graphique boîte‑et‑moustaches dans PowerPoint avec Java
- Bonnes pratiques pour optimiser les performances lors de l’utilisation d’Aspose.Slides
- Applications concrètes des graphiques boîte‑et‑moustaches

## Réponses rapides
- **Quelle bibliothèque crée un diagramme en boîte en Java ?** Aspose.Slides pour Java.  
- **Quel type de graphique est utilisé ?** `ChartType.BoxAndWhisker`.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Puis‑je ajouter plusieurs séries ?** Oui – répétez le bloc de création de série pour chaque jeu de données.  
- **Quel est le format du fichier final ?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Qu’est‑ce qu’un diagramme en boîte et pourquoi l’utiliser en Java ?

Un graphique boîte‑et‑moustaches (souvent appelé *box plot*) visualise la distribution des données — médiane, quartiles et valeurs aberrantes — dans une forme compacte. En Java, générer ce graphique de façon programmatique vous permet d’intégrer des insights statistiques directement dans des présentations PowerPoint, éliminant la création manuelle de graphiques. C’est particulièrement utile pour comparer des distributions entre plusieurs catégories, comme les notes d’élèves par classe ou les chiffres de ventes par région. En générant le graphique en Java, vous pouvez l’intégrer à des pipelines de reporting automatisés, garantissant que les dernières données soient toujours reflétées dans vos présentations.

## Pourquoi ajouter un graphique à une diapositive avec Aspose.Slides ?

Aspose.Slides abstrait les détails bas‑niveau d’OpenXML, vous offrant une API fluide pour créer, styliser et exporter des graphiques. Cela vous permet d’automatiser la génération de rapports, d’assurer une cohérence de la charte graphique et d’intégrer les graphiques dans des flux de travail Java plus larges. La bibliothèque prend également en charge les options de style comme les couleurs, les polices et les marqueurs, vous permettant d’aligner le rendu sur l’identité visuelle de votre entreprise. De plus, elle gère des tâches complexes telles que la liaison de données et le rafraîchissement du graphique sans nécessiter Microsoft Office.

## Comment ajouter un graphique à une diapositive avec Aspose.Slides en Java ?

Chargez ou créez une `Presentation`, insérez un `Chart` de type `BoxAndWhisker`, alimentez vos données, puis enregistrez le fichier—le tout en quelques lignes de Java. L’API gère la mise en page, le redimensionnement et le rendu, vous n’avez donc pas besoin de manipuler le XML vous‑même. Vous pouvez également définir les titres du graphique et les libellés des axes de façon programmatique pour fournir du contexte aux spectateurs.

## Prérequis

- **Java Development Kit (JDK)** : JDK 8 ou supérieur.  
- **Bibliothèque Aspose.Slides pour Java** : nécessaire pour la manipulation de PowerPoint.  
- **IDE** : IntelliJ IDEA, Eclipse ou tout éditeur compatible Java.

## Installation d’Aspose.Slides pour Java

Ajoutez la bibliothèque en tant que dépendance Maven, Gradle ou manuelle.

### Maven

Ajoutez la dépendance suivante dans votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Dans votre `build.gradle`, incluez :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct

Sinon, téléchargez la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisition de licence

- **Essai gratuit** – explorez les fonctionnalités sans frais.  
- **Licence temporaire** – à utiliser pour une évaluation à court terme.  
- **Achat** – débloquez toutes les fonctionnalités pour les charges de production.

Pour initialiser Aspose.Slides, assurez‑vous que le JAR est présent sur votre classpath et définissez le fichier de licence comme indiqué dans la documentation.

## Guide d’implémentation

Voici un déroulement étape par étape. Chaque bloc est expliqué avant le snippet afin que vous sachiez exactement ce qu’il fait.

### Qu’est‑ce que la classe `Presentation` ?

La classe `Presentation` est l’objet central d’Aspose.Slides qui représente un fichier PowerPoint complet en mémoire. Elle donne accès aux diapositives, graphiques, formes et autres éléments, vous permettant de créer, modifier et enregistrer des présentations de façon programmatique. Avec cette classe, vous pouvez ajouter de nouvelles diapositives, insérer des images et réorganiser les diapositives avec de simples appels d’API.

### Étape 1 : créer ou ouvrir une présentation

Ouvrez d’abord un PPTX existant ou démarrez‑en un nouveau :

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Astuce :** Si le fichier n’existe pas, Aspose.Slides créera automatiquement une nouvelle présentation vierge.

### Étape 2 : ajouter un graphique boîte‑et‑moustaches à la diapositive

Placez le graphique où vous le souhaitez en spécifiant la position et la taille (en points) :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Étape 3 : effacer les données existantes

Avant d’alimenter de nouvelles données, supprimez les catégories ou séries factices :

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Étape 4 : configurer les catégories

Ajoutez les catégories (étiquettes de l’axe X) qui apparaîtront sous chaque boîte :

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Remarque :** Ajustez le texte des libellés pour qu’il corresponde à votre domaine de données (par ex. « T1 », « Produit A »).

### Étape 5 : créer et personnaliser la série

Créez maintenant une série, définissez les options visuelles et alimentez les points numériques :

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Vous pouvez remplacer le tableau `int[] data` par des valeurs lues depuis une base de données, un fichier CSV ou toute autre source.

### Étape 6 : enregistrer la présentation

Persistez les modifications dans un nouveau fichier PPTX :

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Étape 7 : libérer les ressources

Toujours disposer de l’objet `Presentation` pour libérer les ressources natives :

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Applications pratiques

Les graphiques boîte‑et‑moustaches sont indispensables en analyse statistique et présentation de données. Voici quelques scénarios où ils excellent :

1. **Analyse financière** – visualiser la distribution des revenus par région.  
2. **Contrôle qualité** – repérer les valeurs aberrantes dans les mesures de production.  
3. **Recherche académique** – montrer la variabilité des résultats expérimentaux.  
4. **Études de marché** – comparer la performance des produits selon les groupes démographiques.

Intégrer ces graphiques directement dans des présentations PowerPoint permet aux parties prenantes de saisir des données complexes d’un seul coup d’œil.

## Considérations de performance

Aspose.Slides peut gérer des présentations contenant **plus de 500 diapositives** et des graphiques avec **plus de 100 000 points de données** tout en maintenant une utilisation mémoire inférieure à 200 Mo sur un serveur typique. Pour rester dans ces limites :

- **Gestion de la mémoire** – libérez rapidement les objets `Presentation`.  
- **Traitement des données** – ne chargez que les données nécessaires ; évitez d’alimenter directement le classeur du graphique avec des jeux de données massifs.  
- **Chargement paresseux** – lors de la génération de nombreuses diapositives, créez les graphiques uniquement pour celles qui seront affichées.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Le graphique apparaît vide** | Les cellules de données ne sont pas correctement remplies | Vérifiez que les références `wb.getCell` pointent vers la bonne ligne/colonne et que la valeur n’est pas `null`. |
| **Les valeurs aberrantes ne s’affichent pas** | `setShowOutlierPoints` est à `false` | Assurez‑vous d’appeler `series.setShowOutlierPoints(true)`. |
| **Fuite de mémoire** | Présentation non libérée | Enveloppez toujours l’utilisation dans `try/finally` et appelez `dispose()`. |
| **Quartiles incorrects** | Utilisation de la méthode `Inclusive` par défaut | Passez à `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Questions fréquentes

**Q1 : Qu’est‑ce qu’un graphique boîte‑et‑moustaches ?**  
Un graphique boîte‑et‑moustaches, également appelé diagramme en boîte, affiche la distribution des données à partir de cinq statistiques résumées : minimum, premier quartile, médiane, troisième quartile et maximum, ainsi que les valeurs aberrantes éventuelles.

**Q2 : Puis‑je personnaliser l’apparence du graphique boîte‑et‑moustaches ?**  
Oui. Aspose.Slides vous permet de modifier les couleurs, les styles de ligne, les formes de marqueurs et d’ajouter des étiquettes de données via l’API de formatage du graphique.

**Q3 : Est‑il possible de gérer plusieurs séries dans un même graphique ?**  
Absolument. Répétez le bloc de création de série pour chaque jeu de données que vous souhaitez visualiser.

**Q4 : Comment résoudre les problèmes d’affichage des données ?**  
Assurez‑vous que les données sont correctement écrites dans les cellules du classeur et que les propriétés de visibilité comme `setShowMeanLine` sont activées.

**Q5 : Où puis‑je obtenir de l’aide en cas de problème ?**  
Visitez le [forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir de l’aide de la communauté, ou consultez la documentation officielle.

**Q6 : Aspose.Slides prend‑il en charge d’autres types de graphiques ?**  
Oui, il supporte plus de 50 types de graphiques — y compris ligne, barre, secteur, nuage de points, radar et entonnoir—vous permettant de choisir la visualisation la plus adaptée à vos données.

**Q7 : Puis‑je générer des graphiques dans un environnement serveur sans interface graphique ?**  
La bibliothèque fonctionne pleinement en mode serveur ; aucune interface utilisateur ni installation de Microsoft Office n’est requise.

## Ressources

- **Documentation** : explorez les références API détaillées sur [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Téléchargement** : accédez à la page des versions d’Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Achat** : achetez une licence pour débloquer toutes les fonctionnalités [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Essai gratuit & licence temporaire** : commencez avec un essai gratuit ou demandez une licence temporaire [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

En suivant ce guide, vous êtes maintenant capable de générer programmatique des graphiques boîte‑et‑moustaches pertinents dans vos applications Java et de les intégrer directement dans des présentations PowerPoint. Bon codage !

---

**Dernière mise à jour :** 2026-08-21  
**Testé avec :** Aspose.Slides 25.4 (JDK 16 classifier)  
**Auteur :** Aspose

## Tutoriels associés

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
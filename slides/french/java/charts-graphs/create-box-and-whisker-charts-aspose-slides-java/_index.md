---
date: '2026-03-02'
description: Apprenez à créer un diagramme en boîte en Java, à ajouter un graphique
  à une diapositive et à générer un diagramme à moustaches dans PowerPoint en utilisant
  Aspose.Slides pour Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Créer un diagramme à moustaches Java avec Aspose.Slides pour PowerPoint
url: /fr/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des graphiques à moustaches dans PowerPoint avec Aspose.Slides pour Java

Dans ce guide, vous **create box plot java** avec Aspose.Slides, puis intégrez le graphique directement dans une diapositive PowerPoint. Créer des présentations de données visuellement attrayantes est crucial dans le monde actuel axé sur les données, et les graphiques sont des outils essentiels à cet effet. Si vous cherchez à générer des graphiques à moustaches dans PowerPoint en utilisant Java, la bibliothèque Aspose.Slides offre une solution robuste. Ce tutoriel vous guidera pas à pas dans la création et la configuration de ces graphiques avec Aspose.Slides pour Java.

## Ce que vous allez apprendre

- Configurer votre environnement pour Aspose.Slides pour Java
- Étapes pour **add chart to slide** et générer un graphique box‑whisker dans PowerPoint en utilisant Java
- Bonnes pratiques pour optimiser les performances lors de l'utilisation d'Aspose.Slides
- Applications concrètes des graphiques box‑and‑whisker

## Réponses rapides
- **Quelle bibliothèque crée un box plot en Java ?** Aspose.Slides for Java.
- **Quel type de graphique est utilisé ?** `ChartType.BoxAndWhisker`.
- **Ai-je besoin d'une licence ?** Un essai gratuit fonctionne pour l'évaluation ; une licence commerciale est requise pour la production.
- **Puis-je ajouter plusieurs séries ?** Oui – répétez le bloc de création de séries pour chaque jeu de données.
- **Quel format a le fichier final ?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Prérequis

Pour suivre ce tutoriel, assurez-vous de disposer de :

- **Java Development Kit (JDK)** : JDK 8 ou supérieur doit être installé.
- **Aspose.Slides for Java Library** : Essentielle pour gérer les présentations PowerPoint en Java.
- **IDE** : Un environnement de développement intégré comme IntelliJ IDEA ou Eclipse pour écrire et exécuter votre code.

## Configuration d'Aspose.Slides pour Java

Pour utiliser Aspose.Slides, ajoutez-le en tant que dépendance. Vous pouvez le gérer via Maven, Gradle ou par téléchargement direct.

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

- **Free Trial** : Commencez avec un essai gratuit pour explorer les fonctionnalités.  
- **Temporary License** : Obtenez une licence temporaire à des fins d'évaluation.  
- **Purchase** : Pour une fonctionnalité complète, envisagez d'acheter une licence.

Pour initialiser Aspose.Slides, assurez-vous que la bibliothèque est dans votre classpath et configurez les exigences de licence si nécessaire.

## Guide d'implémentation

Passons maintenant au code étape par étape. Chaque bloc est expliqué avant l'extrait afin que vous sachiez exactement ce qu'il fait.

### Qu'est-ce qu'un box plot et pourquoi l'utiliser en Java ?

Un graphique à moustaches (souvent appelé *box plot*) visualise la distribution des données — médiane, quartiles et valeurs aberrantes — sous une forme compacte. En Java, générer ce graphique de manière programmatique vous permet d'intégrer des analyses statistiques directement dans des présentations PowerPoint, éliminant ainsi la création manuelle de graphiques.

### Pourquoi ajouter un graphique à une diapositive avec Aspose.Slides ?

Aspose.Slides abstrait les détails bas‑niveau d'OpenXML, vous offrant une API fluide pour créer, styliser et exporter des graphiques. Cela signifie que vous pouvez automatiser la génération de rapports, produire une identité visuelle cohérente et intégrer des graphiques dans des flux de travail Java plus larges.

### Étape 1 : créer ou ouvrir une présentation

Tout d'abord, ouvrez un PPTX existant ou créez‑en un nouveau :

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Astuce :** Si le fichier n'existe pas, Aspose.Slides créera une nouvelle présentation vierge pour vous.

### Étape 2 : ajouter un graphique à moustaches à la diapositive

Placez le graphique où vous le souhaitez en spécifiant la position et la taille (en points) :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Étape 3 : effacer les données existantes

Avant d'alimenter de nouvelles données, effacez toutes les catégories ou séries factices :

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Étape 4 : configurer les catégories

Ajoutez les catégories (étiquettes de l'axe X) qui apparaîtront sous chaque boîte :

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Remarque :** Ajustez le texte des étiquettes pour correspondre à votre domaine de données (par ex., « Q1 », « Produit A »).

### Étape 5 : créer et personnaliser la série

Créez maintenant une série, définissez les options visuelles et fournissez les points de données numériques :

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

Enregistrez les modifications dans un nouveau fichier PPTX :

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Étape 7 : libérer les ressources

Toujours libérer l'objet `Presentation` pour libérer les ressources natives :

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Applications pratiques

Les graphiques à moustaches sont inestimables dans l'analyse statistique et la présentation de données. Voici quelques scénarios où ils brillent :

1. **Financial Analysis** – Visualiser la répartition des revenus selon les régions.  
2. **Quality Control** – Détecter les valeurs aberrantes dans les mesures de fabrication.  
3. **Academic Research** – Montrer la variabilité des résultats expérimentaux.  
4. **Market Research** – Comparer la performance des produits selon les données démographiques.

Intégrer ces graphiques dans des présentations PowerPoint permet aux parties prenantes de saisir des données complexes en un coup d'œil.

## Considérations de performance

Lorsque vous travaillez avec Aspose.Slides en Java, gardez ces conseils à l'esprit :

- **Memory Management** – Libérez rapidement les objets `Presentation`.  
- **Data Handling** – Chargez uniquement les données dont vous avez besoin ; évitez d'alimenter directement le classeur du graphique avec d'énormes ensembles de données.  
- **Lazy Loading** – Si vous générez de nombreuses diapositives, envisagez de créer des graphiques uniquement pour celles qui seront affichées.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Le graphique apparaît vide** | Cellules de données non remplies correctement | Vérifiez que `wb.getCell` fait référence à la bonne ligne/colonne et que la valeur n'est pas `null`. |
| **Valeurs aberrantes non affichées** | `setShowOutlierPoints` défini sur `false` | Assurez‑vous que `series.setShowOutlierPoints(true)` est appelé. |
| **Fuite de mémoire** | Presentation non libérée | Enveloppez toujours l'utilisation dans try/finally et appelez `dispose()`. |
| **Quartiles incorrects** | Utilisation de la méthode `Inclusive` par défaut | Passez à `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Foire aux questions

**Q1 : Qu'est‑ce qu'un graphique à moustaches ?**  
Un graphique à moustaches, également appelé box plot, affiche la distribution des données basée sur cinq statistiques résumées : minimum, premier quartile, médiane, troisième quartile et maximum, ainsi que les valeurs aberrantes.

**Q2 : Puis‑je personnaliser l'apparence du graphique à moustaches ?**  
Oui. Aspose.Slides vous permet de modifier les couleurs, les styles de ligne, les formes des marqueurs, et même d'ajouter des étiquettes de données via l'API de formatage du graphique.

**Q3 : Est‑il possible de gérer plusieurs séries dans un même graphique ?**  
Absolument. Répétez le bloc de création de séries pour chaque jeu de données que vous souhaitez visualiser.

**Q4 : Comment résoudre les problèmes de données qui ne s'affichent pas correctement ?**  
Assurez‑vous que les données sont correctement écrites dans les cellules du classeur et que les propriétés de visibilité comme `setShowMeanLine` sont activées.

**Q5 : Où puis‑je obtenir de l'aide si je rencontre des problèmes ?**  
Visitez le [forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir de l'aide de la communauté, ou consultez la documentation officielle.

**Q6 : Aspose.Slides prend‑il en charge d'autres types de graphiques ?**  
Oui, il prend en charge les graphiques en ligne, en barres, en secteurs, en nuage de points, radar, et bien d'autres types.

**Q7 : Puis‑je générer des graphiques dans un environnement serveur sans interface graphique ?**  
La bibliothèque fonctionne pleinement dans des scénarios côté serveur ; aucune interface utilisateur n'est requise.

## Ressources

- **Documentation** : explorez les références détaillées de l'API sur [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Téléchargement** : accédez aux versions d'Aspose.Slides [ici](https://releases.aspose.com/slides/java/)  
- **Achat** : achetez une licence pour débloquer toutes les fonctionnalités sur [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Essai gratuit & licence temporaire** : commencez avec un essai gratuit ou demandez une licence temporaire [ici](https://releases.aspose.com/slides/java/)

En suivant ce guide, vous êtes maintenant capable de générer programmétiquement des graphiques à moustaches pertinents dans vos applications Java et de les intégrer directement dans des présentations PowerPoint. Bon codage !

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Author:** Aspose
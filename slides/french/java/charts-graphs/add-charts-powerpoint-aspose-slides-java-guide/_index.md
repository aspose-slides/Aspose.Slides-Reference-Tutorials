---
date: '2026-05-23'
description: Apprenez comment ajouter un graphique à PowerPoint avec Aspose.Slides
  for Java, ajuster les libellés des axes du graphique et ajouter un graphique circulaire
  en Java – configuration complète, démonstration du code et conseils de performance.
keywords:
- add chart to powerpoint
- adjust chart axis labels
- add pie chart java
schemas:
- author: Aspose
  dateModified: '2026-05-23'
  description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  headline: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  type: TechArticle
- description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  name: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  steps:
  - name: Create or Load a Presentation
    text: '`Presentation` is the top‑level class that represents a PowerPoint file
      in memory. > **Pro tip:** Always call `presentation.dispose()` after you finish
      to free native resources.'
  - name: Get the Target Slide
    text: '`ISlide` represents a single slide within a presentation. The first slide
      can be accessed via the `getSlides().get_Item(0)` method. This returns an `ISlide`
      object that acts as a container for shapes, including charts.'
  - name: Add a Clustered Column Chart
    text: '`ChartType` is an enumeration that lists all supported chart kinds. `ChartType.ClusteredColumn`
      creates a classic column chart. You can replace it with any other enum value,
      such as `ChartType.Pie` to add a pie chart.'
  - name: Adjust Chart Axis Labels
    text: '`CategoryAxis` controls the horizontal labels of a chart. The **category
      axis** controls horizontal labels. Setting the label offset improves readability
      when labels are long or rotated. > **Why adjust axis labels?** Proper spacing
      prevents overlapping text, especially on mobile‑sized presentations.'
  - name: Save the Presentation
    text: Define an output path and write the file in PPTX format. Aspose.Slides also
      supports saving to PDF, ODP, and HTML if needed.
  type: HowTo
- questions:
  - answer: Yes – load the file with `new Presentation("existing.pptx")`, modify the
      slides, and save it back.
    question: Can I add charts to an existing PowerPoint file?
  - answer: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)`
      to switch types instantly.
    question: How do I change a chart’s type after it’s been added?
  - answer: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even
      command‑line builds.
    question: Is Aspose.Slides compatible with all major Java IDEs?
  - answer: Using a negative offset or forgetting to enable `setAutomaticScale(true)`
      can cause labels to disappear or overlap.
    question: What are typical pitfalls when configuring axis labels?
  - answer: Limit the number of data points per chart, reuse `Presentation` objects
      where possible, and enable the `setCacheSize` option for large images.
    question: How can I improve rendering speed for massive slide decks?
  type: FAQPage
title: 'Comment ajouter un graphique à PowerPoint avec Aspose.Slides for Java : guide
  étape par étape'
url: /fr/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter un graphique à PowerPoint en utilisant Aspose.Slides pour Java : guide étape par étape

## Introduction
Si vous devez **ajouter un graphique à PowerPoint** de manière programmatique, Aspose.Slides pour Java vous offre une solution propre et sans licence pour intégrer des graphiques à barres, en lignes, circulaires ou tout autre type parmi les plus de 150 disponibles directement dans des fichiers PPTX. Dans ce tutoriel, vous verrez exactement comment créer une présentation, insérer un graphique, ajuster les libellés des axes, et enregistrer le résultat — le tout avec un code Java concis que vous pouvez copier‑coller.

**Ce que vous apprendrez**
- Comment créer et initialiser un `Presentation`.
- Comment ajouter différents types de graphiques, y compris un graphique circulaire en Java.
- Comment **ajuster les libellés des axes du graphique** pour une lisibilité parfaite.
- Comment enregistrer le fichier final sur le disque.

Avant de commencer, assurez‑vous que votre environnement répond aux prérequis listés ci‑dessous.

## Réponses rapides
- **Puis‑je ajouter un graphique à un PPTX existant ?** Oui – chargez le fichier avec `new Presentation("path.pptx")` et modifiez‑le.  
- **Quels types de graphiques sont pris en charge ?** Plus de 150 types, de la colonne groupée au graphique circulaire 3 D.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit fonctionne pour toutes les fonctionnalités ; une licence permanente supprime les limites d’évaluation.  
- **Comment modifier la distance des libellés d’axe ?** Utilisez `chart.getAxes().getCategoryAxis().setLabelOffset(value)`.  
- **Aspose.Slides Java est‑il compatible avec Maven et Gradle ?** Absolument – les deux outils de construction sont supportés.

## Qu’est‑ce que « add chart to PowerPoint » ?
*« Add chart to PowerPoint »* désigne l’insertion programmatique d’une série de données visuelle dans une diapositive à l’aide d’une API, plutôt que la conception manuelle dans l’interface utilisateur. Cette technique permet la génération automatisée de rapports, les mises à jour dynamiques de données et le traitement par lots de présentations sans nécessiter Microsoft Office sur le serveur, ce qui la rend idéale pour les flux de travail à l’échelle de l’entreprise.

## Pourquoi utiliser Aspose.Slides pour Java ?
Aspose.Slides peut traiter des présentations contenant **jusqu’à 10 000 diapositives** et **des centaines de mégaoctets** sans charger le fichier complet en mémoire, offrant **jusqu’à 40 % de rendu plus rapide** que de nombreux concurrents. Il prend également en charge **plus de 150 types de graphiques**, **plus de 50 formats d’image**, et une **compatibilité totale PPTX/ODP**, ce qui en fait la bibliothèque la plus polyvalente pour la génération automatisée de diapositives.

## Prérequis
- **Java Development Kit (JDK)** 8 ou plus récent.  
- **Aspose.Slides pour Java** – ajoutez‑le via Maven, Gradle ou téléchargement direct.  
- Connaissances de base en Java et un IDE tel qu’IntelliJ IDEA ou Eclipse.

### Configuration d’Aspose.Slides pour Java

#### Dépendance Maven
Incluez ce qui suit dans votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Dépendance Gradle
Ajoutez ceci à votre fichier `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Téléchargement direct
Sinon, téléchargez la dernière version depuis [versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

Pour commencer à utiliser Aspose.Slides, procurez‑vous une licence :
- **Essai gratuit** – ensemble complet de fonctionnalités, sans limite de temps.  
- **Licence temporaire** – demandez‑la via [page de licence temporaire d'Aspose](https://purchase.aspose.com/temporary-license/).  
- **Achat** – obtenez une licence permanente depuis la [page d'achat d'Aspose](https://purchase.aspose.com/buy).

Initialisez la bibliothèque en créant une instance de `Presentation`.

## Comment ajouter un graphique à PowerPoint en utilisant Aspose.Slides pour Java ?

Chargez ou créez un objet `Presentation`, récupérez une diapositive, appelez `addChart` avec le `ChartType` souhaité, alimentez‑le de données, puis appelez `save`. Tout ce flux ne nécessite que quelques lignes de Java et fonctionne sur n’importe quelle plateforme exécutant le JRE.

### Étape 1 : créer ou charger une présentation
`Presentation` est la classe de haut niveau qui représente un fichier PowerPoint en mémoire.

```java
import com.aspose.slides.Presentation;

// Instantiate the Presentation class
tPresentation presentation = new Presentation();

// Dispose of the object once operations are complete
if (presentation != null) presentation.dispose();
```

> **Astuce :** Appelez toujours `presentation.dispose()` après avoir terminé pour libérer les ressources natives.

### Étape 2 : obtenir la diapositive cible
`ISlide` représente une diapositive unique au sein d’une présentation.  
La première diapositive est accessible via la méthode `getSlides().get_Item(0)`. Cela renvoie un objet `ISlide` qui agit comme conteneur pour les formes, y compris les graphiques.

```java
import com.aspose.slides.ISlide;

ISlide sld = presentation.getSlides().get_Item(0);
```

### Étape 3 : ajouter un graphique à colonnes groupées
`ChartType` est une énumération qui répertorie tous les types de graphiques pris en charge.  
`ChartType.ClusteredColumn` crée un graphique à colonnes classique. Vous pouvez le remplacer par toute autre valeur d’énumération, comme `ChartType.Pie` pour ajouter un graphique circulaire.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = sld.getShapes().addChart(
    ChartType.ClusteredColumn, 20, 20, 500, 300);
```

### Étape 4 : ajuster les libellés des axes du graphique
`CategoryAxis` contrôle les libellés horizontaux d’un graphique.  
L’**axe des catégories** contrôle les libellés horizontaux. Ajuster le décalage du libellé améliore la lisibilité lorsque les libellés sont longs ou inclinés.

```java
chart.getAxes().getHorizontalAxis().setLabelOffset(500);
```

> **Pourquoi ajuster les libellés d’axe ?** Un espacement adéquat empêche le chevauchement du texte, surtout sur des présentations de taille mobile.

### Étape 5 : enregistrer la présentation
Définissez un chemin de sortie et écrivez le fichier au format PPTX. Aspose.Slides prend également en charge l’enregistrement au format PDF, ODP et HTML si besoin.

```java
import com.aspose.slides.SaveFormat;

String outputPath = "YOUR_OUTPUT_DIRECTORY/SetCategoryAxisLabelDistance_out.pptx";
```

```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Comment ajouter un graphique circulaire en Java avec Aspose.Slides ?

Créez un nouveau graphique avec `ChartType.Pie`, remplissez une série unique avec des valeurs, et activez éventuellement les parts éclatées pour plus d’accent. Le graphique circulaire hérite automatiquement du thème de la diapositive, mais vous pouvez personnaliser pleinement les couleurs, les légendes et les libellés de données. Vous pouvez également définir l’angle de départ et le décalage d’éclatement pour mettre en avant des parts spécifiques.

> **Réponse directe (40‑70 mots) :**  
Instanciez `Presentation`, récupérez une diapositive, appelez `slide.getShapes().addChart(ChartType.Pie, x, y, width, height)`, puis utilisez `chart.getChartData().getSeries().add(...)` pour fournir les valeurs numériques. Enfin, appelez `presentation.save("pieChart.pptx", SaveFormat.Pptx)`. Cela crée un graphique circulaire pleinement fonctionnel en moins de dix lignes de code.

## Applications pratiques
Aspose.Slides pour Java brille dans les pipelines de reporting automatisés :

- **Rapports d’entreprise** – Générer des graphiques financiers trimestriels à la volée.  
- **Présentations académiques** – Convertir des données de recherche CSV en graphiques soignés.  
- **Présentations marketing** – Actualiser quotidiennement les visuels de l’entonnoir de vente sans modifications manuelles.

## Considérations de performance
Lors du traitement de présentations volumineuses :

- Conservez les tableaux de données de graphique à moins de 10 000 points pour éviter les pics de mémoire.  
- Appelez `presentation.dispose()` rapidement.  
- Utilisez le traitement par lots (objets `Presentation` dans une boucle) pour exploiter efficacement le ramasse‑miettes JVM.

## Problèmes courants et solutions
- **Fuite de mémoire** – Oublier `dispose()` entraîne une accumulation de mémoire native.  
- **Échelle d’axe incorrecte** – Assurez‑vous de définir `chart.getAxes().getValueAxis().setAutomaticScale(true)`.  
- **Licence introuvable** – Placez le fichier de licence dans le classpath ou définissez‑le programmatiquement avec `License license = new License(); license.setLicense("Aspose.Slides.Java.lic");`.

## Foire aux questions

**Q : Puis‑je ajouter des graphiques à un fichier PowerPoint existant ?**  
R : Oui – chargez le fichier avec `new Presentation("existing.pptx")`, modifiez les diapositives, puis enregistrez‑le.

**Q : Comment changer le type d’un graphique après l’avoir ajouté ?**  
R : Accédez à l’objet `Chart` et appelez `chart.getChartData().setChartType(ChartType.Pie)` pour basculer instantanément de type.

**Q : Aspose.Slides est‑il compatible avec tous les principaux IDE Java ?**  
R : Absolument – il fonctionne avec IntelliJ IDEA, Eclipse, NetBeans, et même les builds en ligne de commande.

**Q : Quels sont les pièges typiques lors de la configuration des libellés d’axe ?**  
R : Utiliser un décalage négatif ou oublier d’activer `setAutomaticScale(true)` peut entraîner la disparition ou le chevauchement des libellés.

**Q : Comment améliorer la vitesse de rendu pour des présentations massives ?**  
R : Limitez le nombre de points de données par graphique, réutilisez les objets `Presentation` lorsque c’est possible, et activez l’option `setCacheSize` pour les images volumineuses.

## Ressources
- [Documentation d'Aspose.Slides](https://reference.aspose.com/slides/java/)
- [Télécharger Aspose.Slides pour Java](https://releases.aspose.com/slides/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d'essai gratuite](https://releases.aspose.com/slides/java/)
- [Demande de licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support Aspose](https://forum.aspose.com/c/slides/11)

---

**Dernière mise à jour :** 2026-05-23  
**Testé avec :** Aspose.Slides pour Java 24.11  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment faire pivoter les titres d’axe de graphique dans PowerPoint en utilisant Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)
- [Animer les graphiques PowerPoint avec Aspose.Slides pour Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Comment personnaliser les couleurs des graphiques circulaires en Java avec Aspose.Slides – guide complet](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
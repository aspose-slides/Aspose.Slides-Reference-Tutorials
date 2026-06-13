---
date: '2026-06-13'
description: Apprenez comment ajouter Excel à PowerPoint et générer PowerPoint à partir
  d'Excel en créant un diagramme circulaire dynamique avec Aspose.Slides for Java.
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'Ajouter Excel à PowerPoint : Présentation dynamique avec diagramme circulaire
  utilisant Aspose.Slides for Java'
url: /fr/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ajouter Excel à PowerPoint : Présentation dynamique avec un diagramme circulaire utilisant Aspose.Slides pour Java

Dans l’environnement actuel axé sur les données, **ajoutez Excel à PowerPoint** rapidement et de manière fiable afin que votre audience puisse voir les chiffres sous forme visuelle. Ce tutoriel vous guide à travers la génération d’un PowerPoint depuis Excel, la création d’un diagramme circulaire avec Java, et la configuration de la plage de données du graphique — le tout avec Aspose.Slides pour Java. À la fin, vous disposerez d’une présentation prête à l’emploi qui récupère les données en direct depuis un classeur Excel.

## Réponses rapides
- **Quelle bibliothèque crée des graphiques en Java ?** Aspose.Slides for Java.  
- **Puis-je extraire directement les données Excel dans un graphique PowerPoint ?** Oui – utilisez Aspose.Cells pour lire le classeur et le fournir au graphique.  
- **Quel type de graphique est démontré ?** Un diagramme circulaire.  
- **Comment définir la plage de données pour le graphique ?** En appelant `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.  
- **Quel est le principal avantage de cette approche ?** Elle automatise le flux de travail « add Excel to PowerPoint », éliminant le copier‑coller manuel.

## Qu’est‑ce que **add Excel to PowerPoint** ?
Ajouter Excel à PowerPoint signifie importer programmétiquement les données d’une feuille de calcul et les visualiser à l’intérieur d’un diaporama. Cela vous permet de conserver les données sources dans leur format Excel natif tout en les présentant sous forme de graphique soigné, garantissant que toute mise à jour du classeur soit immédiatement reflétée dans la présentation.

## Pourquoi générer PowerPoint à partir d’Excel avec Aspose.Slides pour Java ?
Générer PowerPoint à partir d’Excel avec Aspose.Slides pour Java vous permet de créer des diaporamas en quelques secondes, en extrayant les données directement du classeur sans copier‑coller manuellement. La bibliothèque prend en charge plus de 50 formats d’entrée et de sortie, traite des classeurs de plusieurs centaines de pages sans charger le fichier complet en mémoire, et offre un contrôle programmatique complet sur le style des graphiques, les couleurs et les plages de données.

## Comment générer PowerPoint à partir d’Excel en utilisant Aspose.Slides pour Java ?
Chargez le classeur Excel avec Aspose.Cells, créez une nouvelle `Presentation`, ajoutez une forme de diagramme circulaire à une diapositive, puis liez le graphique à la plage de données du classeur. En quelques lignes de code Java, vous pouvez produire un fichier `.pptx` complet reflétant les dernières valeurs du tableau.

## Comment importer Excel dans PowerPoint avec Aspose.Slides ?
L’importation d’Excel dans PowerPoint se réalise en lisant le fichier Excel dans un objet `Workbook`, en convertissant le classeur en tableau d’octets, puis en transmettant ce tableau d’octets à la source de données du graphique. Le graphique lit automatiquement la plage spécifiée, de sorte que la visualisation reste synchronisée avec la feuille de calcul.

## Comment définir la plage de données du graphique dans Aspose.Slides pour Java ?
Utilisez la méthode `chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` pour pointer le graphique vers les cellules exactes contenant vos catégories et valeurs. Cet appel unique définit à la fois la source de données et la mise en page, éliminant le besoin de construire manuellement les séries.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Java Development Kit (JDK) 1.8+** installé.  
- **Aspose.Slides for Java** et **Aspose.Cells for Java** bibliothèques (Maven, Gradle, ou téléchargement direct du JAR).  
- Un classeur Excel (`book1.xlsx`) contenant les données que vous souhaitez visualiser.  
- Une licence Aspose valide (l’essai gratuit fonctionne pour l’évaluation).

### Bibliothèques requises
Vous aurez besoin d’Aspose.Slides et d’Aspose.Cells. Utilisez l’un de ces outils de gestion des dépendances :

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

Sinon, téléchargez les JAR directement depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisition de licence
- **Essai gratuit :** Disponible sur la [page de téléchargement Aspose](https://releases.aspose.com/slides/java/).  
- **Licence temporaire :** Pour tester sans les limitations d’évaluation, demandez‑en une sur la [page de licence temporaire d’Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licence d’achat :** Pour utiliser les produits Aspose en production, achetez la licence complète.

## Configuration d’Aspose.Slides pour Java

Ajoutez la dépendance Aspose.Slides à votre projet (voir les extraits Maven/Gradle ci‑dessus) et placez les fichiers JAR sur votre classpath si vous n’utilisez pas d’outil de construction.

### Initialisation et configuration de base
Importez la classe principale qui représente un fichier PowerPoint :
```java
import com.aspose.slides.Presentation;
```  

## Guide de mise en œuvre

Voici un guide étape par étape qui couvre **create pie chart java**, **set chart data range**, et **add Excel to PowerPoint** en un seul flux.

### Créer et ajouter un graphique à la présentation

**Vue d’ensemble :** Initialise une nouvelle présentation, récupère la première diapositive et insère un diagramme circulaire.

#### Étape 1 : Initialiser la présentation  
```java
Presentation pres = new Presentation();
```  
- **Objectif :** Crée un fichier PowerPoint vide en mémoire.

#### Étape 2 : Accéder à la première diapositive  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **Explication :** Récupère la première diapositive créée automatiquement.

#### Étape 3 : Ajouter un diagramme circulaire à la diapositive  
L’objet `IChart` représente une forme de graphique sur une diapositive.  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **Paramètres :** Position (`x`, `y`) et taille (`width`, `height`).  
- **Objectif :** Place une forme de diagramme circulaire sur la diapositive.

### Charger le classeur depuis un fichier

**Vue d’ensemble :** Chargez le classeur Excel contenant les données pour le graphique.

#### Étape 1 : Définir le répertoire du document  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- Définissez‑le sur le dossier contenant `book1.xlsx`.

#### Étape 2 : Ouvrir le classeur  
La classe `Workbook` d’Aspose.Cells charge un fichier Excel en mémoire.  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **Objectif :** Lit le fichier Excel en mémoire.

### Enregistrer le classeur dans ByteArrayOutputStream

**Vue d’ensemble :** Convertir le classeur en tableau d’octets afin qu’Aspose.Slides puisse le consommer.

#### Étape 1 : Créer ByteArrayOutputStream  
`ByteArrayOutputStream` fournit un tampon en mémoire pour les données binaires.  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **Objectif :** Fournit un flux en mémoire pour le stockage temporaire.

#### Étape 2 : Enregistrer le classeur dans le flux  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **Explication :** Écrit le classeur sous forme de flux d’octets XLSX.

### Écrire les données du classeur dans le graphique

**Vue d’ensemble :** Alimenter le graphique avec le tableau d’octets Excel comme source de données.

#### Étape 1 : Alimenter le graphique avec les données  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **Objectif :** Lie le graphique aux données Excel.

### Définir la plage de données du graphique et configurer les séries

**Vue d’ensemble :** Définir quelles cellules le graphique doit lire et améliorer le style visuel.

#### Étape 1 : Définir la plage de données  
La méthode `setRange` définit les cellules Excel utilisées comme source de données du graphique.  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **Explication :** Pointe le graphique vers la plage exacte sur *Sheet2*.

#### Étape 2 : Configurer les propriétés des séries  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **Objectif :** Permet des couleurs variées pour chaque part du diagramme circulaire.

### Enregistrer la présentation dans un fichier

**Vue d’ensemble :** Enregistrer la présentation terminée sur le disque.

#### Étape 1 : Définir le chemin de sortie  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- Choisissez un dossier où vous souhaitez le fichier PowerPoint final.

#### Étape 2 : Enregistrer la présentation  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **Explication :** Écrit la présentation sous forme de fichier `.pptx`.

## Applications pratiques

1. **Rapports d’entreprise :** Transformez les feuilles de calcul de ventes mensuelles en diaporamas soignés avec une seule commande.  
2. **Outils éducatifs :** Affichez les répartitions statistiques pour les présentations en classe sans création manuelle de graphiques.  
3. **Intégration de tableau de bord :** Automatisez la génération de tableaux de bord basés sur des diapositives qui extraient des données en temps réel depuis des classeurs Excel.

## Considérations de performance

- **Gestion de la mémoire :** Encapsulez les flux dans un try‑with‑resources ou fermez‑les dans un bloc `finally` pour éviter les fuites.  
- **Jeux de données volumineux :** Traitez les données par morceaux ou utilisez `Workbook.getWorksheets().clear()` après avoir extrait les valeurs nécessaires.  
- **Chargement paresseux :** Chargez le classeur uniquement lorsque vous devez remplir le graphique, pas au démarrage de l’application.

## Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| **Le graphique n’affiche aucune donnée** | Vérifiez que la chaîne de plage correspond exactement au nom de la feuille et aux adresses des cellules (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | Utilisez `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` pour garantir que le flux soit libéré rapidement. |
| **Licence non appliquée** | Chargez la licence avant l’instanciation de toute classe Aspose : `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Slides sans licence ?**  
R : Oui, mais le mode d’évaluation ajoute des filigranes et limite certaines fonctionnalités. Pour la production, obtenez une licence temporaire ou complète.

**Q : Comment gérer de grandes présentations avec Aspose.Slides ?**  
R : Utilisez une gestion efficace des ressources, divisez la présentation en parties plus petites et libérez rapidement les objets inutilisés.

**Q : Quels formats de fichier Aspose.Slides peut‑il exporter ?**  
R : PPTX, PDF, XPS, ODP, HTML et les formats d’image tels que PNG, JPEG et BMP.

**Q : Est‑il possible de mettre à jour un fichier PowerPoint existant au lieu d’en créer un nouveau ?**  
R : Absolument. Chargez un fichier existant avec `new Presentation("existing.pptx")`, modifiez les diapositives/graphes, puis enregistrez.

**Q : La bibliothèque prend‑elle en charge la définition de couleurs personnalisées pour chaque part du diagramme circulaire ?**  
R : Oui – après avoir récupéré la série, vous pouvez définir `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` et attribuer une `Color`.

## Ressources
- **Documentation :** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Téléchargement :** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)
- **Acheter une licence :** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Essai gratuit :** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Licence temporaire :** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Dernière mise à jour :** 2026-06-13  
**Testé avec :** Aspose.Slides 25.4 pour Java (JDK 16) & Aspose.Cells 25.4  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment mettre à jour la plage de données d’un graphique PowerPoint en utilisant Aspose.Slides pour Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [Comment ajouter un diagramme circulaire PowerPoint avec Aspose.Slides pour Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Comment ajouter des graphiques à PowerPoint en utilisant Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
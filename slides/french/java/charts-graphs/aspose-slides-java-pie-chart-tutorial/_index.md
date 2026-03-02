---
date: '2026-03-02'
description: Apprenez à ajouter Excel à PowerPoint et à générer un PowerPoint à partir
  d'Excel en créant un graphique circulaire dynamique avec Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 'Ajouter Excel à PowerPoint : Présentation dynamique avec diagramme circulaire
  utilisant Aspose.Slides pour Java'
url: /fr/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ajouter Excel à PowerPoint : Présentation dynamique avec diagramme circulaire utilisant Aspose.Slides for Java

Dans l’environnement actuel axé sur les données, **add Excel to PowerPoint** rapidement et de façon fiable afin que votre audience puisse voir les chiffres sous forme visuelle. Ce tutoriel vous guide à travers la génération d’un PowerPoint à partir d’Excel, la création d’un diagramme circulaire avec Java, et la configuration de la plage de données du graphique — le tout avec Aspose.Slides for Java. À la fin, vous disposerez d’une présentation prête à l’emploi qui extrait les données en direct depuis un classeur Excel.

## Réponses rapides
- **Quelle bibliothèque crée des graphiques en Java ?** Aspose.Slides for Java.
- **Puis-je extraire directement les données Excel dans un graphique PowerPoint ?** Oui – utilisez Aspose.Cells pour lire le classeur et le fournir au graphique.
- **Quel type de graphique est démontré ?** Un diagramme circulaire.
- **Comment définir la plage de données du graphique ?** En appelant `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.
- **Quel est le principal avantage de cette approche ?** Elle automatise le flux « add Excel to PowerPoint », éliminant le copier‑coller manuel.

## Qu’est‑ce que **add Excel to PowerPoint** ?
Ajouter Excel à PowerPoint signifie importer programmétiquement des données de feuille de calcul et les visualiser à l’intérieur d’une présentation. Avec Aspose.Slides et Aspose.Cells, vous pouvez lire n’importe quel fichier Excel, mapper les cellules aux séries du graphique, et produire une présentation soignée sans jamais ouvrir PowerPoint manuellement.

## Pourquoi générer PowerPoint à partir d’Excel avec Aspose.Slides for Java ?
- **Vitesse :** Créez des rapports en secondes, pas en minutes.
- **Exactitude :** Les données sont lues directement depuis le classeur source, éliminant les erreurs de transcription.
- **Flexibilité :** Personnalisez les couleurs, les styles et les plages de données du graphique à la volée.
- **Évolutivité :** Intégrez-le dans des jobs batch, des services web ou des pipelines de reporting planifiés.

## Prérequis
- **Java Development Kit (JDK) 1.8+** installé.
- **Aspose.Slides for Java** et **Aspose.Cells for Java** libraries (Maven, Gradle, or direct JAR download).
- Un classeur Excel (`book1.xlsx`) contenant les données que vous souhaitez visualiser.
- Une licence Aspose valide (l’essai gratuit fonctionne pour l’évaluation).

### Bibliothèques requises
Vous aurez besoin d’Aspose.Slides et d’Aspose.Cells. Utilisez l’un de ces outils de gestion des dépendances :

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

Alternatively, download the JARs directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisition de licence
- **Essai gratuit :** Disponible sur la [page de téléchargement Aspose](https://releases.aspose.com/slides/java/).  
- **Licence temporaire :** Pour tester sans les limitations d’évaluation, demandez‑en une sur la [page de licence temporaire d’Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licence d’achat :** Pour utiliser les produits Aspose en production, achetez la licence complète.

## Configuration d’Aspose.Slides pour Java

Ajoutez la dépendance Aspose.Slides à votre projet (voir les extraits Maven/Gradle ci‑dessus) et placez les fichiers JAR sur votre classpath si vous n’utilisez pas d’outil de build.

### Initialisation et configuration de base
Importez la classe principale qui représente un fichier PowerPoint :

```java
import com.aspose.slides.Presentation;
```

## Guide d’implémentation

Ci‑dessous, un guide pas à pas qui couvre **create pie chart java**, **set chart data range**, et **add Excel to PowerPoint** dans un même flux.

### Créer et ajouter un graphique à la présentation

**Vue d’ensemble :** Initialise une nouvelle présentation, récupère la première diapositive, et insère un diagramme circulaire.

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
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **Paramètres :** Position (`x`, `y`) et taille (`width`, `height`).  
- **Objectif :** Place une forme de diagramme circulaire sur la diapositive.

### Charger le classeur depuis le fichier

**Vue d’ensemble :** Charge le classeur Excel qui contient les données pour le graphique.

#### Étape 1 : Définir le répertoire du document
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- Définissez-le sur le dossier contenant `book1.xlsx`.

#### Étape 2 : Ouvrir le classeur
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **Objectif :** Lit le fichier Excel en mémoire.

### Enregistrer le classeur dans ByteArrayOutputStream

**Vue d’ensemble :** Convertit le classeur en tableau d’octets afin qu’Aspose.Slides puisse le consommer.

#### Étape 1 : Créer ByteArrayOutputStream
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

**Vue d’ensemble :** Alimente le diagramme circulaire avec le tableau d’octets Excel comme source de données.

#### Étape 1 : Alimenter les données dans le graphique
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **Objectif :** Lie le graphique aux données Excel.

### Définir la plage de données du graphique et configurer les séries

**Vue d’ensemble :** Spécifie quelles cellules le graphique doit lire et améliore le style visuel.

#### Étape 1 : Définir la plage de données
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

**Vue d’ensemble :** Persiste la présentation terminée sur le disque.

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

1. **Reporting d’entreprise :** Transformez les feuilles de calcul de ventes mensuelles en présentations soignées avec une seule commande.  
2. **Outils éducatifs :** Affichez les répartitions statistiques pour les présentations en classe sans création manuelle de graphiques.  
3. **Intégration de tableau de bord :** Automatisez la génération de tableaux de bord basés sur des diapositives qui extraient les données en direct depuis les classeurs Excel.

## Considérations de performance

- **Gestion de la mémoire :** Enveloppez les flux dans try‑with‑resources ou fermez‑les dans un bloc `finally` pour éviter les fuites.  
- **Jeux de données volumineux :** Traitez les données par morceaux ou utilisez `Workbook.getWorksheets().clear()` après avoir extrait les valeurs nécessaires.  
- **Chargement paresseux :** Chargez le classeur uniquement lorsque vous devez remplir le graphique, pas au démarrage de l’application.

## Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| **Chart shows no data** | Verify the range string matches the sheet name and cell addresses exactly (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | Use `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` to ensure the stream is released promptly. |
| **License not applied** | Load the license before any Aspose class is instantiated: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Foire aux questions

**Q : Puis‑je utiliser Aspose.Slides sans licence ?**  
R : Oui, mais le mode d’évaluation ajoute des filigranes et limite certaines fonctionnalités. Pour la production, obtenez une licence temporaire ou complète.

**Q : Comment gérer de grandes présentations avec Aspose.Slides ?**  
R : Utilisez une gestion efficace des ressources, divisez la présentation en parties plus petites, et libérez rapidement les objets inutilisés.

**Q : Quels formats de fichier Aspose.Slides peut‑il exporter ?**  
R : PPTX, PDF, XPS, ODP, HTML, et des formats d’image tels que PNG, JPEG et BMP.

**Q : Est‑il possible de mettre à jour un fichier PowerPoint existant au lieu d’en créer un nouveau ?**  
R : Absolument. Chargez un fichier existant avec `new Presentation("existing.pptx")`, modifiez les diapositives/graphes, puis enregistrez.

**Q : La bibliothèque prend‑elle en charge la définition de couleurs personnalisées pour chaque part du diagramme circulaire ?**  
R : Oui – après avoir récupéré la série, vous pouvez définir `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` et assigner une `Color`.

## Ressources
- **Documentation :** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Téléchargement :** [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)
- **Licence d’achat :** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Essai gratuit :** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Licence temporaire :** [Get a Temporary License](https://purchase.aspose.com/temporary-license)

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
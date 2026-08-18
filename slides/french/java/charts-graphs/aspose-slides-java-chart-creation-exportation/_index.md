---
date: '2026-06-03'
description: Apprenez comment exporter un graphique vers Excel et créer des graphiques
  Java en utilisant Aspose.Slides for Java. Maîtrisez la visualisation des données,
  les diapositives de rapports d'entreprise et la génération de classeurs.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Exporter le graphique vers Excel et créer des graphiques avec Aspose.Slides
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exporter le graphique vers Excel et créer des graphiques avec Aspose.Slides

**Maîtrisez les techniques de visualisation de données avec Aspose.Slides for Java**

Dans le paysage actuel axé sur les données, *export chart to excel* programmé est une compétence qui peut transformer des chiffres bruts en histoires visuelles convaincantes. Que vous créiez un diaporama de rapport d'entreprise ou un tableau de bord analytique interactif, Aspose.Slides for Java vous donne le pouvoir de générer, personnaliser et exporter des graphiques directement depuis votre code. Dans ce tutoriel, vous apprendrez comment créer des objets de graphique, exporter les données du graphique vers Excel, et lier les graphiques à des classeurs externes pour une gestion fluide des données.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Slides for Java (v25.4+).  
- **Puis-je exporter les données du graphique vers Excel ?** Yes – use `readWorkbookStream()` and write the bytes to an *.xlsx* file.  
- **Quelle version de Java est requise ?** JDK 16 or higher.  
- **Ai-je besoin d'une licence ?** A free trial works for evaluation; a permanent license is required for production.  
- **Quel type de graphique est démontré ?** A Pie chart, but the same approach works for Bar, Line, and other chart types.

## Qu'est-ce qu'Aspose.Slides for Java ?
Aspose.Slides for Java est une API pure‑Java qui permet aux développeurs de créer, modifier et convertir des présentations PowerPoint sans Microsoft Office. Elle fournit un ensemble complet de classes pour la manipulation des diapositives, la génération de graphiques et la conversion de formats, permettant des solutions de reporting automatisées. Elle prend en charge **plus de 50 types de graphiques**, la liaison complète des données et l'exportation directe vers Excel, ce qui la rend idéale pour les projets de **visualisation de données java**.

## Pourquoi utiliser Aspose.Slides pour créer un graphique et exporter le graphique vers Excel ?
Exporter le graphique vers Excel rapidement et de manière fiable. Aspose.Slides élimine le besoin d'installations Office, offre **plus de 50 styles de graphiques intégrés**, et traite les présentations **jusqu'à 300 Mo en moins de 30 secondes** sur du matériel serveur standard. Vous bénéficiez également de la génération native de classeurs Excel, ce qui permet aux analystes en aval de travailler avec les chiffres bruts sans copier‑coller manuellement.

## Prérequis
Avant de commencer, assurez-vous d'avoir les éléments suivants :

### Bibliothèques requises et versions
- **Aspose.Slides for Java** version 25.4 ou ultérieure (prend en charge JDK 16+)

### Exigences de configuration de l'environnement
- Kit de développement Java (JDK) 16 ou supérieur  
- Un IDE tel qu'IntelliJ IDEA ou Eclipse (ou tout éditeur de texte de votre choix)

### Prérequis de connaissances
- Compétences de base en programmation Java  
- Familiarité avec les outils de construction Maven ou Gradle

## Configuration d'Aspose.Slides for Java
Ajoutez la bibliothèque à votre projet en utilisant votre système de construction préféré.

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

Alternativement, vous pouvez [télécharger la dernière version directement](https://releases.aspose.com/slides/java/).

### Étapes d'obtention de licence
Aspose.Slides propose une licence d'essai gratuite pour explorer toutes ses capacités. Vous pouvez également demander une licence temporaire ou en acheter une pour une utilisation prolongée. Suivez ces étapes :

1. Visitez la [page d'achat Aspose](https://purchase.aspose.com/buy) pour obtenir votre licence.  
2. Pour un essai gratuit, téléchargez depuis [Releases](https://releases.aspose.com/slides/java/).  
3. Demandez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

Une fois que vous avez le fichier de licence, initialisez-le dans votre application Java :

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guide étape par étape

### Comment créer un graphique – Charger une présentation
Chargez un fichier PowerPoint existant avant de pouvoir ajouter ou modifier des graphiques.  
La classe `Presentation` représente un fichier PowerPoint en mémoire, exposant les diapositives, les formes et les objets de graphique.  
Chargez votre fichier avec `new Presentation("input.pptx")`, puis travaillez avec la première diapositive en utilisant `presentation.getSlides().get_Item(0)`. Appelez toujours `presentation.dispose()` dans un bloc `finally` pour libérer les ressources natives.

### Comment créer un graphique – Ajouter un graphique circulaire à une diapositive
Inserrez un graphique circulaire, idéal pour afficher des données proportionnelles.  
L'interface `IChart` est le point d'entrée principal pour la manipulation des graphiques ; `addChart` crée un nouveau graphique sur la diapositive cible. Fournissez le type de graphique (`ChartType.Pie`), les coordonnées X/Y, et la largeur/hauteur. Après la création, vous pouvez personnaliser les titres, la légende et les séries de données via l'objet `ChartData`.

### Comment exporter le graphique vers Excel – Exporter les données du graphique
L'exportation des données du graphique permet aux analystes de travailler avec les chiffres dans Excel, offrant des analyses plus approfondies.  
`readWorkbookStream()` renvoie le classeur Excel sous-jacent du graphique sous forme de tableau d'octets. Appelez `chart.getChartData().readWorkbookStream()` pour récupérer le classeur et écrivez ce tableau dans un fichier nommé `externalWorkbook1.xlsx` en utilisant les I/O Java standard. Le fichier Excel résultant contient les données exactes utilisées par le graphique, prêtes pour une analyse supplémentaire.

### Comment créer un graphique – Définir un classeur externe pour des données dynamiques
Liez un graphique à un classeur externe pour permettre des mises à jour de données en temps réel sans reconstruire la diapositive.  
`setExternalWorkbook()` lie le graphique à un fichier Excel externe pour des mises à jour de données dynamiques. Utilisez `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` pour lier le graphique au fichier externe. Lorsque le classeur Excel est modifié, le graphique reflète automatiquement les changements lors de la prochaine ouverture de la présentation, supportant les scénarios de reporting dynamique.

## Applications pratiques
Aspose.Slides propose des solutions polyvalentes pour divers scénarios réels :

1. **Diapositives de rapports d'entreprise :** Générez automatiquement des graphiques de performance trimestriels à partir de vos pipelines de données.  
2. **Présentations académiques :** Transformez les données de recherche en visualisations claires sans création manuelle de graphiques.  
3. **Analyse financière :** Exportez les données du graphique vers Excel pour que les auditeurs vérifient les chiffres, réduisant les erreurs manuelles.  
4. **Analyse marketing :** Visualisez les métriques de campagne et partagez des classeurs éditables avec les parties prenantes pour une prise de décision collaborative.  
5. **Génération automatisée de tableaux de bord :** Combinez l'API de création de graphiques avec des tâches planifiées pour produire chaque matin des diaporamas à jour.

## Problèmes courants et dépannage
- **`FileNotFoundException`** – Vérifiez que `dataDir` pointe vers un dossier valide et que le chemin de sortie est accessible en écriture.  
- **Fuites de mémoire** – Appelez toujours `presentation.dispose()` dans un bloc `finally` pour libérer les ressources natives.  
- **Le graphique n'apparaît pas** – Assurez-vous que l'index de diapositive (`get_Item(0)`) correspond à une diapositive existante, et que les dimensions du graphique sont à l'intérieur des limites de la diapositive.  
- **L'exportation Excel produit un fichier vide** – Confirmez que le graphique contient réellement des séries de données avant d'appeler `readWorkbookStream()`.

## Questions fréquentes

**Q : Puis-je utiliser un autre type de graphique (par ex., Bar, Line) avec le même code ?**  
R : Oui. Remplacez `ChartType.Pie` par toute autre valeur d'énumération `ChartType` telle que `ChartType.Bar` ou `ChartType.Line`.

**Q : Est-il possible de mettre à jour le classeur externe après la création du graphique ?**  
R : Absolument. Modifiez directement le fichier Excel ; le graphique lié reflétera les changements lors de la prochaine ouverture de la présentation.

**Q : Ai-je besoin d'une licence séparée pour la fonction d'exportation Excel ?**  
R : Non. La capacité d'exportation Excel est incluse dans la licence standard d'Aspose.Slides for Java.

**Q : Quelles versions de Java sont prises en charge ?**  
R : Aspose.Slides for Java prend en charge JDK 16 et les versions ultérieures ; les versions antérieures peuvent fonctionner mais ne sont pas officiellement testées.

**Q : Comment puis-je intégrer le classeur Excel généré dans le fichier PPTX ?**  
R : Utilisez `chart.getChartData().setExternalWorkbook(null)` pour intégrer le classeur, ou conservez le lien externe pour des mises à jour dynamiques.

---

**Dernière mise à jour :** 2026-06-03  
**Testé avec :** Aspose.Slides for Java 25.4 (classificateur JDK 16)  
**Auteur :** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer un graphique en Java avec Aspose.Slides – Ajouter et valider les graphiques](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Récupérer les données du classeur à partir des graphiques PowerPoint avec Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Comment mettre à jour la plage de données d'un graphique PowerPoint en utilisant Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
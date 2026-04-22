---
date: '2026-02-09'
description: Apprenez à créer des graphiques et à exporter des graphiques vers Excel
  en utilisant Aspose.Slides pour Java. Maîtrisez la visualisation des données, les
  diapositives de rapports d'entreprise et la génération de classeurs.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Comment créer un graphique avec Aspose.Slides Java
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique avec Aspose.Slides for Java

**Maîtrisez les techniques de visualisation de données avec Aspose.Slides for Java**

Dans le paysage actuel axé sur les données, *comment créer un graphique* de manière programmatique est une compétence qui peut transformer des chiffres bruts en histoires visuelles convaincantes. Que vous construisiez un diaporama de rapport d'entreprise ou un tableau de bord analytique interactif, Aspose.Slides for Java vous donne le pouvoir de générer, personnaliser et exporter des graphiques directement depuis votre code. Dans ce tutoriel, vous apprendrez à créer des objets graphiques, à exporter les données du graphique vers Excel, et à lier les graphiques à des classeurs externes pour une gestion fluide des données.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Slides for Java (v25.4+).  
- **Puis-je exporter les données du graphique vers Excel ?** Oui – utilisez `readWorkbookStream()` et écrivez les octets dans un fichier *.xlsx*.  
- **Quelle version de Java est requise ?** JDK 16 ou supérieur.  
- **Ai‑je besoin d'une licence ?** Un essai gratuit suffit pour l'évaluation ; une licence permanente est requise pour la production.  
- **Quel type de graphique est démontré ?** Un graphique en secteurs, mais la même approche fonctionne pour les graphiques à barres, en lignes et autres types.

## Qu'est‑ce qu'Aspose.Slides for Java ?
Aspose.Slides for Java est une API pure‑Java qui permet aux développeurs de créer, modifier et convertir des présentations PowerPoint sans Microsoft Office. Elle prend en charge une gamme complète de types de graphiques, la liaison de données et les capacités d'exportation, ce qui la rend idéale pour les projets **data visualization java**.

## Pourquoi utiliser Aspose.Slides pour créer un graphique et l'exporter vers Excel ?
- **Pas d'installation d'Office** – fonctionne sur n'importe quel serveur ou environnement cloud.  
- **Bibliothèque de graphiques riche** – des dizaines de types de graphiques et un contrôle complet du style.  
- **Exportation directe vers Excel** – génère un classeur externe pour l'analyse en aval.  
- **Orienté performance** – faible empreinte mémoire et traitement rapide pour de grands jeux de diapositives.

## Prérequis
Avant de commencer, assurez‑vous d'avoir les éléments suivants :

### Bibliothèques requises et versions
- **Aspose.Slides for Java** version 25.4 ou ultérieure

### Exigences de configuration de l'environnement
- Java Development Kit (JDK) 16 ou supérieur  
- Un IDE tel qu'IntelliJ IDEA ou Eclipse (ou tout éditeur de texte de votre choix)

### Prérequis de connaissances
- Compétences de base en programmation Java  
- Familiarité avec les outils de construction Maven ou Gradle

## Configuration d'Aspose.Slides pour Java
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

Une fois que vous avez le fichier de licence, initialisez‑le dans votre application Java :

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guide étape par étape

### Comment créer un graphique – Charger une présentation
Charger un fichier PowerPoint existant est la première étape avant de pouvoir ajouter ou modifier des graphiques.

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

**Explication :**  
- `Presentation` représente le fichier PowerPoint.  
- Appelez toujours `dispose()` pour libérer les ressources natives.

### Comment créer un graphique – Ajouter un graphique en secteurs à une diapositive
Nous allons maintenant insérer un graphique en secteurs, idéal pour afficher des données proportionnelles.

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

**Explication :**  
- `addChart` insère le graphique sur la première diapositive.  
- Les paramètres définissent le type de graphique, la position X/Y et la taille.

### Comment exporter le graphique vers Excel – Exporter les données du graphique
L'exportation des données du graphique permet aux analystes de travailler avec les nombres dans Excel, offrant des analyses plus approfondies.

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

**Explication :**  
- `readWorkbookStream()` extrait le classeur Excel sous‑jacent du graphique sous forme de tableau d'octets.  
- Le tableau d'octets est écrit dans `externalWorkbook1.xlsx`, vous fournissant un fichier Excel prêt à l'emploi.

### Comment créer un graphique – Définir un classeur externe pour des données dynamiques
Lier un graphique à un classeur externe vous permet de mettre à jour le graphique simplement en modifiant le fichier Excel.

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

**Explication :**  
- `setExternalWorkbook` lie le graphique au fichier Excel spécifié, permettant des mises à jour de données en direct sans reconstruire la diapositive.

## Applications pratiques
Aspose.Slides propose des solutions polyvalentes pour divers scénarios réels :

1. **Diapositives de rapports d'entreprise :** Générez automatiquement des graphiques de performance trimestrielle à partir de vos pipelines de données.  
2. **Présentations académiques :** Transformez les données de recherche en visualisations claires sans création manuelle de graphiques.  
3. **Analyse financière :** Exportez les données du graphique vers Excel pour que les auditeurs vérifient les chiffres.  
4. **Analyse marketing :** Visualisez les métriques de campagne et partagez des classeurs modifiables avec les parties prenantes.

## Problèmes courants & dépannage
- **`FileNotFoundException`** – Vérifiez que `dataDir` pointe vers un dossier valide et que le chemin de sortie est accessible en écriture.  
- **Fuites de mémoire** – Appelez toujours `pres.dispose()` dans un bloc `finally` pour libérer les ressources natives.  
- **Graphique absent** – Assurez‑vous que l'index de diapositive (`get_Item(0)`) correspond à une diapositive qui existe réellement.

## Questions fréquemment posées

**Q : Puis‑je utiliser un type de graphique différent (p. ex., Bar, Line) avec le même code ?**  
R : Oui. Remplacez `ChartType.Pie` par n'importe quelle autre valeur d'énumération `ChartType` telle que `ChartType.Bar` ou `ChartType.Line`.

**Q : Est‑il possible de mettre à jour le classeur externe après la création du graphique ?**  
R : Absolument. Modifiez directement le fichier Excel ; le graphique lié reflétera les modifications lors de la prochaine ouverture de la présentation.

**Q : Ai‑je besoin d'une licence séparée pour la fonction d'exportation vers Excel ?**  
R : Non. La capacité d'exportation vers Excel est incluse dans la licence standard d'Aspose.Slides for Java.

**Q : Quelles versions de Java sont prises en charge ?**  
R : Aspose.Slides for Java prend en charge JDK 16 et les versions ultérieures ; les versions antérieures peuvent fonctionner mais ne sont pas officiellement testées.

**Q : Comment puis‑je intégrer le classeur Excel généré dans le fichier PPTX ?**  
R : Utilisez `chart.getChartData().setExternalWorkbook(null)` pour intégrer le classeur, ou conservez le lien externe pour des mises à jour dynamiques.

---

**Dernière mise à jour :** 2026-02-09  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
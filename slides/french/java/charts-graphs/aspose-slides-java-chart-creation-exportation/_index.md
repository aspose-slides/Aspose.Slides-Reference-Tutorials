---
date: '2026-01-14'
description: Apprenez à exporter un graphique vers Excel en utilisant Aspose.Slides
  pour Java et à ajouter une diapositive de graphique circulaire aux présentations.
  Guide étape par étape avec le code.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Exporter le graphique vers Excel avec Aspose.Slides Java
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exporter un graphique vers Excel avec Aspose.Slides pour Java

**Maîtrisez les techniques de visualisation de données avec Aspose.Slides pour Java**

Dans le paysage actuel axé sur les données, pouvoir **exporter un graphique vers Excel** directement depuis votre application Java peut transformer des visuels PowerPoint statiques en ensembles de données réutilisables et analysables. Que vous ayez besoin de générer des rapports, d’alimenter des pipelines d’analyse, ou simplement de permettre aux utilisateurs métier de modifier les données du graphique dans Excel, Aspose.Slides rend cela simple. Ce tutoriel vous guide à travers la création d’un graphique, l’ajout d’une diapositive de graphique en secteurs, et l’exportation des données du graphique vers un classeur Excel.

**Ce que vous apprendrez :**
- Charger et manipuler des fichiers de présentation sans effort
- **Ajouter une diapositive de graphique en secteurs** et d’autres types de graphiques à vos diapositives
- **Exporter le graphique vers Excel** (générer un fichier Excel à partir du graphique) pour l’analyse en aval
- Définir le chemin d’un classeur externe pour **intégrer le graphique dans la présentation** et garder les données synchronisées

## Réponses rapides
- **Quel est le but principal ?** Exporter les données du graphique d’une diapositive PowerPoint vers un fichier Excel.  
- **Quelle version de la bibliothèque est requise ?** Aspose.Slides for Java 25.4 ou ultérieure.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Puis‑je ajouter une diapositive de graphique en secteurs ?** Oui – le tutoriel montre comment ajouter un graphique en secteurs.  
- **Java 16 est‑il le minimum ?** Oui, JDK 16 ou supérieur est recommandé.

## Comment exporter un graphique vers Excel avec Aspose.Slides ?
Exporter les données du graphique vers Excel est aussi simple que de charger une présentation, créer un graphique, puis écrire le flux du classeur du graphique dans un fichier. Les étapes ci‑dessous vous guident à travers le processus complet, de la configuration du projet à la vérification finale.

## Prérequis
Avant de commencer, assurez‑vous d’avoir les éléments suivants prêts :

### Bibliothèques requises et versions
- **Aspose.Slides for Java** version 25.4 ou ultérieure

### Exigences de configuration de l’environnement
- Java Development Kit (JDK) 16 ou supérieur
- Un éditeur de code ou un IDE tel qu’IntelliJ IDEA ou Eclipse

### Prérequis en connaissances
- Compétences de base en programmation Java
- Familiarité avec les systèmes de construction Maven ou Gradle

## Configuration d’Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides, incluez‑le dans votre projet avec Maven ou Gradle.

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

Vous pouvez également [télécharger la dernière version directement](https://releases.aspose.com/slides/java/).

### Étapes d’obtention de licence
Aspose.Slides propose une licence d’essai gratuite pour explorer toutes ses capacités. Vous pouvez également demander une licence temporaire ou en acheter une pour une utilisation prolongée. Suivez ces étapes :
1. Visitez la [page d’achat d’Aspose](https://purchase.aspose.com/buy) pour obtenir votre licence.  
2. Pour un essai gratuit, téléchargez depuis [Releases](https://releases.aspose.com/slides/java/).  
3. Demandez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

Une fois que vous avez le fichier de licence, initialisez‑le dans votre application Java :
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guide d’implémentation

### Fonctionnalité 1 : Charger la présentation
Charger une présentation est la première étape de toute tâche de manipulation.

#### Vue d’ensemble
Cette fonctionnalité montre comment charger un fichier PowerPoint existant avec Aspose.Slides for Java.

#### Implémentation étape par étape
**Charger la présentation**
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
- `Presentation` est initialisé avec le chemin de votre fichier `.pptx`.  
- Toujours libérer l’objet `Presentation` pour libérer les ressources natives.

### Fonctionnalité 2 : Ajouter une diapositive de graphique en secteurs
Ajouter un graphique peut améliorer considérablement la présentation des données, et de nombreux développeurs se demandent **comment ajouter une diapositive de graphique** en Java.

#### Vue d’ensemble
Cette fonctionnalité montre comment ajouter une **diapositive de graphique en secteurs** (le scénario classique « ajouter une diapositive de graphique en secteurs ») à la première diapositive d’une présentation.

#### Implémentation étape par étape
**Ajouter un graphique en secteurs**
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
- `addChart` insère un graphique en secteurs.  
- Les paramètres définissent le type de graphique ainsi que sa position/taille sur la diapositive.

### Fonctionnalité 3 : Générer un Excel à partir du graphique
Exporter les données du graphique vous permet de **générer un Excel à partir du graphique** pour une analyse plus approfondie.

#### Vue d’ensemble
Cette fonctionnalité montre comment exporter les données du graphique d’une présentation vers un classeur Excel externe.

#### Implémentation étape par étape
**Exporter les données**
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
- `readWorkbookStream` extrait les données du classeur du graphique.  
- Le tableau d’octets est écrit dans un fichier `.xlsx` à l’aide de `FileOutputStream`.

### Fonctionnalité 4 : Intégrer le graphique dans la présentation avec un classeur externe
Lier un graphique à un classeur externe vous permet de **intégrer le graphique dans la présentation** et de garder les données synchronisées.

#### Vue d’ensemble
Cette fonctionnalité montre comment définir le chemin d’un classeur externe afin que le graphique puisse lire/écrire directement depuis Excel.

#### Implémentation étape par étape
**Définir le chemin du classeur externe**
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
- `setExternalWorkbook` lie le graphique à un fichier Excel, permettant des mises à jour dynamiques sans reconstruire la diapositive.

## Applications pratiques
Aspose.Slides offre des solutions polyvalentes pour divers scénarios :

1. **Rapports d’entreprise :** Créez des rapports détaillés avec des graphiques directement depuis des applications Java.  
2. **Présentations académiques :** Améliorez les cours avec des diapositives de graphiques en secteurs interactifs.  
3. **Analyse financière :** **Exporter le graphique vers Excel** pour une modélisation financière approfondie.  
4. **Analyse marketing :** Visualisez les performances de campagne et **générez un Excel à partir du graphique** pour l’équipe d’analyse.

## Foire aux questions

**Q : Puis‑je utiliser cette approche avec d’autres types de graphiques (p. ex., Bar, Line) ?**  
R : Absolument. Remplacez `ChartType.Pie` par n’importe quelle autre valeur de l’énumération `ChartType`.

**Q : Ai‑je besoin d’une bibliothèque Excel séparée pour lire le fichier exporté ?**  
R : Non. Le fichier `.xlsx` exporté est un classeur Excel standard qui peut être ouvert avec n’importe quelle application de tableur.

**Q : Comment le classeur externe affecte‑t‑il la taille de la diapositive ?**  
R : Le lien vers un classeur externe n’augmente pas de manière significative la taille du fichier PPTX ; le graphique référence le classeur à l’exécution.

**Q : Est‑il possible de mettre à jour les données Excel et que la diapositive reflète les changements automatiquement ?**  
R : Oui. Après avoir appelé `setExternalWorkbook`, toute modification enregistrée dans le classeur sera reflétée lors de la prochaine ouverture de la présentation.

**Q : Que faire si je dois exporter plusieurs graphiques de la même présentation ?**  
R : Parcourez la collection de graphiques de chaque diapositive, appelez `readWorkbookStream()` pour chacun, et écrivez dans des fichiers de classeur distincts.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
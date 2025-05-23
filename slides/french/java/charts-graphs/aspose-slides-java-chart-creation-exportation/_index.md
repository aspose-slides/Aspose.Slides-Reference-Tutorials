---
"date": "2025-04-17"
"description": "Apprenez à créer et exporter des graphiques avec Aspose.Slides en Java. Maîtrisez les techniques de visualisation de données grâce à des guides étape par étape et des exemples de code."
"title": "Aspose.Slides Java &#58; Création et exportation de graphiques pour la visualisation des données"
"url": "/fr/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Création et exportation de graphiques à l'aide d'Aspose.Slides Java

**Maîtriser les techniques de visualisation des données avec Aspose.Slides pour Java**

Dans le contexte actuel axé sur les données, une visualisation efficace des données est essentielle pour prendre des décisions éclairées. L'intégration de fonctionnalités graphiques à vos applications Java peut transformer les données brutes en histoires visuelles captivantes. Ce tutoriel vous guidera dans la création et l'exportation de graphiques avec Aspose.Slides pour Java, garantissant ainsi des présentations à la fois informatives et visuellement attrayantes.

**Ce que vous apprendrez :**
- Chargez et manipulez des fichiers de présentation sans effort
- Ajoutez différents types de graphiques à vos diapositives
- Exportez les données des graphiques vers des classeurs externes en toute transparence
- Définir un chemin de classeur externe pour une gestion efficace des données

C'est parti !

## Prérequis
Avant de commencer, assurez-vous d’avoir la configuration suivante prête :

### Bibliothèques et versions requises
- **Aspose.Slides pour Java** version 25.4 ou ultérieure

### Configuration requise pour l'environnement
- Kit de développement Java (JDK) 16 ou supérieur
- Un éditeur de code ou IDE comme IntelliJ IDEA ou Eclipse

### Prérequis en matière de connaissances
- Compréhension de base de la programmation Java
- Familiarité avec les systèmes de construction Maven ou Gradle

## Configuration d'Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides, vous devez l'inclure dans votre projet. Voici comment :

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

Alternativement, vous pouvez [télécharger directement la dernière version](https://releases.aspose.com/slides/java/).

### Étapes d'acquisition de licence
Aspose.Slides propose une licence d'essai gratuite pour explorer toutes ses fonctionnalités. Vous pouvez également demander une licence temporaire ou en acheter une pour une utilisation prolongée. Suivez ces étapes :
1. Visitez le [Page d'achat d'Aspose](https://purchase.aspose.com/buy) pour obtenir votre permis.
2. Pour un essai gratuit, téléchargez à partir de [Communiqués](https://releases.aspose.com/slides/java/).
3. Demander un permis temporaire [ici](https://purchase.aspose.com/temporary-license/).

Une fois que vous avez le fichier de licence, initialisez-le dans votre application Java :
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guide de mise en œuvre
### Fonctionnalité 1 : Présentation de la charge
Le chargement d’une présentation est la première étape de toute tâche de manipulation.

#### Aperçu
Cette fonctionnalité montre comment charger un fichier PowerPoint existant à l’aide d’Aspose.Slides pour Java.

#### Mise en œuvre étape par étape
**Ajouter un graphique à la diapositive**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Définissez le chemin d'accès à votre répertoire de documents
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Charger une présentation existante
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Nettoyer les ressources
        if (pres != null) pres.dispose();
    }
}
```
**Explication:**
- `Presentation` est initialisé avec le chemin vers votre `.pptx` déposer.
- Jetez toujours le `Presentation` s'opposer aux ressources gratuites.

### Fonctionnalité 2 : Ajouter un graphique à la diapositive
L’ajout d’un graphique peut considérablement améliorer la présentation des données.

#### Aperçu
Cette fonctionnalité montre comment ajouter un graphique à secteurs à la première diapositive d’une présentation.

#### Mise en œuvre étape par étape
**Ajouter un graphique à la diapositive**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Définissez le chemin d'accès à votre répertoire de documents
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Ajouter un graphique à secteurs à la position (50, 50) avec une largeur de 400 et une hauteur de 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explication:**
- `addChart` la méthode est utilisée pour insérer un graphique à secteurs.
- Les paramètres incluent le type de graphique et sa position/taille sur la diapositive.

### Fonctionnalité 3 : Exporter les données du graphique vers un classeur externe
L'exportation des données permet une analyse plus approfondie en dehors de PowerPoint.

#### Aperçu
Cette fonctionnalité illustre l’exportation de données de graphique à partir d’une présentation vers un classeur Excel externe.

#### Mise en œuvre étape par étape
**Exporter des données**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Définissez le chemin d'accès à votre répertoire de documents et à votre répertoire de sortie
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Accéder au graphique de la première diapositive
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Définir le chemin d'accès au classeur externe
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Exporter les données du graphique vers un flux Excel
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
**Explication:**
- `readWorkbookStream` extrait les données du graphique.
- Les données sont écrites dans un fichier Excel à l'aide de `FileOutputStream`.

### Fonctionnalité 4 : Définir un classeur externe pour les données du graphique
Lier des graphiques à des classeurs externes peut rationaliser la gestion des données.

#### Aperçu
Cette fonctionnalité illustre la définition d’un chemin de classeur externe pour stocker les données du graphique.

#### Mise en œuvre étape par étape
**Définir le chemin du classeur externe**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Définissez le chemin d'accès à votre répertoire de documents
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Accéder au graphique de la première diapositive
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Définir et définir le chemin d'accès au classeur externe
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explication:**
- `setExternalWorkbook` relie le graphique à un fichier Excel, permettant des mises à jour dynamiques des données.

## Applications pratiques
Aspose.Slides propose des solutions polyvalentes pour différents scénarios :

1. **Rapports d'activité :** Créez des rapports détaillés avec des graphiques directement à partir d'applications Java.
2. **Présentations académiques :** Améliorez le contenu éducatif avec des graphiques interactifs.
3. **Analyse financière :** Exportez les données financières vers Excel pour une analyse approfondie.
4. **Analyse marketing :** Visualisez les performances de la campagne à l’aide de graphiques dynamiques.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
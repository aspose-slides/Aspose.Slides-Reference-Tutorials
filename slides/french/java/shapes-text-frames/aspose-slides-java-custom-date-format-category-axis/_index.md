---
"date": "2025-04-17"
"description": "Apprenez à personnaliser les formats de date des axes de catégories avec Aspose.Slides pour Java. Améliorez vos graphiques avec une présentation de données personnalisée, idéale pour les rapports annuels et plus encore."
"title": "Comment définir un format de date personnalisé sur l'axe des catégories dans Aspose.Slides Java | Guide de visualisation des données"
"url": "/fr/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment définir un format de date personnalisé sur l'axe des catégories dans Aspose.Slides Java | Guide de visualisation des données

Dans un monde où les données sont omniprésentes, présenter clairement les informations est crucial pour une prise de décision efficace. Lors de la création de graphiques avec Aspose.Slides pour Java, personnaliser le format de date sur l'axe des abscisses peut améliorer considérablement la compréhension et la qualité de la présentation. Ce guide vous explique comment configurer un format de date personnalisé dans Aspose.Slides pour améliorer l'attrait visuel de vos diapositives et la clarté des données.

**Ce que vous apprendrez :**
- Configuration d'Aspose.Slides pour Java
- Implémentation de formats de date personnalisés sur l'axe des catégories
- Conversion des dates du calendrier grégorien au format de date OLE Automation
- Applications pratiques de ces fonctionnalités dans des scénarios réels

Plongeons dans la manière dont vous pouvez y parvenir facilement !

## Prérequis

Avant de commencer, assurez-vous d’avoir couvert les prérequis suivants :

### Bibliothèques et versions requises :
- **Aspose.Slides pour Java**:Vous aurez besoin de la version 25.4 ou ultérieure.

### Configuration requise pour l'environnement :
- Un environnement de développement capable d’exécuter du code Java (tel que IntelliJ IDEA, Eclipse ou NetBeans).
- Maven ou Gradle configuré dans votre projet pour gérer les dépendances.

### Prérequis en matière de connaissances :
- Compréhension de base de la programmation Java.
- Connaissance de l’utilisation des composants graphiques dans les présentations.

## Configuration d'Aspose.Slides pour Java

Pour utiliser Aspose.Slides pour Java, incluez-le comme dépendance dans votre projet. Voici les instructions d'installation :

**Expert :**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle :**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativement, vous pouvez [télécharger la dernière version](https://releases.aspose.com/slides/java/) directement depuis le site officiel d'Aspose.

### Acquisition de licence :
- **Essai gratuit**: Commencez par un essai gratuit pour explorer les fonctionnalités.
- **Permis temporaire**:Demandez une licence temporaire pour des tests prolongés.
- **Achat**: Pour une utilisation à long terme, pensez à souscrire un abonnement. Visitez [Achat Aspose](https://purchase.aspose.com/buy) pour plus de détails.

### Initialisation de base :

Voici comment vous pouvez initialiser Aspose.Slides dans votre projet :
```java
import com.aspose.slides.Presentation;
// Instancier un objet Presentation qui représente un fichier de présentation
Presentation pres = new Presentation();
```

Passons maintenant au cœur de ce guide !

## Guide de mise en œuvre

### Définition du format de date pour l'axe des catégories

Cette fonctionnalité vous permet de personnaliser l'affichage des dates sur l'axe des catégories de votre graphique. Vous trouverez ci-dessous un guide détaillé :

#### 1. Créer une nouvelle présentation et un nouveau graphique
Commencez par créer une instance de `Presentation` et en ajoutant un nouveau graphique en aires.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // Initialiser la présentation
        Presentation pres = new Presentation();
        
        try {
            // Ajoutez un graphique en aires à la première diapositive à la position et à la taille spécifiées
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // Classeur de données de graphique d'accès pour manipuler les données de graphique
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // Effacer toutes les données existantes dans le graphique

            // Supprimer toutes les catégories et séries préexistantes
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // Ajouter des dates à l'axe des catégories à l'aide de dates OLE Automation converties
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // Créez une nouvelle série et ajoutez-y des points de données
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // Définissez le type d'axe de catégorie sur Date et configurez son format numérique
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // Formater les dates en année uniquement

            // Enregistrer la présentation dans un répertoire spécifié
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Date de base pour la conversion OLE Automation
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // Convertir en date d'automatisation OLE
        return String.valueOf(oaDate);
    }
}
```

#### 2. Conversion des dates du calendrier grégorien au format de date OLE Automation

Aspose.Slides requiert des dates au format OLE Automation, un format de date standard d'Excel. Voici comment convertir vos données Java. `GregorianCalendar` dates:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 15 janvier 2021
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Date de base d'Excel pour l'automatisation OLE
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### Conseils de dépannage :
- Assurez-vous de la date de base pour la conversion (`30 Dec 1899`) est correctement analysé.
- Vérifiez que votre environnement Java prend en charge les bibliothèques et les classes nécessaires.
- Si des problèmes surviennent, vérifiez les mises à jour ou les correctifs disponibles pour Aspose.Slides.

### Applications pratiques

La personnalisation des formats de date peut être particulièrement utile dans des scénarios tels que :
- **Rapports annuels :** Affichage clair des tendances annuelles des données.
- **Graphiques financiers :** Présentation précise des périodes fiscales.
- **Calendrier du projet :** Mettre en évidence des délais ou des étapes spécifiques.

En suivant ce guide, vous pourrez améliorer vos présentations avec des formats de date précis et visuellement attrayants en utilisant Aspose.Slides pour Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
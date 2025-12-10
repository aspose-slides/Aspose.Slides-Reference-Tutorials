---
date: '2025-12-10'
description: Apprenez à ajouter du texte à un tableau et à dessiner des cadres autour
  du texte dans PowerPoint en utilisant Aspose.Slides for Java. Ce guide couvre la
  création de tableaux, le réglage de l'alignement du texte et l'encadrement du contenu.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides pour Java – ajouter du texte à un tableau et manipulation de
  cadre
url: /fr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser la manipulation des tableaux et des cadres dans les présentations avec Aspose.Slides pour Java

## Introduction

Présenter des données de manière efficace peut être difficile dans PowerPoint. Que vous soyez développeur logiciel ou concepteur de présentations, **add text to table** des cellules et dessiner des cadres autour des paragraphes clés permet de rendre vos diapositives percutantes. Dans ce tutoriel, vous verrez exactement comment **add text to table**, l’aligner et dessiner des cadres autour du texte — le tout avec Aspose.Slides pour Java. À la fin, vous serez capable de créer des présentations soignées qui mettent en avant les bonnes informations au bon moment.

Prêt à transformer vos présentations ? C’est parti !

## Quick Answers
- **What does “add text to table” mean?** Cela signifie insérer ou mettre à jour le contenu textuel des cellules individuelles d’un tableau de façon programmatique.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – cette étape **save presentation as pptx** finalise vos modifications.  
- **How can I align text inside a shape?** Utilisez `TextAlignment.Left` (ou Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Oui – parcourez les paragraphes, récupérez leur rectangle englobant et ajoutez un `IAutoShape` sans remplissage et avec une bordure noire.  
- **Do I need a license?** Une licence temporaire suffit pour l’évaluation ; une licence complète est requise pour une utilisation en production.

## Prerequisites

Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

### Required Libraries
Vous aurez besoin d’Aspose.Slides pour Java. Voici comment l’inclure avec Maven ou Gradle :

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

### Environment Setup
Assurez‑vous d’avoir un Java Development Kit (JDK) installé, de préférence JDK 16 ou supérieur, car cet exemple utilise le classificateur `jdk16`.

### Knowledge Prerequisites
- Compréhension de base de la programmation Java.  
- Familiarité avec les logiciels de présentation comme PowerPoint.  
- Expérience avec un environnement de développement intégré (IDE) tel qu’IntelliJ IDEA ou Eclipse.

## Setting Up Aspose.Slides for Java

Pour commencer à utiliser Aspose.Slides, suivez ces étapes :

1. **Install the Library** : Utilisez Maven ou Gradle pour gérer les dépendances, ou téléchargez‑la directement depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition** :
   - Commencez avec un essai gratuit en téléchargeant une licence temporaire depuis [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Pour un accès complet, envisagez d’acheter une licence sur [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization** :
Initialisez votre environnement de présentation avec le fragment de code suivant :
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Why add text to table and draw frames?

Ajouter du texte à un tableau vous permet de présenter des données structurées de façon claire, tandis que dessiner des cadres autour de paragraphes ou de portions spécifiques (par ex. celles contenant le caractère **'0'**) attire l’attention du public sur les valeurs importantes. Cette combinaison est idéale pour les rapports financiers, les tableaux de bord ou toute diapositive où il faut mettre en avant des chiffres clés sans encombrer la vue.

## How to add text to table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
Cette fonctionnalité montre comment **how to create table**, puis **add text to table** aux cellules et enfin **save presentation as pptx**.

#### Steps

**1. Create a Table**  
Tout d’abord, initialisez votre présentation et ajoutez un tableau à la position (50, 50) avec les largeurs de colonnes et hauteurs de lignes spécifiées.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Créez des paragraphes contenant des portions de texte et ajoutez‑les à une cellule précise.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 2: Add TextFrame to AutoShape and Set Alignment

#### Overview
Apprenez à ajouter un cadre de texte avec un alignement spécifique à une forme auto‑shape—un exemple de **set text alignment java**.

#### Steps

**1. Add an AutoShape**  
Ajoutez un rectangle en tant qu’AutoShape à la position (400, 100) avec les dimensions spécifiées.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Définissez le texte à « Text in shape » et alignez‑le à gauche.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 3: Draw Frames around Paragraphs and Portions in Table Cells

#### Overview
Cette fonctionnalité se concentre sur **draw frames around text** et même **draw rectangle around paragraph** pour les portions contenant le caractère ‘0’.

#### Steps

**1. Create a Table**  
Réutilisez le code de « Create Table and Add Text to Cells » pour la configuration initiale.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Réutilisez le code de création de paragraphes de la fonctionnalité précédente.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Draw Frames**  
Parcourez les paragraphes et les portions pour dessiner des cadres autour d’eux.
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Conclusion
En suivant ce guide, vous pouvez **add text to table**, aligner le texte à l’intérieur des formes, et **draw frames around text** pour mettre en évidence les informations importantes. Maîtriser ces techniques vous permet de créer des présentations très soignées et axées sur les données avec Aspose.Slides pour Java. Pour aller plus loin, essayez de combiner ces fonctionnalités avec des graphiques, des animations ou l’exportation en PDF.

## Frequently Asked Questions

**Q: Can I use these APIs with older JDK versions?**  
R : La bibliothèque prend en charge JDK 8 et versions ultérieures, mais le classificateur `jdk16` offre les meilleures performances sur les environnements d’exécution récents.

**Q: How do I change the frame color?**  
R : Modifiez la couleur de remplissage du format de ligne, par ex. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
R : Oui—utilisez `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` puis enregistrez le tableau d’octets.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
R : Parcourez `cell.getTextFrame().getParagraphs()`, localisez la portion contenant « Total », et dessinez un rectangle autour du cadre englobant de cette portion.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
R : L’API diffuse les données et libère les ressources lorsque `pres.dispose()` est appelé, ce qui aide à la gestion de la mémoire pour les gros fichiers.

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
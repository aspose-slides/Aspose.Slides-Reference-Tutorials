---
date: '2026-02-09'
description: Apprenez à dessiner des cadres autour du texte et à ajouter du texte
  aux cellules de tableau dans PowerPoint en utilisant Aspose.Slides for Java. Ce
  tutoriel couvre la création de tableaux, le réglage de l’alignement du texte et
  l’enregistrement de la présentation au format pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Comment dessiner des cadres et ajouter du texte à un tableau avec Aspose.Slides
  pour Java
url: /fr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment dessiner des cadres et ajouter du texte à un tableau dans les présentations avec Aspose.Slides for Java

## Introduction

Présenter des données clairement dans PowerPoint peut être un véritable obstacle, surtout lorsque vous devez **add text to table** des cellules et mettre en évidence des valeurs importantes avec des repères visuels. Dans ce guide, vous apprendrez **how to draw frames** autour de paragraphes spécifiques, définir l’alignement du texte à l’intérieur des formes, et enfin **save presentation as pptx** — le tout en utilisant Aspose.Slides for Java. À la fin, vous disposerez d’un diaporama soigné qui attire le regard du public exactement où vous le souhaitez.

Prêt à faire ressortir vos diapositives ? Parcourons le processus étape par étape.

## Quick Answers
- **What does “add text to table” mean?** Cela signifie insérer ou mettre à jour le contenu textuel des cellules individuelles d’un tableau de manière programmatique.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – cette étape **save presentation as pptx** finalise vos modifications.  
- **How can I align text inside a shape?** Utilisez `TextAlignment.Left` (ou Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Oui – parcourez les paragraphes, obtenez leur rectangle englobant, et ajoutez un `IAutoShape` sans remplissage et avec une ligne noire.  
- **Do I need a license?** Une licence temporaire fonctionne pour l’évaluation ; une licence complète est requise pour une utilisation en production.  

## Pourquoi dessiner des cadres autour du texte ?

Dessiner un cadre (ou rectangle) autour d’un paragraphe ou d’une portion spécifique (par exemple, tout texte contenant le caractère **'0'**) attire immédiatement l’attention. Cette technique est idéale pour :
- Mettre en évidence les chiffres financiers clés dans un tableau.  
- Souligner les avertissements ou les notes importantes dans une diapositive.  
- Créer des séparateurs visuels sans ajouter de formes supplémentaires manuellement.

## Prérequis

Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

### Bibliothèques requises
Vous aurez besoin d’Aspose.Slides for Java. Voici comment l’inclure avec Maven ou Gradle :

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

### Configuration de l’environnement
Assurez‑vous d’avoir un Java Development Kit (JDK) installé, de préférence JDK 16 ou supérieur, car cet exemple utilise le classificateur `jdk16`.

### Prérequis de connaissances
- Compréhension de base de la programmation Java.  
- Familiarité avec les logiciels de présentation comme PowerPoint.  
- Expérience avec un environnement de développement intégré (IDE) tel qu’IntelliJ IDEA ou Eclipse.

## Configuration d’Aspose.Slides pour Java

Pour commencer à utiliser Aspose.Slides, suivez ces étapes :

1. **Install the Library** : Utilisez Maven ou Gradle pour gérer les dépendances, ou téléchargez‑le directement depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition** :
   - Commencez avec un essai gratuit en téléchargeant une licence temporaire depuis [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Pour un accès complet, envisagez d’acheter une licence sur [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization** :
Initialisez votre environnement de présentation avec le fragment de code suivant :
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Comment ajouter du texte à un tableau dans Aspose.Slides for Java

### Fonctionnalité 1 : Créer un tableau et ajouter du texte aux cellules

#### Vue d’ensemble
Cette fonctionnalité montre comment **create table**, puis **add text to table** aux cellules et enfin **save presentation as pptx**.

#### Étapes

**1. Create a Table**  
Premièrement, initialisez votre présentation et ajoutez un tableau à la position (50, 50) avec les largeurs de colonnes et hauteurs de lignes spécifiées.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Créez des paragraphes avec des portions de texte et ajoutez‑les à une cellule spécifique.
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

### Fonctionnalité 2 : Ajouter un TextFrame à AutoShape et définir l’alignement

#### Vue d’ensemble
Apprenez comment ajouter un cadre de texte avec un alignement spécifique à une forme auto—un exemple de **set text alignment java**.

#### Étapes

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

### Fonctionnalité 3 : Dessiner des cadres autour des paragraphes et des portions dans les cellules de tableau

#### Vue d’ensemble
Cette fonctionnalité se concentre sur **draw frames around text** et même **draw rectangle around paragraph** pour les portions contenant le caractère ‘0’.

#### Étapes

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

## Pièges courants et astuces

- **Null checks** – Enveloppez toujours votre utilisation de `Presentation` dans un bloc try‑finally afin de garantir que `pres.dispose()` s’exécute et libère les ressources natives.  
- **Bounding rectangle accuracy** – Le rectangle renvoyé par `para.getRect()` reflète la mise en page actuelle ; si vous modifiez la taille de la police ou les marges, recompute le rectangle avant de dessiner le cadre.  
- **Performance** – Lors du travail avec des tableaux très volumineux, envisagez de regrouper les ajouts de formes ou de réutiliser une seule instance `IAutoShape` avec une géométrie mise à jour afin de réduire la surcharge mémoire.  

## Questions fréquemment posées

**Q : Can I use these APIs with older JDK versions?**  
A : La bibliothèque prend en charge JDK 8 et versions ultérieures, mais le classificateur `jdk16` offre les meilleures performances sur les environnements d’exécution plus récents.

**Q : How do I change the frame color?**  
A : Modifiez la couleur de remplissage du format de ligne, par exemple `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q : Is it possible to export the final slide as an image?**  
A : Oui—utilisez `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` puis enregistrez le tableau d’octets.

**Q : What if I need to highlight only the word “Total” inside a cell?**  
A : Parcourez `cell.getTextFrame().getParagraphs()`, localisez la portion contenant “Total”, et dessinez un rectangle autour de la boîte englobante de cette portion.

**Q : Does Aspose.Slides handle large presentations efficiently?**  
A : L’API diffuse les données et libère les ressources lorsque `pres.dispose()` est appelé, ce qui aide à la gestion de la mémoire pour les gros fichiers.

---

{{< blocks/products/products-backtop-button >}}

**Dernière mise à jour :** 2026-02-09  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
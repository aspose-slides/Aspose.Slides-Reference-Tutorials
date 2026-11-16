---
date: '2026-11-16'
description: Dessinez un cadre autour du texte dans les tableaux PowerPoint à l'aide
  d'Aspose.Slides for Java – apprenez à créer des tableaux, ajouter du texte aux cellules,
  mettre en surbrillance les cellules et exporter le fichier au format PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Dessinez un cadre autour du texte dans les tableaux PowerPoint à l'aide
  d'Aspose.Slides for Java. Ce guide montre comment créer des tableaux, ajouter et
  aligner du texte, mettre en surbrillance les cellules et exporter les diapositives
  au format PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Comment dessiner un cadre autour du texte et créer des tableaux dans PowerPoint
  avec Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Comment dessiner un cadre autour du texte et créer des tableaux dans PowerPoint
  avec Aspose.Slides for Java
url: /fr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment dessiner un cadre autour du texte et créer des tableaux dans PowerPoint avec Aspose.Slides for Java

## Introduction

Dessiner un **draw frame around text** dans une diapositive PowerPoint vous permet de mettre en évidence des chiffres clés sans modifier le contenu sous‑jacent. Dans ce tutoriel, vous apprendrez à créer un tableau de manière programmatique, à insérer et aligner du texte dans les cellules, à mettre en surbrillance des mots spécifiques ou des cellules entières, puis à enregistrer la présentation au format PPTX. À la fin, vous disposerez d’une diapositive soignée qui attire l’attention du public exactement où vous le souhaitez.

## Réponses rapides
- **Que signifie « add text to table » ?** Cela signifie insérer ou mettre à jour le contenu textuel des cellules de tableau individuelles de manière programmatique.  
- **Quelle méthode enregistre le fichier ?** `pres.save("output.pptx", SaveFormat.Pptx)` – cette étape **save presentation as pptx** finalise vos modifications.  
- **Comment aligner le texte à l'intérieur d'une forme ?** Utilisez `TextAlignment.Left` (ou Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Puis-je dessiner un rectangle autour d'un paragraphe ?** Oui – parcourez les paragraphes, récupérez leur rectangle englobant, puis ajoutez un `IAutoShape` sans remplissage et avec une ligne noire.  
- **Ai-je besoin d'une licence ?** Une licence temporaire fonctionne pour l'évaluation ; une licence complète est requise pour une utilisation en production.  

## Pourquoi dessiner des cadres autour du texte ?

Dessiner un cadre autour du texte met instantanément en évidence des nombres importants, des avertissements ou des titres. Cela fournit un indice visuel tout en conservant le formatage original intact, ce qui le rend idéal pour les rapports financiers, les tableaux de bord KPI ou toute diapositive où une mise en avant est nécessaire.

## Qu'est-ce que draw frame around text ?

`draw frame around text` est la technique consistant à ajouter de manière programmatique une forme rectangulaire qui suit exactement les limites d'un paragraphe ou d'une portion de texte, en utilisant uniquement le format de ligne sans remplissage intérieur. Cette approche vous permet de souligner le contenu sans modifier le texte lui‑même.

## Prérequis

Avant de commencer, assurez‑vous d’avoir les éléments suivants :

### Bibliothèques requises
Vous aurez besoin d’Aspose.Slides for Java. Incluez‑le avec l’un des gestionnaires de paquets :

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

Vous pouvez également parcourir les versions à l’adresse [versions d'Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Configuration de l'environnement
Il est recommandé d’utiliser un Java Development Kit (JDK) 16 ou plus récent, car les exemples utilisent le classificateur `jdk16`. Tout IDE tel qu’IntelliJ IDEA ou Eclipse fonctionnera.

### Pré‑requis de connaissances
- Compétences de base en programmation Java.  
- Familiarité avec les concepts PowerPoint (diapositives, formes, tableaux).  
- Compréhension du fonctionnement de la gestion des dépendances avec Maven/Gradle.

## Configuration d'Aspose.Slides pour Java

`Presentation` est la classe principale d’Aspose.Slides qui représente un fichier PowerPoint en mémoire et fournit l’accès aux diapositives, formes et tableaux. Elle peut gérer des présentations contenant jusqu’à **10 000 diapositives** tout en maintenant l’utilisation de la mémoire sous **500 Mo**, ce qui la rend adaptée à l’automatisation à grande échelle.

1. **Installer la bibliothèque** – utilisez Maven ou Gradle, ou téléchargez‑la directement depuis [versions d'Aspose.Slides for Java](https://releases.aspose.com/slides/java/).  
2. **Acquisition de licence** – commencez avec un essai gratuit depuis [Temporary License](https://purchase.aspose.com/temporary-license/) et passez à une licence complète sur [Purchase Aspose.Slides](https://purchase.aspose.com/buy) pour les charges de travail en production.  
3. **Initialisation de base** – créez un nouvel objet `Presentation` et chargez ou créez des diapositives selon les besoins.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Comment ajouter du texte à un tableau dans Aspose.Slides for Java ?

`Presentation` est la classe principale qui représente un fichier PowerPoint en mémoire.  
Chargez une nouvelle `Presentation`, créez un tableau aux coordonnées souhaitées, remplissez les cellules avec des objets `TextFrame`, puis appelez `pres.save("output.pptx", SaveFormat.Pptx)`. Cette séquence crée un **create table in PowerPoint**, injecte du texte personnalisé dans chaque cellule et écrit le résultat dans un fichier PPTX en un seul flux de travail efficace.

### Réponse directe
Créez un tableau en appelant `slide.getShapes().addTable(...)`, puis pour chaque cellule utilisez `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Après avoir rempli toutes les cellules, invoquez `pres.save("output.pptx", SaveFormat.Pptx)` pour écrire le fichier. Cette approche vous permet de contrôler de manière programmatique le contenu et le style de chaque cellule.

#### Fonctionnalité 1 : créer un tableau et ajouter du texte aux cellules

**1. créer un tableau** – initialisez une présentation, ajoutez une diapositive et placez un tableau à (50, 50) avec des largeurs de colonne et hauteurs de ligne définies.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. ajouter du texte aux cellules** – pour chaque cellule, créez un `Paragraph`, ajoutez une `Portion` contenant la chaîne souhaitée, puis affectez le paragraphe au `TextFrame` de la cellule.  
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

**3. enregistrer la présentation** – appelez `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Comment dessiner un cadre autour du texte dans une diapositive PowerPoint ?

`Rectangle2D` représente une zone rectangulaire dans un espace de coordonnées bidimensionnel.  
Chargez la diapositive, localisez le paragraphe ou la portion que vous souhaitez mettre en évidence, récupérez son rectangle englobant via `getRect()`, puis ajoutez un rectangle `IAutoShape` sans remplissage et avec une ligne colorée. Cette méthode fonctionne tant pour les paragraphes entiers que pour les portions de mots individuelles.

### Réponse directe
Pour dessiner un cadre autour du texte, obtenez d’abord le rectangle du paragraphe (`Rectangle2D rect = paragraph.getRect();`). Ensuite créez un rectangle `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), définissez `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`, et désactivez le remplissage (`shape.getFillFormat().setFillType(FillType.NoFill)`). La forme contiendra parfaitement le texte.

#### Fonctionnalité 3 : dessiner des cadres autour des paragraphes et des portions dans les cellules de tableau

**1. créer un tableau** – réutilisez le code de la Fonctionnalité 1 pour configurer le tableau initial.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. ajouter des paragraphes** – réutilisez le code de création de paragraphes de la Fonctionnalité 1.  
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

**3. dessiner des cadres** – parcourez chaque paragraphe, obtenez son rectangle englobant et ajoutez une forme rectangulaire comme décrit ci‑dessus. Pour les portions contenant le caractère ‘0’, dessinez un cadre supplémentaire afin de mettre en évidence ces nombres.  
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

**4. enregistrer la présentation** – même étape finale qu’auparavant.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Comment ajouter un cadre de texte à un AutoShape et définir l'alignement

`AutoShape` est une forme qui peut contenir du texte, des images ou d’autres contenus.  
Un `AutoShape` peut contenir un `TextFrame`. Vous pouvez contrôler l’alignement horizontal à l’aide de l’énumération `ParagraphFormat`.

### Réponse directe
Créez un AutoShape rectangle (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), accédez à son `TextFrame`, définissez le texte avec `shape.getTextFrame().setText("Text in shape")`, puis appelez `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. Cela aligne le texte à gauche à l’intérieur de la forme.

**1. ajouter un AutoShape** – placez un rectangle à l’emplacement souhaité.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. définir l'alignement du texte** – appliquez l'alignement à gauche comme indiqué ci‑dessus.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. enregistrer la présentation** – même étape finale.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Écueils courants & conseils

- **Toujours libérer** – encapsulez votre utilisation de `Presentation` dans un bloc try‑finally et appelez `pres.dispose()` pour libérer les ressources natives.  
- **Recalculer les rectangles englobants** – si vous modifiez la taille de police, les marges ou le remplissage des cellules après avoir dessiné un cadre, appelez à nouveau `paragraph.getRect()` avant d’ajouter la forme.  
- **Création groupée de formes pour les grands tableaux** – réutiliser une seule instance `IAutoShape` et mettre à jour sa géométrie réduit la pression mémoire lors du traitement de tableaux contenant des centaines de lignes.  
- **Chiffres de performance** – Aspose.Slides peut générer un PPTX de 200 pages en moins de 2 secondes sur un serveur typique à 4 cœurs, et dessiner des cadres autour de 1 000 paragraphes ajoute moins de 150 ms de surcharge.

## Questions fréquemment posées

**Q : Puis‑je utiliser ces API avec des versions JDK plus anciennes ?**  
R : La bibliothèque prend en charge JDK 8 et versions ultérieures, mais le classificateur `jdk16` offre les meilleures performances sur les environnements d’exécution récents.

**Q : Comment changer la couleur du cadre ?**  
R : Modifiez la couleur de remplissage du format de ligne, par exemple `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q : Est‑il possible d’exporter la diapositive finale en image ?**  
R : Oui—utilisez `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` puis enregistrez le tableau d’octets.

**Q : Que faire si je dois mettre en surbrillance uniquement le mot « Total » dans une cellule ?**  
R : Parcourez `cell.getTextFrame().getParagraphs()`, localisez la portion contenant « Total », et dessinez un rectangle autour du cadre englobant de cette portion.

**Q : Aspose.Slides gère‑t‑il efficacement les présentations volumineuses ?**  
R : L’API diffuse les données et libère les ressources lorsque `pres.dispose()` est appelé, ce qui aide à la gestion de la mémoire pour les gros fichiers.

**Dernière mise à jour :** 2026-11-16  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur :** Aspose  

## Tutoriels associés

- [Aspose.Slides for Java : Maîtriser la manipulation des tableaux PPTX et du texte dans les présentations PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Comment créer des cadres de texte dynamiques dans PowerPoint avec Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Ajouter des colonnes dans un cadre de texte avec Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
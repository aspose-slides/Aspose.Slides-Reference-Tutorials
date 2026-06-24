---
date: '2026-06-23'
description: Apprenez comment créer un tableau dans PowerPoint, ajouter du texte aux
  cellules du tableau, dessiner des cadres autour du texte et enregistrer la présentation
  au format pptx en utilisant Aspose.Slides for Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: Comment créer un tableau dans PowerPoint et dessiner des cadres avec Aspose.Slides
  for Java
url: /fr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un tableau dans PowerPoint et dessiner des cadres avec Aspose.Slides pour Java

## Introduction

Créer un **tableau dans PowerPoint** de manière programmatique peut vous faire gagner des heures de mise en forme manuelle, surtout lorsque vous devez mettre en évidence des chiffres clés ou ajouter des notes explicatives. Dans ce tutoriel, vous découvrirez comment ajouter du texte aux cellules d’un tableau, dessiner des cadres autour de paragraphes spécifiques, définir un alignement précis du texte, et enfin **enregistrer la présentation au format pptx** – le tout avec la puissante API Aspose.Slides pour Java. À la fin, vous disposerez d’une diapositive soignée, facile à lire, qui attire instantanément l’attention du public sur les données les plus importantes.

## Réponses rapides
- **Que signifie « ajouter du texte à un tableau » ?** Cela signifie insérer ou mettre à jour le contenu textuel des cellules individuelles d’un tableau de façon programmatique.  
- **Quelle méthode enregistre le fichier ?** `pres.save("output.pptx", SaveFormat.Pptx)` – cette étape **enregistrer la présentation au format pptx** finalise vos modifications.  
- **Comment aligner le texte à l’intérieur d’une forme ?** Utilisez `TextAlignment.Left` (ou Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Puis‑je dessiner un rectangle autour d’un paragraphe ?** Oui – parcourez les paragraphes, récupérez leur rectangle englobant, et ajoutez un `IAutoShape` sans remplissage et avec une bordure noire.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire fonctionne pour l’évaluation ; une licence complète est requise pour une utilisation en production.  

## Pourquoi dessiner des cadres autour du texte ?

Dessiner un cadre (ou rectangle) autour d’un paragraphe ou d’une portion spécifique – par exemple tout texte contenant le caractère **'0'** – attire immédiatement l’attention du public sur ce contenu. Cela fournit un indice visuel clair sans modifier le texte sous‑jacent, ce qui est idéal pour mettre en évidence des chiffres clés, des avertissements ou séparer des sections au sein d’une diapositive.

## Pré‑requis

Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

### Bibliothèques requises
Vous aurez besoin d’Aspose.Slides pour Java. Voici comment l’inclure avec Maven ou Gradle :

**Maven :**  
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

### Configuration de l'environnement
Assurez‑vous d’avoir un Java Development Kit (JDK) installé, de préférence le JDK 16 ou une version ultérieure, car cet exemple utilise le classificateur `jdk16`.

### Pré‑requis de connaissances
- Compréhension de base de la programmation Java.  
- Familiarité avec les logiciels de présentation comme PowerPoint.  
- Expérience avec un environnement de développement intégré (IDE) tel qu’IntelliJ IDEA ou Eclipse.

## Configuration d'Aspose.Slides pour Java

`Presentation` est la classe principale d’Aspose.Slides qui représente un fichier PowerPoint en mémoire et donne accès aux diapositives, formes et tableaux. Pour commencer à utiliser Aspose.Slides, suivez ces étapes :

1. **Installer la bibliothèque** : utilisez Maven ou Gradle pour gérer les dépendances, ou téléchargez‑la directement depuis [versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

2. **Acquisition de licence** :
   - Commencez avec un essai gratuit en téléchargeant une licence temporaire depuis [Licence temporaire](https://purchase.aspose.com/temporary-license/).
   - Pour un accès complet, envisagez d’acheter une licence sur [Acheter Aspose.Slides](https://purchase.aspose.com/buy).

3. **Initialisation de base** :  
   Initialise votre environnement de présentation avec le fragment de code suivant :  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Comment ajouter du texte à un tableau dans Aspose.Slides pour Java ?

Chargez une nouvelle `Presentation`, créez un tableau aux coordonnées souhaitées, remplissez les cellules avec des objets `TextFrame`, puis appelez `pres.save("output.pptx", SaveFormat.Pptx)`. Cette séquence crée un **tableau dans PowerPoint**, injecte du texte personnalisé dans chaque cellule, et écrit le résultat dans un fichier PPTX en un seul flux de travail efficace.

### Fonctionnalité 1 : Créer un tableau et ajouter du texte aux cellules

#### Vue d'ensemble
Cette fonctionnalité montre comment **créer un tableau**, puis **ajouter du texte aux cellules du tableau** et enfin **enregistrer la présentation au format pptx**.

#### Étapes

**1. Créer un tableau**  
Tout d’abord, initialisez votre présentation et ajoutez un tableau à la position (50, 50) avec les largeurs de colonnes et hauteurs de lignes spécifiées.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Ajouter du texte aux cellules**  
Créez des paragraphes contenant des portions de texte et ajoutez‑les à une cellule spécifique.  
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

**3. Enregistrer la présentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Fonctionnalité 2 : Ajouter un TextFrame à une AutoShape et définir l’alignement

#### Vue d'ensemble
Apprenez à ajouter un cadre de texte avec un alignement spécifique à une forme auto – un exemple de **définir l'alignement du texte java**.

#### Étapes

Une AutoShape est une forme pouvant contenir du texte et des graphiques.

**1. Ajouter une AutoShape**  
Ajoutez un rectangle en tant qu’AutoShape à la position (400, 100) avec les dimensions spécifiées.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

L’énumération `TextAlignment` définit les options d’alignement horizontal du texte à l’intérieur d’une forme.

**2. Définir l’alignement du texte**  
Définissez le texte à « Texte dans la forme » et alignez‑le à gauche.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Enregistrer la présentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Fonctionnalité 3 : Dessiner des cadres autour des paragraphes et des portions dans les cellules de tableau

#### Vue d'ensemble
Cette fonctionnalité se concentre sur **dessiner des cadres autour du texte** et même **dessiner un rectangle autour d’un paragraphe** pour les portions contenant le caractère ‘0’.

#### Étapes

`IAutoShape` représente un objet forme pouvant être dessiné sur une diapositive, comme les rectangles utilisés pour les cadres.

**1. Créer un tableau**  
Réutilisez le code de « Créer un tableau et ajouter du texte aux cellules » pour la configuration initiale.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Ajouter des paragraphes**  
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

**3. Dessiner des cadres**  
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

**4. Enregistrer la présentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Pièges courants & astuces

- **Vérifications de null** – Enveloppez toujours votre utilisation de `Presentation` dans un bloc try‑finally afin de garantir que `pres.dispose()` s’exécute et libère les ressources natives.  
- **Précision du rectangle englobant** – Le rectangle renvoyé par `para.getRect()` reflète la mise en page actuelle ; si vous modifiez la taille de police ou les marges, recompute‑z le rectangle avant de dessiner le cadre.  
- **Performance** – Lors du traitement de très grands tableaux, envisagez de regrouper les ajouts de formes ou de réutiliser une seule instance `IAutoShape` avec une géométrie mise à jour afin de réduire la charge mémoire.  

## FAQ

**Q : Puis‑je utiliser ces API avec des versions plus anciennes du JDK ?**  
R : La bibliothèque prend en charge le JDK 8 et versions ultérieures, mais le classificateur `jdk16` offre les meilleures performances sur les environnements récents.

**Q : Comment changer la couleur du cadre ?**  
R : Modifiez la couleur de remplissage du format de ligne, par ex. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q : Est‑il possible d’exporter la diapositive finale en image ?**  
R : Oui—utilisez `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` puis enregistrez le tableau d’octets.

**Q : Et si je dois mettre en évidence uniquement le mot « Total » dans une cellule ?**  
R : Parcourez `cell.getTextFrame().getParagraphs()`, localisez la portion contenant « Total », et dessinez un rectangle autour du rectangle englobant de cette portion.

**Q : Aspose.Slides gère‑t‑il efficacement les présentations volumineuses ?**  
R : L’API diffuse les données et libère les ressources lorsque `pres.dispose()` est appelé, ce qui aide à la gestion de la mémoire pour les fichiers de grande taille.

---

**Dernière mise à jour :** 2026-06-23  
**Testé avec :** Aspose.Slides pour Java 25.4 (jdk16)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Aspose.Slides pour Java : Maîtriser la manipulation des tableaux et du texte PPTX dans les présentations PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Comment créer des cadres de texte dynamiques dans PowerPoint en utilisant Aspose.Slides pour Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Ajouter des colonnes dans un Text Frame avec Aspose.Slides pour Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
"date": "2025-04-18"
"description": "Apprenez à améliorer vos présentations en maîtrisant la manipulation des tableaux et des cadres avec Aspose.Slides pour Java. Ce guide aborde la création de tableaux, l'ajout de cadres de texte et le dessin de cadres autour de contenus spécifiques."
"title": "Aspose.Slides pour Java &#58; Maîtriser la manipulation des tableaux et des cadres dans les présentations"
"url": "/fr/java/animations-transitions/aspose-slides-java-enhance-presentations/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser la manipulation des tableaux et des cadres dans les présentations avec Aspose.Slides pour Java

## Introduction

Présenter efficacement des données dans PowerPoint peut s'avérer complexe. Que vous soyez développeur de logiciels ou concepteur de présentations, l'utilisation de tableaux attrayants et l'ajout de cadres de texte peuvent rendre vos diapositives plus attrayantes. Ce tutoriel explique comment utiliser Aspose.Slides pour Java pour ajouter du texte aux cellules d'un tableau et dessiner des cadres autour des paragraphes et des parties contenant des caractères spécifiques comme « 0 ». En maîtrisant ces techniques, vous améliorerez vos présentations avec précision et style.

### Ce que vous apprendrez :
- Créer des tableaux dans des diapositives et les remplir avec du texte.
- Alignement du texte dans les formes automatiques pour une meilleure présentation.
- Dessiner des cadres autour des paragraphes et des parties pour mettre en valeur le contenu.
- Applications pratiques de ces fonctionnalités dans des scénarios réels.

Prêt à transformer vos présentations ? C'est parti !

## Prérequis

Avant de plonger dans le code, assurez-vous de disposer des éléments suivants :

### Bibliothèques requises
Vous aurez besoin d'Aspose.Slides pour Java. Voici comment l'inclure avec Maven ou Gradle :

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

### Configuration de l'environnement
Assurez-vous d'avoir un kit de développement Java (JDK) installé, de préférence JDK 16 ou une version ultérieure, car cet exemple utilise le `jdk16` classificateur.

### Prérequis en matière de connaissances
- Compréhension de base de la programmation Java.
- Connaissance des logiciels de présentation comme PowerPoint.
- Expérience d'utilisation d'un environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse.

## Configuration d'Aspose.Slides pour Java

Pour commencer à utiliser Aspose.Slides, suivez ces étapes :

1. **Installer la bibliothèque**: Utilisez Maven ou Gradle pour gérer les dépendances, ou téléchargez-le directement depuis [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

2. **Acquisition de licence**:
   - Commencez par un essai gratuit en téléchargeant une licence temporaire à partir de [Permis temporaire](https://purchase.aspose.com/temporary-license/).
   - Pour un accès complet, pensez à acheter une licence sur [Acheter Aspose.Slides](https://purchase.aspose.com/buy).

3. **Initialisation de base**:
Initialisez votre environnement de présentation avec l'extrait de code suivant :
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Votre code ici
} finally {
    if (pres != null) pres.dispose();
}
```

## Guide de mise en œuvre

Cette section couvre différentes fonctionnalités que vous pouvez implémenter à l'aide d'Aspose.Slides pour Java.

### Fonctionnalité 1 : Créer un tableau et ajouter du texte aux cellules

#### Aperçu
Cette fonctionnalité montre comment créer un tableau sur la première diapositive et remplir des cellules spécifiques avec du texte. 

##### Mesures:
**1. Créer un tableau**
Tout d’abord, initialisez votre présentation et ajoutez un tableau à la position (50, 50) avec des largeurs de colonnes et des hauteurs de lignes spécifiées.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. Ajouter du texte aux cellules**
Créez des paragraphes avec des portions de texte et ajoutez-les à une cellule spécifique.
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
**3. Enregistrez la présentation**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Fonctionnalité 2 : Ajouter un cadre de texte à la forme automatique et définir l'alignement

#### Aperçu
Découvrez comment ajouter un cadre de texte avec un alignement spécifique à une forme automatique.

##### Mesures:
**1. Ajouter une forme automatique**
Ajoutez un rectangle en tant que forme automatique à la position (400, 100) avec les dimensions spécifiées.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```
**2. Définir l'alignement du texte**
Définissez le texte sur « Texte en forme » et alignez-le à gauche.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
**3. Enregistrez la présentation**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Fonctionnalité 3 : Dessiner des cadres autour des paragraphes et des portions dans les cellules d'un tableau

#### Aperçu
Cette fonctionnalité se concentre sur le dessin de cadres autour des paragraphes et des parties contenant « 0 » dans les cellules du tableau.

##### Mesures:
**1. Créer un tableau**
Réutilisez le code de « Créer un tableau et ajouter du texte aux cellules » pour la configuration initiale.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. Ajouter des paragraphes**
Réutiliser le code de création de paragraphes de la fonctionnalité précédente.
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
Parcourez les paragraphes et les parties pour dessiner des cadres autour d'eux.
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
**4. Enregistrez la présentation**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Conclusion
En suivant ce guide, vous pouvez améliorer efficacement vos présentations avec Aspose.Slides pour Java. Maîtriser la manipulation des tableaux et des cadres vous permet de créer des diapositives plus attrayantes et visuellement plus captivantes. Pour approfondir vos connaissances, n'hésitez pas à explorer les fonctionnalités supplémentaires d'Aspose.Slides ou à l'intégrer à d'autres applications Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
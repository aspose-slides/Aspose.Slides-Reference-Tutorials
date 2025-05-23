---
"date": "2025-04-18"
"description": "Apprenez à améliorer vos présentations en personnalisant les puces SmartArt avec des images grâce à Aspose.Slides pour Java. Suivez ce guide étape par étape pour un rendu professionnel."
"title": "Comment personnaliser les puces SmartArt avec des images avec Aspose.Slides pour Java | Guide étape par étape"
"url": "/fr/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment personnaliser les puces SmartArt avec des images à l'aide d'Aspose.Slides pour Java

## Introduction

Créer des présentations visuellement attrayantes est essentiel pour capter l'attention de votre public et communiquer efficacement votre message. L'un des défis courants lors de la conception de diapositives est d'enrichir les puces des graphiques SmartArt à l'aide d'images personnalisées. Ce tutoriel vous guidera dans la définition d'une image comme format de remplissage des puces dans les nœuds SmartArt avec Aspose.Slides pour Java, vous permettant ainsi de sublimer vos présentations de manière professionnelle.

**Ce que vous apprendrez :**
- Configuration et utilisation d'Aspose.Slides pour Java
- Personnalisation des puces avec des images dans les graphiques SmartArt
- Applications pratiques de cette personnalisation
- Dépannage des problèmes courants

Avant de nous lancer dans la mise en œuvre, assurez-vous que tout est prêt.

## Prérequis

Pour suivre ce tutoriel, assurez-vous de remplir les conditions préalables suivantes :

1. **Bibliothèques et dépendances**:Vous aurez besoin de la bibliothèque Aspose.Slides pour Java version 25.4 ou ultérieure.
2. **Configuration de l'environnement**:
   - Un IDE compatible comme IntelliJ IDEA ou Eclipse
   - JDK 16 installé sur votre machine
3. **Prérequis en matière de connaissances**: Familiarité avec la programmation Java et la structure de base des présentations PowerPoint.

## Configuration d'Aspose.Slides pour Java

Pour commencer, incluez la bibliothèque Aspose.Slides dans votre projet en utilisant l’une des méthodes suivantes :

### Maven

Ajoutez cette dépendance à votre `pom.xml` déposer:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Incluez ceci dans votre `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct

Vous pouvez également télécharger la bibliothèque directement depuis [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

**Étapes d'acquisition de licence**Aspose propose une licence d'essai gratuite, idéale pour tester ses fonctionnalités. Vous pouvez demander une licence temporaire ou en acheter une pour lever les restrictions d'évaluation.

Pour initialiser et configurer votre environnement, créez une instance du `Presentation` classe comme indiqué :

```java
Presentation presentation = new Presentation();
```

## Guide de mise en œuvre

Cette section décomposera le processus en étapes gérables, expliquant comment obtenir la fonctionnalité souhaitée.

### Ajout de SmartArt avec remplissage de puces personnalisé

#### Aperçu

Nous commencerons par ajouter une forme SmartArt à votre diapositive et personnaliser ses puces à l’aide d’un remplissage d’image.

#### Instructions étape par étape

**1. Initialiser l'objet de présentation**

```java
Presentation presentation = new Presentation();
```

*But*: Initialise une nouvelle instance de présentation dans laquelle vous ajouterez les graphiques SmartArt.

**2. Ajouter une forme SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Explication*: Cette ligne ajoute une nouvelle forme SmartArt à la première diapositive à la position (x=10, y=10) avec des dimensions de 500x400 pixels. `VerticalPictureList` la mise en page est utilisée pour l'alignement vertical.

**3. Accéder et personnaliser le remplissage des puces**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*But*: Vérifie si le nœud a un `BulletFillFormat` propriété. Si c'est le cas, il charge une image et la définit comme remplissage pour les puces.
*Paramètres*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: Le chemin vers votre fichier image.
  - `PictureFillMode.Stretch`: Garantit que l'image remplit complètement la zone de la puce.

**4. Enregistrez votre présentation**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
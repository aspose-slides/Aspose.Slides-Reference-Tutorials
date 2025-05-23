---
"date": "2025-04-18"
"description": "Apprenez à verrouiller ou déverrouiller les proportions des tableaux dans les présentations PowerPoint avec Aspose.Slides pour Java. Ce guide couvre la configuration, l'implémentation du code et les applications pratiques."
"title": "Comment verrouiller et déverrouiller les proportions des tableaux dans PowerPoint avec Aspose.Slides pour Java"
"url": "/fr/java/tables/lock-unlock-table-aspect-ratio-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment verrouiller et déverrouiller les proportions des tableaux dans PowerPoint avec Aspose.Slides pour Java

## Introduction

Vous avez du mal à maintenir la cohérence des tableaux dans vos présentations PowerPoint ? Grâce au verrouillage et au déverrouillage des proportions, gérer le redimensionnement des tableaux lors des modifications devient un jeu d'enfant. Ce tutoriel vous guide dans l'utilisation d'« Aspose.Slides pour Java » pour contrôler efficacement les dimensions des tableaux. Vous apprendrez non seulement à manipuler les proportions, mais aussi à intégrer cette fonctionnalité à des workflows de présentation plus larges.

**Ce que vous apprendrez :**
- Comment verrouiller et déverrouiller le rapport hauteur/largeur des tableaux dans les présentations PowerPoint.
- Le processus de configuration d'Aspose.Slides pour Java à l'aide de Maven, Gradle ou de téléchargements directs.
- Implémentation de code étape par étape avec des explications claires.
- Applications pratiques et considérations de performances lors du travail avec de grands diaporamas.

Plongeons dans les prérequis avant de commencer.

## Prérequis

Pour suivre ce tutoriel, assurez-vous d'avoir :
- **Kit de développement Java (JDK) :** Version 16 ou ultérieure installée sur votre machine.
- **IDE:** Tout IDE Java comme IntelliJ IDEA ou Eclipse.
- **Maven/Gradle :** Si vous choisissez d’utiliser des gestionnaires de packages pour les dépendances.
- Compréhension de base de la programmation Java et familiarité avec les fonctionnalités de tableau de PowerPoint.

## Configuration d'Aspose.Slides pour Java

### Configuration de Maven
Pour inclure Aspose.Slides dans votre projet à l'aide de Maven, ajoutez la dépendance suivante :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Configuration de Gradle
Pour ceux qui utilisent Gradle, incluez ceci dans votre `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger la dernière version à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

#### Étapes d'acquisition de licence
- **Essai gratuit :** Commencez par un essai gratuit pour explorer les fonctionnalités de base.
- **Licence temporaire :** Obtenez une licence temporaire pour un accès complet aux fonctionnalités pendant l'évaluation.
- **Licence d'achat :** Envisagez d’acheter une licence pour une utilisation à long terme et ininterrompue.

Après avoir configuré votre environnement et acquis les licences nécessaires, initialisez Aspose.Slides dans votre application Java comme suit :

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        // Votre code ici...
    }
}
```

## Guide de mise en œuvre

### Rapport hauteur/largeur du tableau de verrouillage/déverrouillage

Cette fonctionnalité vous permet de conserver ou d'ajuster le rapport hauteur/largeur des tableaux dans vos présentations, garantissant ainsi une conception et une lisibilité cohérentes.

#### Accéder à une table
Commencez par charger votre présentation et accédez au tableau souhaité :

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ITable;

// Charger le fichier de présentation.
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/pres.pptx");
ITable table = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

#### Vérification et modification du rapport hauteur/largeur

Vérifiez si le rapport hauteur/largeur est verrouillé, puis basculez son état :

```java
// Vérifiez l'état actuel du verrouillage du rapport hauteur/largeur.
boolean isLocked = table.getGraphicalObjectLock().getAspectRatioLocked();

// Inverser l'état de verrouillage du rapport hauteur/largeur.
table.getGraphicalObjectLock().setAspectRatioLocked(!isLocked);
```

Cette fonction de basculement permet des ajustements flexibles pendant votre processus de conception.

#### Sauvegarde des modifications
Après avoir apporté des modifications, enregistrez la présentation mise à jour :

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/pres-out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
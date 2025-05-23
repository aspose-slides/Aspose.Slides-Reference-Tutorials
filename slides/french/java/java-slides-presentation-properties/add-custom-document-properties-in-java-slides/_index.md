---
"description": "Découvrez comment améliorer vos présentations PowerPoint avec des propriétés de document personnalisées dans Java Slides. Guide étape par étape avec des exemples de code utilisant Aspose.Slides pour Java."
"linktitle": "Ajouter des propriétés de document personnalisées dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter des propriétés de document personnalisées dans les diapositives Java"
"url": "/fr/java/presentation-properties/add-custom-document-properties-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des propriétés de document personnalisées dans les diapositives Java


## Introduction à l'ajout de propriétés de document personnalisées dans les diapositives Java

Dans ce tutoriel, nous vous expliquerons comment ajouter des propriétés de document personnalisées à une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Ces propriétés vous permettent de stocker des informations supplémentaires sur la présentation à des fins de référence ou de catégorisation.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java.

## Étape 1 : Importer les packages requis

```java
import com.aspose.slides.*;
```

## Étape 2 : Créer une nouvelle présentation

Tout d'abord, vous devez créer un nouvel objet de présentation. Pour ce faire, procédez comme suit :

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";

// Instancier la classe Presentation
Presentation presentation = new Presentation();
```

## Étape 3 : Obtenir les propriétés du document

Ensuite, vous récupérerez les propriétés de la présentation. Ces propriétés incluent des propriétés intégrées comme le titre, l'auteur et des propriétés personnalisées que vous pouvez ajouter.

```java
// Obtenir les propriétés du document
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Étape 4 : Ajout de propriétés personnalisées

Ajoutons maintenant des propriétés personnalisées à la présentation. Ces propriétés sont composées d'un nom et d'une valeur. Vous pouvez les utiliser pour stocker toutes les informations souhaitées.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Étape 5 : Obtenir un nom de propriété à un index particulier

Vous pouvez également récupérer le nom d'une propriété personnalisée à un index spécifique. Cela peut être utile si vous devez travailler avec des propriétés spécifiques.

```java
// Obtenir le nom de la propriété à un index particulier
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Étape 6 : Suppression d'une propriété sélectionnée

Si vous souhaitez supprimer une propriété personnalisée, vous pouvez le faire en spécifiant son nom. Ici, nous supprimons la propriété obtenue à l'étape 5.

```java
// Suppression de la propriété sélectionnée
documentProperties.removeCustomProperty(getPropertyName);
```

## Étape 7 : Enregistrer la présentation

Enfin, enregistrez la présentation avec les propriétés personnalisées ajoutées et supprimées dans un fichier.

```java
// Sauvegarde de la présentation
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Code source complet pour ajouter des propriétés de document personnalisées dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier la classe Presentation
Presentation presentation = new Presentation();
// Obtenir les propriétés du document
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Ajout de propriétés personnalisées
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Obtenir le nom de la propriété à un index particulier
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Suppression de la propriété sélectionnée
documentProperties.removeCustomProperty(getPropertyName);
// Sauvegarde de la présentation
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Vous avez appris à ajouter des propriétés de document personnalisées à une présentation PowerPoint en Java avec Aspose.Slides. Les propriétés personnalisées peuvent être utiles pour stocker des informations supplémentaires relatives à vos présentations. Vous pouvez approfondir ces connaissances pour inclure davantage de propriétés personnalisées selon vos besoins spécifiques.

## FAQ

### Comment récupérer la valeur d'une propriété personnalisée ?

Pour récupérer la valeur d’une propriété personnalisée, vous pouvez utiliser le `get_Item` méthode sur le `documentProperties` objet. Par exemple :

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Puis-je ajouter des propriétés personnalisées de différents types de données ?

Oui, vous pouvez ajouter des propriétés personnalisées pour différents types de données, notamment des nombres, des chaînes, des dates, etc., comme illustré dans l'exemple. Aspose.Slides pour Java gère différents types de données de manière transparente.

### Existe-t-il une limite au nombre de propriétés personnalisées que je peux ajouter ?

Il n'y a pas de limite stricte au nombre de propriétés personnalisées que vous pouvez ajouter. Cependant, gardez à l'esprit qu'un nombre excessif de propriétés peut affecter les performances et la taille de votre fichier de présentation.

### Comment puis-je répertorier toutes les propriétés personnalisées dans une présentation ?

Vous pouvez parcourir toutes les propriétés personnalisées pour les lister. Voici un exemple :

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Ce code affichera les noms et les valeurs de toutes les propriétés personnalisées dans la présentation.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Accéder aux propriétés intégrées dans PowerPoint
linktitle: Accéder aux propriétés intégrées dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment accéder aux propriétés intégrées dans PowerPoint à l'aide d'Aspose.Slides pour Java. Ce didacticiel vous guide dans la récupération de l'auteur, de la date de création, etc.
weight: 10
url: /fr/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans ce didacticiel, nous verrons comment accéder aux propriétés intégrées dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Aspose.Slides est une bibliothèque puissante qui permet aux développeurs Java de travailler avec des présentations PowerPoint par programme, permettant ainsi des tâches telles que la lecture et la modification de propriétés de manière transparente.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez le télécharger depuis[ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides pour Java : téléchargez et installez Aspose.Slides pour Java à partir de[ce lien](https://releases.aspose.com/slides/java/).

## Importer des packages
Tout d’abord, vous devez importer les packages nécessaires dans votre projet Java. Ajoutez l'instruction d'importation suivante au début de votre fichier Java :
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Étape 1 : configurer l'objet de présentation
Commencez par configurer l'objet Présentation pour représenter la présentation PowerPoint avec laquelle vous souhaitez travailler. Voici comment procéder :
```java
// Le chemin d'accès au répertoire contenant le fichier de présentation
String dataDir = "path_to_your_presentation_directory/";
// Instancier la classe Présentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Étape 2 : accéder aux propriétés du document
Après avoir configuré l'objet Présentation, vous pouvez accéder aux propriétés intégrées de la présentation à l'aide de l'interface IDocumentProperties. Voici comment récupérer diverses propriétés :
### Catégorie
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Statut actuel
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Date de création
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Auteur
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Description
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Mots clés
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Dernière modification par
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Superviseur
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Date modifiée
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Format de présentation
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Date de la dernière impression
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Partagé entre producteurs
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Sujet
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Titre
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Conclusion
Dans ce didacticiel, nous avons appris comment accéder aux propriétés intégrées dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. En suivant les étapes décrites ci-dessus, vous pouvez facilement récupérer diverses propriétés telles que l'auteur, la date de création et le titre par programme.
## FAQ
### Puis-je modifier ces propriétés intégrées à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez modifier ces propriétés à l'aide d'Aspose.Slides. Utilisez simplement les méthodes de définition appropriées fournies par l'interface IDocumentProperties.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Aspose.Slides prend en charge une large gamme de versions de PowerPoint, garantissant la compatibilité sur diverses plates-formes.
### Puis-je également récupérer des propriétés personnalisées ?
Oui, outre les propriétés intégrées, vous pouvez également récupérer et modifier des propriétés personnalisées à l'aide d'Aspose.Slides pour Java.
### Aspose.Slides propose-t-il de la documentation et une assistance ?
 Oui, vous pouvez trouver une documentation complète et accéder aux forums d'assistance sur le[Site Aspose](https://reference.aspose.com/slides/java/).
### Existe-t-il une version d’essai disponible pour Aspose.Slides pour Java ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

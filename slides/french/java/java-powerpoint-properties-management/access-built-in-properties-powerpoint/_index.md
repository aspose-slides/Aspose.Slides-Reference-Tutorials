---
"description": "Découvrez comment accéder aux propriétés intégrées de PowerPoint avec Aspose.Slides pour Java. Ce tutoriel vous guide pour récupérer l'auteur, la date de création, etc."
"linktitle": "Accéder aux propriétés intégrées dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Accéder aux propriétés intégrées dans PowerPoint"
"url": "/fr/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Accéder aux propriétés intégrées dans PowerPoint

## Introduction
Dans ce tutoriel, nous découvrirons comment accéder aux propriétés intégrées des présentations PowerPoint avec Aspose.Slides pour Java. Aspose.Slides est une bibliothèque puissante qui permet aux développeurs Java de travailler avec des présentations PowerPoint par programmation, permettant ainsi des tâches telles que la lecture et la modification de propriétés en toute transparence.
## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : Assurez-vous que le JDK est installé sur votre système. Vous pouvez le télécharger ici. [ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides pour Java : téléchargez et installez Aspose.Slides pour Java depuis [ce lien](https://releases.aspose.com/slides/java/).

## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires dans votre projet Java. Ajoutez l'instruction d'importation suivante au début de votre fichier Java :
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Étape 1 : Configurer l'objet de présentation
Commencez par configurer l'objet Présentation pour représenter la présentation PowerPoint que vous souhaitez utiliser. Voici comment procéder :
```java
// Le chemin d'accès au répertoire contenant le fichier de présentation
String dataDir = "path_to_your_presentation_directory/";
// Instancier la classe Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Étape 2 : Accéder aux propriétés du document
Après avoir configuré l'objet Présentation, vous pouvez accéder aux propriétés intégrées de la présentation via l'interface IDocumentProperties. Voici comment récupérer différentes propriétés :
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
### Mots-clés
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
### Date de modification
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
### Partagé entre les producteurs
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
Dans ce tutoriel, nous avons appris à accéder aux propriétés intégrées des présentations PowerPoint avec Aspose.Slides pour Java. En suivant les étapes décrites ci-dessus, vous pouvez facilement récupérer par programmation diverses propriétés telles que l'auteur, la date de création et le titre.
## FAQ
### Puis-je modifier ces propriétés intégrées à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez modifier ces propriétés avec Aspose.Slides. Utilisez simplement les méthodes de définition appropriées fournies par l'interface IDocumentProperties.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Aspose.Slides prend en charge une large gamme de versions de PowerPoint, garantissant ainsi la compatibilité sur différentes plates-formes.
### Puis-je également récupérer des propriétés personnalisées ?
Oui, en plus des propriétés intégrées, vous pouvez également récupérer et modifier des propriétés personnalisées à l'aide d'Aspose.Slides pour Java.
### Aspose.Slides propose-t-il de la documentation et du support ?
Oui, vous pouvez trouver une documentation complète et accéder aux forums d'assistance sur le [Site Web d'Aspose](https://reference.aspose.com/slides/java/).
### Existe-t-il une version d'essai disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ici](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
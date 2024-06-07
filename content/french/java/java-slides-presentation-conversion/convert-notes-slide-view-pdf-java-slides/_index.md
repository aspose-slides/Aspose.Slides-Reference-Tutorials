---
title: Convertir la vue diapositive Notes en PDF dans les diapositives Java
linktitle: Convertir la vue diapositive Notes en PDF dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment convertir des présentations PowerPoint avec des notes en PDF à l'aide d'Aspose.Slides pour Java. Suivez notre guide étape par étape avec le code source.
type: docs
weight: 16
url: /fr/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## Introduction à la conversion de la vue diapositive Notes en PDF dans les diapositives Java

Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'une présentation PowerPoint avec une vue diapositive de notes en PDF à l'aide de la bibliothèque Aspose.Slides pour Java. Cette bibliothèque fournit des fonctionnalités puissantes pour travailler avec des présentations PowerPoint en Java.

## Conditions préalables
1. Kit de développement Java (JDK) installé.
2. Bibliothèque Aspose.Slides pour Java ajoutée à votre projet.

## Étape 1 : Importer les classes nécessaires
Pour commencer, vous devrez importer les classes nécessaires depuis la bibliothèque Aspose.Slides. Voici le code pour faire cela :

```java
import com.aspose.slides.*;
```

## Étape 2 : Charger la présentation PowerPoint
 Vous devriez avoir votre fichier de présentation PowerPoint prêt. Remplacer`"Your Document Directory"` avec le chemin d'accès au répertoire où se trouve votre fichier de présentation. Voici le code pour charger la présentation :

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Étape 3 : Configurer les options PDF
Maintenant, configurons les options d'exportation PDF. Plus précisément, nous définirons la position des notes sur « BottomFull » pour inclure des notes sous les diapositives du PDF. Voici le code :

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Vous pouvez personnaliser d'autres options PDF en fonction de vos besoins.

## Étape 4 : Enregistrez la présentation au format PDF avec des notes
Enfin, enregistrons la présentation sous forme de fichier PDF, y compris les notes. Vous pouvez spécifier le nom du fichier de sortie (par exemple,`"Pdf_Notes_out.pdf"`) et choisissez le format (`SaveFormat.Pdf`). Voici le code pour faire cela :

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Étape 5 : Nettoyer les ressources
N'oubliez pas de libérer les ressources une fois que vous avez terminé la présentation :

```java
if (presentation != null) presentation.dispose();
```

## Code source complet pour convertir la vue diapositive Notes en PDF dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier un objet Présentation qui représente un fichier de présentation
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Enregistrer la présentation dans des notes PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons exploré comment convertir des présentations PowerPoint avec des vues de diapositives de notes en PDF à l'aide de la bibliothèque Aspose.Slides pour Java. Nous avons suivi un guide étape par étape avec le code source pour réaliser cette conversion. Voici les principaux points à retenir :

## FAQ

### Comment modifier la position des notes dans le PDF ?

 Vous pouvez changer la position des notes dans le PDF en modifiant le`setNotesPosition` argument de méthode. Par exemple, vous pouvez le définir sur`NotesPositions.RightFull` pour positionner les notes sur le côté droit des diapositives.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Puis-je personnaliser davantage l’exportation PDF ?

Oui, vous pouvez personnaliser l'exportation PDF en ajustant diverses options dans le`PdfOptions` objet. Par exemple, vous pouvez définir la qualité, la compression et d'autres paramètres en fonction de vos besoins.

### Comment puis-je obtenir Aspose.Slides pour Java ?

 Vous pouvez télécharger Aspose.Slides pour Java à partir du site Web à l'adresse[ici](https://releases.aspose.com/slides/java/).

### Existe-t-il des exigences de licence pour utiliser Aspose.Slides ?

Oui, Aspose.Slides nécessite une licence valide pour une utilisation commerciale. Vous pouvez obtenir une licence sur le site Web Aspose.

### Où puis-je trouver plus de documentation et d'exemples ?

 Vous pouvez trouver une documentation complète et des exemples pour Aspose.Slides pour Java sur[ici](https://reference.aspose.com/slides/java/).
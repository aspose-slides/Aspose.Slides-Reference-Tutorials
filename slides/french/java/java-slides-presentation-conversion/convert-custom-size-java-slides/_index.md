---
title: Convertir avec une taille personnalisée dans les diapositives Java
linktitle: Convertir avec une taille personnalisée dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment convertir des présentations PowerPoint en images TIFF avec une taille personnalisée à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec des exemples de code pour les développeurs.
weight: 31
url: /fr/java/presentation-conversion/convert-custom-size-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction à la conversion avec une taille personnalisée dans les diapositives Java

Dans cet article, nous allons explorer comment convertir des présentations PowerPoint en images TIFF avec une taille personnalisée à l'aide de l'API Aspose.Slides pour Java. Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PowerPoint par programme. Nous procéderons étape par étape et vous fournirons le code Java nécessaire pour accomplir cette tâche.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Kit de développement Java (JDK) installé
- Aspose.Slides pour la bibliothèque Java

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour Java à partir du site Web :[Télécharger Aspose.Slides pour Java](https://releases.aspose.com/slides/java/)

## Étape 1 : Importer la bibliothèque Aspose.Slides

Pour commencer, vous devez importer la bibliothèque Aspose.Slides dans votre projet Java. Voici comment procéder :

```java
// Ajoutez la déclaration d'importation nécessaire
import com.aspose.slides.*;
```

## Étape 2 : Charger la présentation PowerPoint

 Ensuite, vous devrez charger la présentation PowerPoint que vous souhaitez convertir en image TIFF. Remplacer`"Your Document Directory"` avec le chemin réel vers votre fichier de présentation.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Instancier un objet Présentation qui représente un fichier Présentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Étape 3 : Définir les options de conversion TIFF

Maintenant, définissons les options de conversion TIFF. Nous spécifierons le type de compression, le DPI (points par pouce), la taille de l'image et la position des notes. Vous pouvez personnaliser ces options selon vos besoins.

```java
// Instancier la classe TiffOptions
TiffOptions opts = new TiffOptions();

// Définition du type de compression
opts.setCompressionType(TiffCompressionTypes.Default);

// Définition du DPI de l'image
opts.setDpiX(200);
opts.setDpiY(100);

// Définir la taille de l'image
opts.setImageSize(new Dimension(1728, 1078));

// Définir la position des notes
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Étape 4 : Enregistrer au format TIFF

Une fois toutes les options configurées, vous pouvez désormais enregistrer la présentation sous forme d'image TIFF avec les paramètres spécifiés.

```java
// Enregistrez la présentation au format TIFF avec la taille d'image spécifiée
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Code source complet pour la conversion avec une taille personnalisée dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier un objet Présentation qui représente un fichier Présentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Instancier la classe TiffOptions
	TiffOptions opts = new TiffOptions();
	// Définition du type de compression
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Types de compression
	// Par défaut - Spécifie le schéma de compression par défaut (LZW).
	// Aucun - Spécifie aucune compression.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// La profondeur dépend du type de compression et ne peut pas être définie manuellement.
	// L'unité de résolution est toujours égale à « 2 » (points par pouce)
	// Définition du DPI de l'image
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Définir la taille de l'image
	opts.setImageSize(new Dimension(1728, 1078));
	// Enregistrez la présentation au format TIFF avec la taille d'image spécifiée
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Toutes nos félicitations! Vous avez converti avec succès une présentation PowerPoint en image TIFF avec une taille personnalisée à l'aide d'Aspose.Slides pour Java. Cela peut s'avérer une fonctionnalité précieuse lorsque vous devez générer des images de haute qualité à partir de vos présentations à diverses fins.

## FAQ

### Comment puis-je modifier le type de compression de l'image TIFF ?

 Vous pouvez changer le type de compression en modifiant le`setCompressionType` méthode dans le`TiffOptions` classe. Il existe différents types de compression disponibles, tels que Par défaut, Aucun, CCITT3, CCITT4, LZW et RLE.

### Puis-je ajuster le DPI (points par pouce) de l’image TIFF ?

Oui, vous pouvez ajuster le DPI en utilisant le`setDpiX` et`setDpiY` méthodes dans le`TiffOptions` classe. Définissez simplement les valeurs souhaitées pour contrôler la résolution de l’image.

### Quelles sont les options disponibles pour la position des notes dans l'image TIFF ?

 La position des notes dans l'image TIFF peut être configurée à l'aide du`setNotesPosition` méthode avec des options telles que BottomFull, BottomTruncated et SlideOnly. Choisissez celui qui correspond le mieux à vos besoins.

### Est-il possible de spécifier une taille d'image personnalisée pour la conversion TIFF ?

 Absolument! Vous pouvez définir une taille d'image personnalisée en utilisant le`setImageSize` méthode dans le`TiffOptions` classe. Fournissez les dimensions (largeur et hauteur) souhaitées pour l’image de sortie.

### Où puis-je trouver plus d’informations sur Aspose.Slides pour Java ?

 Pour une documentation détaillée et des informations supplémentaires sur Aspose.Slides pour Java, veuillez visiter la documentation :[Référence de l'API Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

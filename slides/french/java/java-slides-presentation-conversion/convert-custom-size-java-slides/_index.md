---
"description": "Apprenez à convertir des présentations PowerPoint en images TIFF avec une taille personnalisée grâce à Aspose.Slides pour Java. Guide étape par étape avec exemples de code pour les développeurs."
"linktitle": "Convertir avec une taille personnalisée dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Convertir avec une taille personnalisée dans les diapositives Java"
"url": "/fr/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir avec une taille personnalisée dans les diapositives Java


## Introduction à la conversion avec une taille personnalisée dans les diapositives Java

Dans cet article, nous allons découvrir comment convertir des présentations PowerPoint en images TIFF avec une taille personnalisée grâce à l'API Aspose.Slides pour Java. Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PowerPoint par programmation. Nous vous fournirons étape par étape le code Java nécessaire pour réaliser cette tâche.

## Prérequis

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Kit de développement Java (JDK) installé
- Bibliothèque Aspose.Slides pour Java

Vous pouvez télécharger la bibliothèque Aspose.Slides pour Java à partir du site Web : [Télécharger Aspose.Slides pour Java](https://releases.aspose.com/slides/java/)

## Étape 1 : Importer la bibliothèque Aspose.Slides

Pour commencer, vous devez importer la bibliothèque Aspose.Slides dans votre projet Java. Voici comment procéder :

```java
// Ajoutez la déclaration d'importation nécessaire
import com.aspose.slides.*;
```

## Étape 2 : Charger la présentation PowerPoint

Ensuite, vous devrez charger la présentation PowerPoint que vous souhaitez convertir en image TIFF. Remplacer `"Your Document Directory"` avec le chemin réel vers votre fichier de présentation.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";

// Instancier un objet Presentation qui représente un fichier Presentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Étape 3 : définir les options de conversion TIFF

Définissons maintenant les options de conversion TIFF. Nous allons spécifier le type de compression, la résolution (DPI), la taille de l'image et la position des notes. Vous pouvez personnaliser ces options selon vos besoins.

```java
// Instancier la classe TiffOptions
TiffOptions opts = new TiffOptions();

// Définition du type de compression
opts.setCompressionType(TiffCompressionTypes.Default);

// Réglage du DPI de l'image
opts.setDpiX(200);
opts.setDpiY(100);

// Définir la taille de l'image
opts.setImageSize(new Dimension(1728, 1078));

// Définir la position des notes
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Étape 4 : Enregistrer au format TIFF

Une fois toutes les options configurées, vous pouvez désormais enregistrer la présentation sous forme d’image TIFF avec les paramètres spécifiés.

```java
// Enregistrez la présentation au format TIFF avec la taille d'image spécifiée
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Code source complet pour la conversion avec une taille personnalisée dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier un objet Presentation qui représente un fichier Presentation
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
	// Aucun - Ne spécifie aucune compression.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// La profondeur dépend du type de compression et ne peut pas être définie manuellement.
	// L'unité de résolution est toujours égale à « 2 » (points par pouce)
	// Réglage du DPI de l'image
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

Félicitations ! Vous avez réussi à convertir une présentation PowerPoint en image TIFF avec une taille personnalisée grâce à Aspose.Slides pour Java. Cette fonctionnalité peut s'avérer utile pour générer des images de haute qualité à partir de vos présentations, à diverses fins.

## FAQ

### Comment puis-je modifier le type de compression de l'image TIFF ?

Vous pouvez modifier le type de compression en modifiant le `setCompressionType` méthode dans le `TiffOptions` classe. Différents types de compression sont disponibles, tels que Par défaut, Aucun, CCITT3, CCITT4, LZW et RLE.

### Puis-je ajuster le DPI (points par pouce) de l'image TIFF ?

Oui, vous pouvez régler le DPI en utilisant le `setDpiX` et `setDpiY` méthodes dans le `TiffOptions` classe. Définissez simplement les valeurs souhaitées pour contrôler la résolution de l'image.

### Quelles sont les options disponibles pour la position des notes dans l'image TIFF ?

La position des notes dans l'image TIFF peut être configurée à l'aide du `setNotesPosition` Méthode avec des options comme BottomFull, BottomTruncated et SlideOnly. Choisissez celle qui correspond le mieux à vos besoins.

### Est-il possible de spécifier une taille d'image personnalisée pour la conversion TIFF ?

Absolument ! Vous pouvez définir une taille d'image personnalisée en utilisant le `setImageSize` méthode dans le `TiffOptions` classe. Fournissez les dimensions (largeur et hauteur) que vous souhaitez pour l'image de sortie.

### Où puis-je trouver plus d'informations sur Aspose.Slides pour Java ?

Pour une documentation détaillée et des informations supplémentaires sur Aspose.Slides pour Java, veuillez consulter la documentation : [Référence de l'API Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Découvrez comment enrichir vos présentations PowerPoint avec des contrôles ActiveX grâce à Aspose.Slides pour .NET. Notre guide étape par étape couvre l'insertion, la manipulation, la personnalisation, la gestion des événements, et bien plus encore."
"linktitle": "Gérer le contrôle ActiveX dans PowerPoint"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Gérer le contrôle ActiveX dans PowerPoint"
"url": "/fr/net/slide-view-and-layout-manipulation/manage-activex-control/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gérer le contrôle ActiveX dans PowerPoint

Les contrôles ActiveX sont des éléments puissants qui améliorent la fonctionnalité et l'interactivité de vos présentations PowerPoint. Ils vous permettent d'intégrer et de manipuler des objets tels que des lecteurs multimédias, des formulaires de saisie de données, etc., directement dans vos diapositives. Dans cet article, nous découvrirons comment gérer les contrôles ActiveX dans PowerPoint grâce à Aspose.Slides pour .NET, une bibliothèque polyvalente qui permet une intégration et une manipulation fluides des fichiers PowerPoint dans vos applications .NET.

## Ajout de contrôles ActiveX aux diapositives PowerPoint

Pour commencer à intégrer des contrôles ActiveX dans vos présentations PowerPoint, suivez ces étapes :

1. Créer une présentation PowerPoint : Commencez par créer une présentation PowerPoint avec Aspose.Slides pour .NET. Vous pouvez vous référer à la section [Référence de l'API Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/) pour obtenir des conseils sur la façon de travailler avec des présentations.

2. Ajouter une diapositive : utilisez la bibliothèque pour ajouter une nouvelle diapositive à votre présentation. Il s'agira de la diapositive où vous souhaitez insérer le contrôle ActiveX.

3. Insérer le contrôle ActiveX : Il est maintenant temps d'insérer le contrôle ActiveX dans la diapositive. Pour ce faire, suivez l'exemple de code ci-dessous :

```csharp
// Charger la présentation
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Obtenez la diapositive où vous souhaitez insérer le contrôle ActiveX
ISlide slide = presentation.Slides[0];

// Définir les propriétés du contrôle ActiveX
int left = 100; // Spécifiez la position de gauche
int top = 100; // Spécifiez la position supérieure
int width = 200; // Spécifiez la largeur
int height = 100; // Spécifiez la hauteur
string progId = "YourActiveXControl.ProgID"; // Spécifiez le ProgID du contrôle ActiveX

// Ajoutez le contrôle ActiveX à la diapositive
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

Assurez-vous de remplacer `"YourActiveXControl.ProgID"` avec le ProgID réel du contrôle ActiveX que vous souhaitez insérer.

4. Enregistrer la présentation : après avoir inséré le contrôle ActiveX, enregistrez la présentation à l'aide du code suivant :

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Manipulation des contrôles ActiveX par programmation

Une fois le contrôle ActiveX ajouté à votre diapositive, vous souhaiterez peut-être le manipuler par programmation. Voici comment procéder :

1. Accéder au contrôle ActiveX : Pour accéder aux propriétés et méthodes du contrôle ActiveX, vous devez obtenir une référence à celui-ci. Utilisez le code suivant pour obtenir le contrôle depuis la diapositive :

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Méthodes d'appel : Vous pouvez appeler les méthodes du contrôle ActiveX à l'aide de la référence obtenue. Par exemple, si le contrôle ActiveX possède une méthode appelée « Play », vous pouvez l'appeler ainsi :

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Définir les propriétés : Vous pouvez également définir les propriétés du contrôle ActiveX par programmation. Par exemple, si le contrôle possède une propriété appelée « Volume », vous pouvez la définir comme suit :

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Personnalisation des propriétés du contrôle ActiveX

Personnaliser les propriétés de votre contrôle ActiveX peut grandement améliorer l'expérience utilisateur de votre présentation. Voici comment personnaliser ces propriétés :

1. Accéder aux propriétés : Comme mentionné précédemment, vous pouvez accéder aux propriétés du contrôle ActiveX à l'aide de l' `IOleObjectFrame` référence.

2. Définir les propriétés : utilisez le `SetProperty` Méthode permettant de définir diverses propriétés du contrôle ActiveX. Par exemple, vous pouvez modifier la couleur d'arrière-plan comme suit :

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Gestion des événements associés aux contrôles ActiveX

Les contrôles ActiveX sont souvent associés à des événements qui peuvent déclencher des actions en fonction des interactions de l'utilisateur. Voici comment gérer ces événements :

1. S'abonner aux événements : Commencez par vous abonner à l'événement souhaité du contrôle ActiveX. Par exemple, si le contrôle possède un événement « Clic », vous pouvez vous y abonner comme suit :

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Votre code de gestion d'événement ici
};
```

## Suppression des contrôles ActiveX des diapositives

Si vous souhaitez supprimer un contrôle ActiveX d’une diapositive, procédez comme suit :

1. Accéder au contrôle : obtenir une référence au contrôle ActiveX à l'aide de l' `IOleObjectFrame` référence comme indiqué précédemment.

2. Supprimer le contrôle : utilisez le code suivant pour supprimer le contrôle de la diapositive :

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## Enregistrement et exportation de la présentation modifiée

Après avoir apporté toutes les modifications nécessaires à votre présentation, vous pouvez l'enregistrer et l'exporter à l'aide du code suivant :

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Avantages de l'utilisation d'Aspose.Slides pour .NET

Aspose.Slides pour .NET simplifie l'utilisation des contrôles ActiveX dans les présentations PowerPoint grâce à une API conviviale permettant une intégration et une manipulation fluides de ces contrôles. Parmi les avantages d'Aspose.Slides pour .NET, on peut citer :

- Insertion facile de contrôles ActiveX sur les diapositives.
- Méthodes complètes pour interagir par programmation avec les contrôles.
- Personnalisation simplifiée des propriétés de contrôle.
- Gestion efficace des événements pour des présentations interactives.
- Suppression simplifiée des contrôles des diapositives.

## Conclusion

L'intégration de contrôles ActiveX dans vos présentations PowerPoint peut améliorer l'interactivité et l'engagement de votre public. Avec Aspose.Slides pour .NET, vous disposez d'un outil puissant pour gérer facilement les contrôles ActiveX et créer des présentations dynamiques et captivantes qui marqueront les esprits.

## FAQ

### Comment puis-je ajouter un contrôle ActiveX à une diapositive spécifique ?

Pour ajouter un contrôle ActiveX à une diapositive spécifique, vous pouvez utiliser le `AddOleObjectFrame` Méthode fournie par Aspose.Slides pour .NET. Cette méthode permet de spécifier la position, la taille et le ProgID du contrôle ActiveX à insérer.

### Puis-je manipuler les contrôles ActiveX par programmation ?

Oui, vous pouvez manipuler les contrôles ActiveX par programmation avec Aspose.Slides pour .NET. En obtenant une référence à `IOleObjectFrame` en représentant le contrôle, vous pouvez appeler des méthodes et définir des propriétés pour interagir avec le contrôle de manière dynamique.

### Comment gérer les événements

 déclenché par les contrôles ActiveX ?

Vous pouvez gérer les événements déclenchés par les contrôles ActiveX en vous abonnant aux événements correspondants à l'aide de l' `EventClick` Gestionnaire d'événements (ou similaire). Il permet d'exécuter des actions spécifiques en réponse aux interactions de l'utilisateur avec le contrôle.

### Est-il possible de personnaliser l’apparence des contrôles ActiveX ?

Absolument, vous pouvez personnaliser l’apparence des contrôles ActiveX à l’aide du `SetProperty` Méthode fournie par Aspose.Slides pour .NET. Cette méthode permet de modifier diverses propriétés, telles que la couleur d'arrière-plan, le style de police, etc.

### Puis-je supprimer un contrôle ActiveX d’une diapositive ?

Oui, vous pouvez supprimer un contrôle ActiveX d'une diapositive à l'aide de l' `Remove` méthode de la `Shapes` collection. Transmettez la référence à la `IOleObjectFrame` représentant le contrôle comme un argument du `Remove` méthode et le contrôle sera supprimé de la diapositive.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Gérer le contrôle ActiveX dans PowerPoint
linktitle: Gérer le contrôle ActiveX dans PowerPoint
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer les présentations PowerPoint avec des contrôles ActiveX à l'aide d'Aspose.Slides pour .NET. Notre guide étape par étape couvre l'insertion, la manipulation, la personnalisation, la gestion des événements, etc.
type: docs
weight: 13
url: /fr/net/slide-view-and-layout-manipulation/manage-activex-control/
---
Les contrôles ActiveX sont des éléments puissants qui peuvent améliorer la fonctionnalité et l'interactivité de vos présentations PowerPoint. Ces contrôles vous permettent d'intégrer et de manipuler des objets tels que des lecteurs multimédias, des formulaires de saisie de données et plus directement dans vos diapositives. Dans cet article, nous explorerons comment gérer les contrôles ActiveX dans PowerPoint à l'aide d'Aspose.Slides for .NET, une bibliothèque polyvalente qui permet une intégration et une manipulation transparentes des fichiers PowerPoint dans vos applications .NET.

## Ajout de contrôles ActiveX aux diapositives PowerPoint

Pour commencer à intégrer des contrôles ActiveX dans vos présentations PowerPoint, procédez comme suit :

1.  Créer une nouvelle présentation PowerPoint : Tout d'abord, créez une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides pour .NET. Vous pouvez vous référer au[Aspose.Slides pour la référence de l'API .NET](https://reference.aspose.com/slides/net/) pour obtenir des conseils sur la façon de travailler avec des présentations.

2. Ajouter une diapositive : utilisez la bibliothèque pour ajouter une nouvelle diapositive à votre présentation. Ce sera la diapositive dans laquelle vous souhaitez insérer le contrôle ActiveX.

3. Insérez le contrôle ActiveX : Il est maintenant temps d'insérer le contrôle ActiveX sur la diapositive. Vous pouvez y parvenir en suivant l'exemple de code ci-dessous :

```csharp
// Charger la présentation
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Obtenez la diapositive où vous souhaitez insérer le contrôle ActiveX
ISlide slide = presentation.Slides[0];

// Définir les propriétés du contrôle ActiveX
int left = 100; // Préciser la position gauche
int top = 100; // Spécifiez la première position
int width = 200; // Spécifiez la largeur
int height = 100; // Précisez la hauteur
string progId = "YourActiveXControl.ProgID"; // Spécifiez le ProgID du contrôle ActiveX

// Ajouter le contrôle ActiveX à la diapositive
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

 Assurez-vous de remplacer`"YourActiveXControl.ProgID"` avec le ProgID réel du contrôle ActiveX que vous souhaitez insérer.

4. Enregistrez la présentation : Après avoir inséré le contrôle ActiveX, enregistrez la présentation à l'aide du code suivant :

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Manipulation des contrôles ActiveX par programme

Une fois que vous avez ajouté le contrôle ActiveX à votre diapositive, vous souhaiterez peut-être le manipuler par programme. Voici comment procéder :

1. Accéder au contrôle ActiveX : Pour accéder aux propriétés et méthodes du contrôle ActiveX, vous devrez en obtenir une référence. Utilisez le code suivant pour obtenir le contrôle de la diapositive :

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Invoquer des méthodes : vous pouvez appeler des méthodes du contrôle ActiveX à l'aide de la référence obtenue. Par exemple, si le contrôle ActiveX possède une méthode appelée « Play », vous pouvez l'appeler comme ceci :

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Définir les propriétés : vous pouvez également définir les propriétés du contrôle ActiveX par programme. Par exemple, si le contrôle possède une propriété appelée « Volume », vous pouvez la définir comme ceci :

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Personnalisation des propriétés du contrôle ActiveX

La personnalisation des propriétés de votre contrôle ActiveX peut grandement améliorer l'expérience utilisateur de votre présentation. Voici comment personnaliser ces propriétés :

1.  Accéder aux propriétés : comme mentionné précédemment, vous pouvez accéder aux propriétés du contrôle ActiveX à l'aide du`IOleObjectFrame` référence.

2.  Définir les propriétés : utilisez le`SetProperty`méthode pour définir diverses propriétés du contrôle ActiveX. Par exemple, vous pouvez modifier la couleur d'arrière-plan comme ceci :

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Gestion des événements associés aux contrôles ActiveX

Les contrôles ActiveX sont souvent associés à des événements qui peuvent déclencher des actions basées sur les interactions de l'utilisateur. Voici comment gérer ces événements :

1. S'abonner aux événements : Tout d'abord, abonnez-vous à l'événement souhaité du contrôle ActiveX. Par exemple, si le contrôle possède un événement « Clicé », vous pouvez vous y abonner comme ceci :

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Votre code de gestion des événements ici
};
```

## Suppression des contrôles ActiveX des diapositives

Si vous souhaitez supprimer un contrôle ActiveX d'une diapositive, procédez comme suit :

1.  Accéder au contrôle : obtenez une référence au contrôle ActiveX à l'aide du`IOleObjectFrame` référence comme indiqué précédemment.

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

Aspose.Slides pour .NET simplifie le processus d'utilisation des contrôles ActiveX dans les présentations PowerPoint en fournissant une API conviviale qui vous permet d'intégrer et de manipuler ces contrôles de manière transparente. Certains avantages de l’utilisation d’Aspose.Slides pour .NET incluent :

- Insertion facile des contrôles ActiveX sur les diapositives.
- Méthodes complètes pour interagir par programmation avec les contrôles.
- Personnalisation simplifiée des propriétés de contrôle.
- Gestion efficace des événements pour les présentations interactives.
- Suppression simplifiée des contrôles des diapositives.

## Conclusion

L'intégration de contrôles ActiveX dans vos présentations PowerPoint peut augmenter le niveau d'interactivité et d'engagement de votre public. Avec Aspose.Slides pour .NET, vous disposez d'un outil puissant pour gérer de manière transparente les contrôles ActiveX, vous permettant de créer des présentations dynamiques et captivantes qui laissent une impression durable.

## FAQ

### Comment puis-je ajouter un contrôle ActiveX à une diapositive spécifique ?

 Pour ajouter un contrôle ActiveX à une diapositive spécifique, vous pouvez utiliser le`AddOleObjectFrame` méthode fournie par Aspose.Slides pour .NET. Cette méthode vous permet de spécifier la position, la taille et le ProgID du contrôle ActiveX que vous souhaitez insérer.

### Puis-je manipuler les contrôles ActiveX par programme ?

 Oui, vous pouvez manipuler les contrôles ActiveX par programme à l'aide d'Aspose.Slides pour .NET. En obtenant une référence au`IOleObjectFrame` représentant le contrôle, vous pouvez appeler des méthodes et définir des propriétés pour interagir dynamiquement avec le contrôle.

### Comment gérer les événements

 déclenché par les contrôles ActiveX ?

Vous pouvez gérer les événements déclenchés par les contrôles ActiveX en vous abonnant aux événements correspondants à l'aide du`EventClick` (ou similaire) gestionnaire d’événements. Cela vous permet d'exécuter des actions spécifiques en réponse aux interactions de l'utilisateur avec le contrôle.

### Est-il possible de personnaliser l’apparence des contrôles ActiveX ?

 Absolument, vous pouvez personnaliser l'apparence des contrôles ActiveX à l'aide de l'outil`SetProperty` méthode fournie par Aspose.Slides pour .NET. Cette méthode vous permet de modifier diverses propriétés, telles que la couleur d'arrière-plan, le style de police, etc.

### Puis-je supprimer un contrôle ActiveX d’une diapositive ?

 Oui, vous pouvez supprimer un contrôle ActiveX d'une diapositive à l'aide de l'outil`Remove` méthode du`Shapes` collection. Passez la référence au`IOleObjectFrame` représentant le contrôle comme argument au`Remove` méthode et le contrôle sera supprimé de la diapositive.
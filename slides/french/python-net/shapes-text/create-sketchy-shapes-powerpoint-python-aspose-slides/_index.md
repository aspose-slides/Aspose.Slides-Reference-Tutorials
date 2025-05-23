---
"date": "2025-04-23"
"description": "Apprenez à ajouter une touche artistique unique à vos présentations PowerPoint en créant des formes esquissées avec Python et Aspose.Slides. Idéal pour enrichir vos récits créatifs et vos supports pédagogiques."
"title": "Comment créer des formes esquissées dans PowerPoint avec Python et Aspose.Slides"
"url": "/fr/python-net/shapes-text/create-sketchy-shapes-powerpoint-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des formes esquissées dans PowerPoint avec Python et Aspose.Slides

## Introduction

Envie d'insuffler de la créativité à vos présentations PowerPoint ? L'ajout de formes dessinées à la main peut transformer l'apparence de vos diapositives, les rendant plus attrayantes et personnalisées. Ce tutoriel vous guidera dans leur utilisation. **Aspose.Slides pour Python** pour créer sans effort ces effets artistiques.

### Ce que vous apprendrez
- Configuration d'Aspose.Slides dans un environnement Python
- Ajout de rectangles de forme automatique avec des effets d'esquisse
- Enregistrer votre présentation aux formats PNG et PPTX
- Comprendre les options de formatage des lignes

Avant de commencer à créer ces formes esquissées, assurons-nous que vous disposez des prérequis nécessaires.

## Prérequis

### Bibliothèques, versions et dépendances requises
Pour suivre ce tutoriel, assurez-vous d'avoir :
- Python (version 3.6 ou ultérieure recommandée)
- Bibliothèque Aspose.Slides pour Python
- Compréhension de base de la programmation Python

Assurez-vous que votre environnement de développement est configuré avec ces composants.

## Configuration d'Aspose.Slides pour Python

### Installation
Commencez par installer le **Aspose.Slides** bibliothèque utilisant pip :
```bash
pip install aspose.slides
```

### Étapes d'acquisition de licence
Vous pouvez essayer Aspose.Slides gratuitement. Pour bénéficier de fonctionnalités étendues, envisagez d'acquérir une licence temporaire ou une licence complète :
- Essai gratuit : [Diapositives Aspose pour la version Python](https://releases.aspose.com/slides/python-net/)
- Licence temporaire : [Acheter une licence temporaire](https://purchase.aspose.com/temporary-license/)
- Achat: [Acheter la licence complète](https://purchase.aspose.com/buy)

### Initialisation et configuration de base
Pour initialiser une présentation, créez une instance de `Presentation`:
```python
import aspose.slides as slides

# Initialiser la présentation
presentation = slides.Presentation()
```

## Guide de mise en œuvre

Maintenant que vous avez installé Aspose.Slides, concentrons-nous sur la création de formes esquissées.

### Créer des formes esquissées dans PowerPoint

#### Aperçu
Cette fonctionnalité vous permet d'ajouter un effet de ligne esquissée aux formes de votre présentation, leur donnant une apparence artistique et dessinée à la main.

#### Ajout d'un rectangle avec un style de ligne griffonnée

##### Étape 1 : Initialiser une nouvelle présentation
Commencez par créer une nouvelle instance de présentation :
```python
with slides.Presentation() as pres:
    # Procéder à l'ajout de formes
```

##### Étape 2 : Ajouter une forme automatique (rectangle)
Insérez une forme rectangulaire dans la première diapositive à l'aide de `add_auto_shape`:
```python
shape = pres.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 20, 20, 300, 150
)
```
Les paramètres spécifient le type de forme et sa position/taille sur la diapositive.

##### Étape 3 : définissez le type de remplissage sur « NO_FILL »
Pour mettre l'accent sur l'effet d'esquisse, supprimez tout remplissage :
```python
shape.fill_format.fill_type = slides.FillType.NO_FILL
```

##### Étape 4 : Appliquer un effet de croquis de ligne griffonnée
Améliorez votre silhouette avec un style de ligne griffonnée :
```python
shape.line_format.sketch_format.sketch_type = slides.LineSketchType.SCRIBBLE
```
Ce paramètre applique l'apparence esquissée au contour de la forme.

##### Étape 5 : Enregistrer au format PNG et PPTX
Exportez d’abord la diapositive sous forme d’image, puis enregistrez-la sous forme de fichier PowerPoint :
```python
pres.slides[0].get_image(4 / 3, 4 / 3).save(
    "YOUR_OUTPUT_DIRECTORY/shapes_sketch_format_out.png",
    slides.ImageFormat.PNG
)
pres.save("YOUR_OUTPUT_DIRECTORY/shapes_sketch_format_out.pptx", 
          slides.export.SaveFormat.PPTX)
```
Remplacer `"YOUR_OUTPUT_DIRECTORY"` avec le chemin de sauvegarde souhaité.

#### Conseils de dépannage
- Assurez-vous que le répertoire de sortie existe et est accessible en écriture.
- Vérifiez les fautes de frappe dans les chemins de fichiers ou les noms de méthodes.

## Applications pratiques
Les formes esquissées peuvent être particulièrement utiles dans :
1. **Présentations éducatives**: Simplifiez les diagrammes complexes pour les rendre plus compréhensibles.
2. **Narration créative**:Améliorez les diapositives narratives avec une sensation unique et dessinée à la main.
3. **Matériel de marketing**:Créez des visuels accrocheurs qui se démarquent.

Ces formes peuvent également s'intégrer de manière transparente dans les flux de travail de conception à l'aide de l'API étendue d'Aspose.Slides.

## Considérations relatives aux performances
Pour des performances optimales :
- Utilisez des structures de données efficaces lors de la gestion de présentations volumineuses.
- Mettez régulièrement à jour la dernière version d'Aspose.Slides pour corriger les bugs et améliorer les performances.
- Gérez efficacement la mémoire en vous débarrassant des objets qui ne sont plus utilisés.

Ces pratiques garantiront un déroulement fluide tout au long du processus de création de votre présentation.

## Conclusion
En suivant ce guide, vous avez appris à créer des formes esquissées à l'aide de **Aspose.Slides pour Python**Expérimentez différents styles de lignes et formes pour trouver celui qui correspond le mieux à vos besoins. À mesure que vous vous familiariserez avec Aspose.Slides, explorez ses nombreuses fonctionnalités pour améliorer vos présentations.

Ensuite, pensez à explorer d’autres fonctionnalités telles que des animations ou des éléments interactifs pour rendre vos diapositives encore plus attrayantes.

## Section FAQ
1. **Quel est l’objectif principal de l’utilisation de formes esquissées dans les présentations ?**
   - Pour ajouter un élément visuel unique et créatif qui capte l’attention.
2. **Comment changer le type de forme d'un rectangle à une autre forme ?**
   - Utiliser `ShapeType` énumération pour spécifier différentes formes comme `ELLIPSE`, `STAR`, etc.
3. **Puis-je également appliquer des effets d’esquisse aux zones de texte ?**
   - Oui, des méthodes similaires peuvent être appliquées à n’importe quelle forme ou objet dans vos diapositives.
4. **Est-il possible de régler l'intensité de l'effet gribouillage ?**
   - Bien qu'aucun contrôle direct sur l'intensité ne soit fourni, expérimenter avec l'épaisseur et la couleur des lignes peut permettre d'obtenir les résultats souhaités.
5. **Comment résoudre les erreurs d’importation pour Aspose.Slides ?**
   - Assurez-vous que vous avez correctement installé la bibliothèque via pip et qu'il n'y a aucune faute de frappe dans votre code.

## Ressources
- [Documentation](https://reference.aspose.com/slides/python-net/)
- [Télécharger la dernière version](https://releases.aspose.com/slides/python-net/)
- [Acheter la licence complète](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/slides/python-net/)
- [Permis temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d'assistance](https://forum.aspose.com/c/slides/11)

Explorez ces ressources pour approfondir votre compréhension et vos capacités avec Aspose.Slides pour Python.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
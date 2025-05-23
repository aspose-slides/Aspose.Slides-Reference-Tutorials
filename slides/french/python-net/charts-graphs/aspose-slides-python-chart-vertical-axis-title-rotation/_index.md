---
"date": "2025-04-23"
"description": "Découvrez comment ajuster l'angle de rotation des titres de graphiques dans les présentations à l'aide d'Aspose.Slides pour Python, améliorant ainsi la lisibilité et l'esthétique."
"title": "Comment définir la rotation du titre de l'axe vertical d'un graphique dans Aspose.Slides pour Python"
"url": "/fr/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment définir la rotation du titre de l'axe vertical d'un graphique dans Aspose.Slides pour Python

## Introduction

Dans les présentations de données, améliorer la lisibilité des graphiques est crucial. Ajuster l'angle de rotation du titre de l'axe vertical de votre graphique avec Aspose.Slides pour Python permet d'optimiser l'affichage ou de mettre en valeur les titres dans vos diapositives. Ce tutoriel vous guide dans le réglage de cet angle de rotation pour améliorer à la fois la fonctionnalité et l'esthétique.

**Ce que vous apprendrez :**
- Comment installer et configurer Aspose.Slides pour Python.
- Étapes pour ajouter et personnaliser des graphiques dans vos diapositives.
- Techniques pour définir l'angle de rotation des titres de graphiques.
- Applications concrètes de ces fonctionnalités dans la visualisation des données.

Commençons par couvrir les prérequis avant de plonger dans la mise en œuvre.

## Prérequis

Avant de commencer, assurez-vous d'avoir :
- **Environnement Python**: Installez Python 3.x à partir de [python.org](https://www.python.org/).
- **Bibliothèque Aspose.Slides**:Installez via pip pour manipuler efficacement les présentations.
- **Connaissances de base de la programmation Python**:La familiarité avec la syntaxe Python et les opérations sur les fichiers vous aidera à suivre.

## Configuration d'Aspose.Slides pour Python

Pour utiliser Aspose.Slides, installez-le avec pip. Ouvrez votre terminal ou votre invite de commande et exécutez :

```bash
pip install aspose.slides
```

### Étapes d'acquisition de licence

Aspose propose différentes options de licence :
- **Essai gratuit**: Téléchargez une version d'essai à partir de [Page de sortie d'Aspose](https://releases.aspose.com/slides/python-net/).
- **Permis temporaire**: Obtenez une licence temporaire pour les fonctionnalités étendues via le [portail d'achat](https://purchase.aspose.com/temporary-license/).
- **Achat**: Pensez à l'acheter si vous trouvez l'outil indispensable, disponible auprès du [Page d'achat Aspose](https://purchase.aspose.com/buy).

#### Initialisation et configuration de base

Voici comment initialiser Aspose.Slides dans votre script Python :

```python
import aspose.slides as slides

# Créer un objet de présentation
def main():
    with slides.Presentation() as pres:
        # Votre code ira ici
        pass

if __name__ == "__main__":
    main()
```

## Guide de mise en œuvre

### Ajout et personnalisation de graphiques

#### Aperçu

Dans cette section, nous allons ajouter un graphique à colonnes groupées à votre diapositive et le personnaliser en définissant l'angle de rotation du titre de son axe vertical.

#### Mesures:

##### Étape 1 : Ajouter un graphique à colonnes groupées

Commencez par ajouter un graphique à des coordonnées spécifiques avec des dimensions définies :

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Ajouter un graphique à colonnes groupées à la diapositive 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Étape 2 : Configurer le titre de l’axe vertical

Activer et définir l'angle de rotation du titre de l'axe vertical :

```python
def configure_chart(chart):
    # Activer le titre de l'axe vertical
    chart.axes.vertical_axis.has_title = True
    
    # Réglez l'angle de rotation à 90 degrés
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Étape 3 : Enregistrez votre présentation

Enfin, enregistrez votre présentation avec les modifications :

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Enregistrer la présentation
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
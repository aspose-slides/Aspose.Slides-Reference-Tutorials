---
"date": "2025-04-23"
"description": "Apprenez à ajouter et supprimer facilement des sous-titres vidéo dans vos présentations PowerPoint avec Aspose.Slides pour Python. Améliorez l'accessibilité et l'engagement de votre public."
"title": "Comment ajouter et supprimer des sous-titres vidéo dans PowerPoint avec Aspose.Slides pour Python"
"url": "/fr/python-net/images-multimedia/aspose-slides-python-add-video-captions-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter et supprimer des sous-titres vidéo dans PowerPoint avec Aspose.Slides pour Python

## Introduction

L'ajout de sous-titres à vos présentations PowerPoint peut grandement améliorer l'accessibilité, notamment pour les publics variés ou ceux qui ont besoin de sous-titres. Avec Aspose.Slides pour Python, vous pouvez facilement intégrer des sous-titres à vos vidéos PowerPoint. Ce tutoriel vous guidera dans l'ajout et la suppression de sous-titres dans vos présentations PowerPoint avec Aspose.Slides.

**Ce que vous apprendrez :**
- Comment ajouter des sous-titres vidéo à partir d'un fichier VTT.
- Techniques d'extraction et de suppression des sous-titres existants.
- Bonnes pratiques pour optimiser les performances avec Aspose.Slides.

Configurons votre environnement et commençons !

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :
- **Environnement Python**:Python 3.6 ou version ultérieure installé sur votre système.
- **Aspose.Slides pour Python**:Installez via pip comme indiqué ci-dessous.
- **Fichiers VTT**: Préparez un fichier VTT pour le sous-titrage et des fichiers vidéo pour les tests.

### Bibliothèques requises
Pour travailler avec Aspose.Slides, vous devrez l'installer à l'aide de pip :

```
pip install aspose.slides
```

#### Acquisition de licence
Vous pouvez obtenir une licence d'essai gratuite sur le site web d'Aspose. Cela vous permettra de tester toutes les fonctionnalités sans limitation. Pour une utilisation à long terme, pensez à acheter une licence ou une licence temporaire.

### Prérequis en matière de connaissances
Une compréhension de base de Python et une familiarité avec les fichiers PowerPoint seront bénéfiques pour suivre efficacement ce guide.

## Configuration d'Aspose.Slides pour Python
Tout d'abord, assurez-vous qu'Aspose.Slides est installé. Si ce n'est pas déjà fait, exécutez la commande d'installation pip :

```bash
pip install aspose.slides
```

#### Initialisation de base
Après avoir installé Aspose.Slides, initialisez-le dans votre script pour commencer à travailler avec des fichiers PowerPoint.

## Guide de mise en œuvre
Nous explorerons deux fonctionnalités principales : l’ajout de sous-titres et leur suppression des vidéos intégrées dans les présentations PowerPoint.

### Ajout de sous-titres à une image vidéo
Cette fonctionnalité vous permet d'améliorer l'accessibilité de votre contenu vidéo en incluant des sous-titres ou des légendes directement dans votre présentation.

#### Étape 1 : Créer et charger une présentation
Commencez par créer un nouvel objet de présentation :

```python
import aspose.slides as slides

def add_video_captions():
    # Créer une nouvelle présentation
    with slides.Presentation() as pres:
        ...
```

#### Étape 2 : ajouter le fichier vidéo
Chargez votre fichier vidéo dans la présentation. Assurez-vous d'avoir le bon chemin d'accès à votre vidéo :

```python
        with open("YOUR_DOCUMENT_DIRECTORY/NewVideo.mp4", "rb") as f:
            video = pres.videos.add_video(f.read())
```

#### Étape 3 : insérer une image vidéo et ajouter des sous-titres
Insérer un `VideoFrame` à la position souhaitée et ajoutez des légendes à l'aide de votre fichier VTT :

```python
        # Ajouter un VideoFrame avec des dimensions spécifiées
        video_frame = pres.slides[0].shapes.add_video_frame(0, 0, 100, 100, video)
        
        # Joindre une piste de légende à partir d'un fichier VTT
        video_frame.caption_tracks.add("New track", "YOUR_DOCUMENT_DIRECTORY/bunny.vtt")
```

#### Étape 4 : Enregistrer la présentation
Enfin, enregistrez votre présentation mise à jour avec les légendes :

```python
        pres.save("YOUR_OUTPUT_DIRECTORY/VideoCaptionsAdd_out.pptx", slides.export.SaveFormat.PPTX)
```

### Extraction et suppression des sous-titres d'une image vidéo
Maintenant que vous avez ajouté des légendes, explorons comment les extraire pour les réviser ou les supprimer complètement.

#### Étape 1 : ouvrir une présentation existante
Commencez par charger la présentation contenant votre vidéo avec les sous-titres :

```python
def extract_and_remove_captions():
    # Charger la présentation existante
    with slides.Presentation("YOUR_OUTPUT_DIRECTORY/VideoCaptionsAdd_out.pptx") as pres:
        ...
```

#### Étape 2 : Extraire les données de sous-titres
Parcourez chaque piste de sous-titres pour enregistrer ses données dans des fichiers VTT :

```python
        video_frame = pres.slides[0].shapes[0]
        if video_frame is not None:
            for idx, caption_track in enumerate(video_frame.caption_tracks):
                with open(f"YOUR_OUTPUT_DIRECTORY/VideoCaption_out_{idx}.vtt", "wb") as f:
                    f.write(caption_track.binary_data)
```

#### Étape 3 : supprimer les sous-titres
Effacer toutes les sous-titres de l'image vidéo :

```python
            # Effacer toutes les pistes de sous-titres
            video_frame.caption_tracks.clear()
            
            # Enregistrer les modifications dans un nouveau fichier
            pres.save("YOUR_OUTPUT_DIRECTORY/VideoCaptionsRemove_out.pptx", slides.export.SaveFormat.PPTX)
```

## Applications pratiques
L'ajout et la suppression de sous-titres peuvent s'avérer très utiles dans divers scénarios :
- **Contenu éducatif**: Améliorer l’accessibilité pour les étudiants malentendants.
- **Présentations d'entreprise**:Assurer une communication claire lors des réunions mondiales où existent des barrières linguistiques.
- **Campagnes marketing**:Fournir un contenu inclusif à un public plus large.

L'intégration d'Aspose.Slides avec d'autres systèmes peut rationaliser ces processus, améliorant ainsi l'efficacité et la portée.

## Considérations relatives aux performances
Pour des performances optimales lorsque vous travaillez avec des sous-titres vidéo :
- **Gestion des ressources**: Assurez-vous que votre système dispose de ressources suffisantes pour gérer des présentations volumineuses.
- **Optimisation de la mémoire**:Utilisez des techniques efficaces de gestion de la mémoire en Python pour gérer efficacement de grands ensembles de données.

## Conclusion
En suivant ce guide, vous maîtriserez désormais l'ajout et la suppression de sous-titres vidéo dans PowerPoint avec Aspose.Slides pour Python. Poursuivez votre exploration en expérimentant différents formats vidéo ou en intégrant cette fonctionnalité à des projets plus vastes.

### Prochaines étapes
Explorez les autres fonctionnalités d'Aspose.Slides pour améliorer encore vos présentations. Rejoignez la communauté sur les forums pour obtenir du soutien et partager vos expériences !

## Section FAQ
**Q : Que faire si mon fichier VTT n’est pas reconnu ?**
A : Assurez-vous que le chemin est correct et que le format VTT est conforme aux spécifications.

**Q : Puis-je ajouter plusieurs pistes de sous-titres simultanément ?**
R : Oui, Aspose.Slides prend en charge l’ajout de plusieurs pistes de sous-titres à une seule image vidéo.

**Q : Comment gérer efficacement les grandes présentations ?**
A : Pensez à décomposer les tâches ou à optimiser votre environnement Python pour une meilleure gestion des ressources.

## Ressources
- **Documentation**: [Documentation des diapositives Aspose](https://reference.aspose.com/slides/python-net/)
- **Télécharger**: [Diapositives d'Aspose publiées](https://releases.aspose.com/slides/python-net/)
- **Achat**: [Acheter des diapositives Aspose](https://purchase.aspose.com/buy)
- **Essai gratuit**: [Essayez Aspose Slides gratuitement](https://releases.aspose.com/slides/python-net/)
- **Permis temporaire**: [Obtenir un permis temporaire](https://purchase.aspose.com/temporary-license/)
- **Soutien**: [Forum Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-23"
"description": "Apprenez à configurer vos présentations PowerPoint en lecture seule et à compter les diapositives par programmation avec Aspose.Slides pour Python. Idéal pour le partage sécurisé de documents et la création de rapports automatisés."
"title": "Configurer PowerPoint en lecture seule et compter les diapositives avec Python à l'aide d'Aspose.Slides"
"url": "/fr/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Configurer PowerPoint en lecture seule et compter les diapositives avec Python

## Introduction
Avez-vous déjà été confronté au défi de distribuer une présentation sans la modifier ? Ou peut-être souhaitiez-vous vérifier facilement le nombre de diapositives de votre présentation sans l'ouvrir ? **Aspose.Slides pour Python**Ces tâches deviennent simples. Ce tutoriel vous guidera dans la configuration de vos présentations PowerPoint en lecture seule et le comptage des diapositives avec Aspose.Slides, offrant une solution robuste pour gérer vos fichiers PowerPoint par programmation.

**Ce que vous apprendrez :**
- Comment définir la protection en écriture sur une présentation PowerPoint.
- Comment enregistrer un fichier PowerPoint avec des restrictions de lecture seule.
- Comment charger une présentation et compter le nombre de diapositives efficacement.

Voyons comment vous pouvez réaliser ces tâches de manière transparente en Python.

## Prérequis
Avant de commencer, assurez-vous d’avoir :
- **Python 3.6+** installé sur votre système.
- Accès à une interface de ligne de commande pour l'installation de packages.

Vous devrez également installer Aspose.Slides pour Python. Cette puissante bibliothèque permet une manipulation avancée des fichiers PowerPoint directement depuis votre environnement Python. Bien que la version gratuite offre des fonctionnalités limitées, l'acquisition d'une licence (par essai gratuit ou achat) étend considérablement ses possibilités.

## Configuration d'Aspose.Slides pour Python
Pour commencer à utiliser Aspose.Slides en Python, vous devez d'abord l'installer. Voici comment :

### Installation de pip
Exécutez la commande suivante dans votre terminal ou invite de commande :

```bash
pip install aspose.slides
```

Cela téléchargera et installera la dernière version d'Aspose.Slides pour Python.

### Étapes d'acquisition de licence
1. **Essai gratuit**: Commencez par un essai gratuit pour explorer les fonctionnalités de base.
2. **Permis temporaire**: Obtenez une licence temporaire pour débloquer toutes les fonctionnalités pendant votre période d'évaluation.
3. **Achat**:Envisagez d’acheter une licence pour un accès et une assistance continus.

Une fois que vous avez votre fichier de licence, chargez-le dans votre script comme ceci :

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## Guide de mise en œuvre
Dans cette section, nous allons décomposer l'implémentation en deux fonctionnalités principales : définir une présentation en lecture seule et compter les diapositives.

### Fonctionnalité 1 : Enregistrer la présentation en lecture seule
#### Aperçu
Cette fonctionnalité permet de protéger un fichier PowerPoint en écriture, empêchant toute modification sans mot de passe. Elle est particulièrement utile pour distribuer des présentations qui ne doivent pas être modifiées par le destinataire.

#### Mesures
##### Étape 1 : instancier un objet de présentation
Commencez par créer un `Presentation` objet. Ceci représente votre fichier PPT en Python.

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
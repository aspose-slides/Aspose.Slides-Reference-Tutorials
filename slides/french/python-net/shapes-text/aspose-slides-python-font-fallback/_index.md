---
"date": "2025-04-24"
"description": "Apprenez à créer et à gérer des règles de secours de police avec Aspose.Slides pour Python pour garantir que vos présentations sont cohérentes sur différents systèmes."
"title": "Maîtriser les polices de secours dans Aspose.Slides pour Python &#58; un guide complet"
"url": "/fr/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser la gestion des polices de secours dans Aspose.Slides pour Python : un guide complet

## Introduction

Les problèmes de compatibilité des polices peuvent être difficiles lors de la création de présentations, en particulier avec les caractères Unicode non pris en charge par les polices principales. **Aspose.Slides pour Python** fournit une solution robuste grâce à des règles de repli de police, garantissant l'attrait visuel et la lisibilité de votre présentation sur différents systèmes.

Dans ce guide, nous découvrirons comment créer et gérer des règles de remplacement de polices avec Aspose.Slides pour Python. Vous apprendrez :
- Configurer votre environnement avec Aspose.Slides
- Création d'une collection de règles de secours pour les polices
- Gérer ces règles en ajoutant ou en supprimant des polices en fonction des plages Unicode
- Application des règles aux présentations et rendu des diapositives sous forme d'images

Commençons par préparer votre environnement.

## Prérequis

Assurez-vous que votre environnement est prêt pour cette tâche. Voici ce dont vous aurez besoin :
1. **Aspose.Slides pour Python**: Cette bibliothèque gère les règles de secours des polices.
2. **Environnement Python**: Assurez-vous que Python (version 3.6 ou ultérieure) est installé.
3. **Connaissances de base en Python**:La familiarité avec la syntaxe et les concepts Python sera utile lorsque nous nous plongerons dans des extraits de code.

## Configuration d'Aspose.Slides pour Python

### Installation

Pour commencer, installez la bibliothèque Aspose.Slides à l'aide de pip :

```bash
pip install aspose.slides
```

### Acquisition de licence

Aspose propose une licence d'essai gratuite pour explorer ses fonctionnalités sans limites. Voici comment l'obtenir :
- Visite [Page d'achat d'Aspose](https://purchase.aspose.com/buy) pour acheter des options ou accéder à une licence temporaire.
- Vous pouvez également télécharger une version d'essai gratuite à partir du [Section Téléchargements](https://releases.aspose.com/slides/python-net/).

### Initialisation de base

Une fois installé, initialisez Aspose.Slides dans votre script Python :

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Guide de mise en œuvre

### Création et gestion des règles de secours des polices

#### Aperçu

Les règles de secours en matière de police garantissent que tous les caractères de votre présentation ont une police appropriée, préservant ainsi la lisibilité pour les langues avec des jeux de caractères uniques.

#### Étapes de mise en œuvre

**1. Créer une collection de règles de secours pour les polices**

Commencez par créer une collection pour définir les polices de secours :

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Ajouter une règle de secours pour les polices**

Définissez une règle spécifiant la plage Unicode et la police de secours :

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Paramètres**: `0x400` est le début de la gamme Unicode, `0x4FF` c'est la fin, et `"Times New Roman"` est la police de secours.

**3. Gérer les règles existantes**

Parcourez chaque règle pour les modifier selon vos besoins :

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Supprimer une règle**

Si nécessaire, supprimez la première règle de votre collection :

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Application des règles de repli des polices à une présentation et rendu d'une image

#### Aperçu

Une fois les règles de secours des polices configurées, appliquez-les aux présentations pour garantir que le texte utilise les polices de secours spécifiées lorsque cela est nécessaire.

#### Étapes de mise en œuvre

**1. Initialisez votre environnement**

Préparez les répertoires pour l'entrée et la sortie :

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Appliquer des règles de secours à une présentation**

Chargez votre fichier de présentation et appliquez les règles de police :

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-22"
"description": "Apprenez à modifier le texte des zones de texte, les légendes des boutons et les images dans PowerPoint avec Aspose.Slides et Python. Améliorez vos présentations avec des éléments interactifs."
"title": "Maîtrisez Aspose.Slides pour Python et modifiez facilement les contrôles ActiveX de PowerPoint"
"url": "/fr/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser Aspose.Slides pour Python : Modification des contrôles ActiveX PowerPoint

Dans le paysage numérique dynamique d'aujourd'hui, la personnalisation des présentations Microsoft PowerPoint est essentielle pour créer du contenu attrayant. Que vous développiez des modules de formation interactifs ou que vous amélioriez vos présentations professionnelles avec des fonctionnalités de saisie utilisateur, la modification des contrôles ActiveX PowerPoint peut considérablement améliorer les fonctionnalités de votre présentation. Ce tutoriel explore l'utilisation d'Aspose.Slides pour Python pour modifier le texte des zones de texte et les légendes des boutons, remplacer des images, repositionner ou supprimer des contrôles ActiveX des diapositives.

## Ce que vous apprendrez
- Comment modifier le texte de la zone de texte et les légendes des boutons dans les présentations PowerPoint.
- Techniques de substitution d'images dans les contrôles ActiveX.
- Méthodes pour repositionner ou supprimer efficacement les contrôles ActiveX.
- Applications pratiques de ces fonctionnalités dans des scénarios réels.

Avant de plonger dans Aspose.Slides pour Python, passons en revue les prérequis.

## Prérequis
Pour suivre ce tutoriel, assurez-vous d'avoir :
- **Python**:Version 3.6 ou supérieure installée sur votre système.
- **Aspose.Slides pour Python via .NET**:Cela peut être installé en utilisant pip.
- Une compréhension de base de la programmation Python et une familiarité avec la structure de PowerPoint.

### Configuration requise pour l'environnement
1. **Installer Aspose.Slides**:
   Utilisez la commande suivante pour installer Aspose.Slides pour Python via .NET :

   ```bash
   pip install aspose.slides
   ```

2. **Acquisition de licence**: 
   Commencez par obtenir un [licence d'essai gratuite](https://releases.aspose.com/slides/python-net/) ou demandez une licence temporaire pour explorer toutes les fonctionnalités sans limitations.

3. **Initialisation de base**:
   Importez les modules nécessaires et chargez votre document PowerPoint comme indiqué ci-dessous :

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # Votre code ira ici.
   ```

## Guide de mise en œuvre
### Fonctionnalité : modifier le texte de la zone de texte et remplacer l'image
#### Aperçu
Cette fonctionnalité vous permet de mettre à jour le texte dans un contrôle ActiveX TextBox et de remplacer son image associée, utile pour personnaliser les présentations ou mettre à jour dynamiquement le contenu.

##### Guide étape par étape
1. **Charger la présentation**:
   Commencez par charger votre présentation PowerPoint contenant les contrôles ActiveX.

   ```python
def change_textbox_and_image():
    avec slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") comme présentation :
        diapositive = présentation.slides[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **Créer une image de remplacement**:
   Générer une image pour remplacer le contenu d'origine lors de l'activation ActiveX.

   ```python
            import aspose.pydrawing as drawing

            # Créer une image avec des dimensions spécifiées
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # Ajoutez des lignes de bordure pour un look soigné
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Fonctionnalité : Modifier la légende du bouton et remplacer l'image
#### Aperçu
Mettez à jour les légendes des boutons dans les contrôles ActiveX de votre présentation, offrant ainsi des possibilités d'interaction utilisateur dynamiques.

##### Guide étape par étape
1. **Charger la présentation**:
   Comme précédemment, commencez par charger le fichier PowerPoint.

   ```python
def change_button_caption_and_image():
    avec slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") comme présentation :
        diapositive = présentation.slides[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **Créer une image de remplacement**:
   Générer une image pour le remplacement visuel.

   ```python
            # Créer une image bitmap pour les dimensions du bouton
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # Ajoutez des lignes de bordure pour l'esthétique
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Fonctionnalité : Déplacer les contrôles ActiveX vers le bas et enregistrer la présentation
#### Aperçu
Découvrez comment repositionner les contrôles ActiveX dans une diapositive, améliorant ainsi la flexibilité de la mise en page.

##### Guide étape par étape
1. **Charger la présentation**:
   Ouvrez votre document PowerPoint pour le modifier.

   ```python
def move_active_x_controls_and_save() :
    avec slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") comme présentation :
        diapositive = présentation.slides[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**Conclusion:**
En suivant ce guide, vous pourrez modifier efficacement les contrôles ActiveX de PowerPoint avec Aspose.Slides pour Python. Cela améliorera l'interactivité et la personnalisation de vos présentations, les rendant plus attrayantes pour votre public.

## Recommandations de mots clés
- « Modifier les contrôles ActiveX de PowerPoint »
- « Aspose.Slides pour Python »
- « Modifier le texte de la zone de texte dans PowerPoint »
- « Remplacer les images dans les contrôles ActiveX »

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
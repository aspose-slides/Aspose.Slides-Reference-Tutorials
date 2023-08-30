---
title: Applying 3D Rotation Effect on Shapes in Presentation Slides with Aspose.Slides
linktitle: Applying 3D Rotation Effect on Shapes in Presentation Slides with Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to apply captivating 3D rotation effects to presentation slides using Aspose.Slides for .NET. Step-by-step guide with source code for stunning visual impact.
type: docs
weight: 23
url: /net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

Imagine giving your presentation a stunning visual impact by adding dynamic 3D rotation effects to shapes. With Aspose.Slides for .NET, you can easily achieve this captivating effect and make your slides stand out. In this tutorial, we will guide you through the process of applying 3D rotation effects to shapes in presentation slides step by step. We will provide you with the source code and explain each step in detail. Let's dive in!

## Introduction to 3D Rotation Effects

3D rotation effects add depth and realism to your presentation slides. They allow you to make shapes appear as if they are rotating in three-dimensional space, creating an engaging visual experience for your audience.

## Setting Up Your Development Environment

Before we begin, make sure you have Aspose.Slides for .NET installed in your project. You can download it from [here](https://releases.aspose.com/slides/net/).

## Creating a Presentation

To get started, let's create a new presentation:

```csharp
// Initialize a presentation
Presentation presentation = new Presentation();
```

## Adding Shapes to Slides

Now, let's add some shapes to our slides:

```csharp
// Access the first slide
ISlide slide = presentation.Slides[0];

// Add a rectangle shape
IShape shape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```

## Applying 3D Rotation Effect

To apply a 3D rotation effect to the shape, use the following code:

```csharp
// Apply 3D rotation effect to the shape
shape.ThreeDFormat.RotationX = 30;
shape.ThreeDFormat.RotationY = 45;
```

## Adjusting Rotation Angle and Perspective

You can adjust the rotation angle and perspective to achieve the desired effect:

```csharp
// Adjust rotation angle and perspective
shape.ThreeDFormat.RotationX = 60;
shape.ThreeDFormat.RotationY = 30;
shape.ThreeDFormat.PresetCamera.PresetType = CameraPresetType.OrthographicFront;
```

## Fine-tuning Rotation Settings

For more precise control, you can fine-tune rotation settings:

```csharp
// Fine-tune rotation settings
shape.ThreeDFormat.RotationX = 45;
shape.ThreeDFormat.RotationY = 15;
shape.ThreeDFormat.RotationZ = 10;
```

## Adding Animation (Optional)

To add animation to the rotation effect:

```csharp
// Add animation to the rotation effect
ITransition transition = slide.SlideShowTransition;
transition.AdvanceOnTime = true;
transition.AdvanceTime = 2; // seconds
```

## Saving and Exporting Your Presentation

After applying the 3D rotation effect and any other desired adjustments, save and export your presentation:

```csharp
// Save and export presentation
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Conclusion

Congratulations! You've successfully learned how to apply 3D rotation effects to shapes in presentation slides using Aspose.Slides for .NET. This technique can greatly enhance the visual appeal of your presentations and keep your audience engaged.

## FAQs

### How can I adjust the rotation speed of the animation?

You can adjust the rotation speed by modifying the `AdvanceTime` property in the transition settings.

### Can I apply 3D rotation to text boxes?

Yes, you can apply 3D rotation effects to text boxes or any other shapes in your presentation.

### Is Aspose.Slides compatible with different PowerPoint versions?

Yes, Aspose.Slides is compatible with various PowerPoint versions and allows you to create presentations that can be opened and viewed by different PowerPoint software.

### Can I apply multiple 3D effects to a single shape?

Yes, you can combine multiple 3D effects, such as rotation, depth, and lighting, to create complex visual effects for your shapes.

### Does Aspose.Slides provide support for other types of animations?

Yes, Aspose.Slides offers a wide range of animation effects that you can apply to your presentation slides to make them more dynamic and engaging.
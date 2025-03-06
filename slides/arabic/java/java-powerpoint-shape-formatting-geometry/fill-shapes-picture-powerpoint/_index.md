---
title: ملء الأشكال مع الصورة في PowerPoint
linktitle: ملء الأشكال مع الصورة في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية ملء الأشكال بالصور في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تعزيز الجاذبية البصرية دون عناء.
weight: 12
url: /ar/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ملء الأشكال مع الصورة في PowerPoint

## مقدمة
غالبًا ما تتطلب عروض PowerPoint التقديمية عناصر مرئية مثل الأشكال المملوءة بالصور لتعزيز جاذبيتها ونقل المعلومات بشكل فعال. يوفر Aspose.Slides for Java مجموعة قوية من الأدوات لإنجاز هذه المهمة بسلاسة. في هذا البرنامج التعليمي، سنتعلم كيفية ملء الأشكال بالصور باستخدام Aspose.Slides لـ Java خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل Aspose.Slides لمكتبة Java. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/slides/java/).
3. المعرفة الأساسية ببرمجة جافا.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم الضرورية:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: إعداد دليل المشروع
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 تأكد من الاستبدال`"Your Document Directory"` مع المسار إلى دليل المشروع الخاص بك.
## الخطوة 2: إنشاء عرض تقديمي
```java
Presentation pres = new Presentation();
```
 إنشاء مثيل`Presentation` فئة لإنشاء عرض تقديمي جديد ل PowerPoint.
## الخطوة 3: إضافة شريحة وشكل
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
أضف شريحة إلى العرض التقديمي وقم بإنشاء شكل مستطيل عليها.
## الخطوة 4: اضبط نوع التعبئة على الصورة
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
اضبط نوع تعبئة الشكل على الصورة.
## الخطوة 5: ضبط وضع تعبئة الصورة
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
ضبط وضع تعبئة الصورة للشكل.
## الخطوة 6: تعيين الصورة
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
قم بتحميل الصورة وقم بتعيينها كتعبئة للشكل.
## الخطوة 7: حفظ العرض التقديمي
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدل في ملف.

## خاتمة
باستخدام Aspose.Slides for Java، يصبح ملء الأشكال بالصور في عروض PowerPoint التقديمية عملية مباشرة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة تحسين عروضك التقديمية باستخدام عناصر جذابة بصريًا.

## الأسئلة الشائعة
### هل يمكنني ملء أشكال مختلفة بالصور باستخدام Aspose.Slides لـ Java؟
نعم، يدعم Aspose.Slides for Java ملء الأشكال المختلفة بالصور، مما يوفر مرونة في التصميم.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يقوم Aspose.Slides for Java بإنشاء عروض تقديمية متوافقة مع PowerPoint 97 والإصدارات الأحدث، مما يضمن التوافق الواسع.
### كيف يمكنني تغيير حجم الصورة داخل الشكل؟
يمكنك تغيير حجم الصورة داخل الشكل عن طريق ضبط أبعاد الشكل أو تغيير حجم الصورة وفقًا لذلك قبل تعيينها كتعبئة.
### هل هناك أي قيود على تنسيقات الصور المدعومة لملء الأشكال؟
يدعم Aspose.Slides for Java مجموعة واسعة من تنسيقات الصور، بما في ذلك JPEG وPNG وGIF وBMP وTIFF وغيرها.
### هل يمكنني تطبيق التأثيرات على الأشكال المملوءة؟
نعم، يوفر Aspose.Slides for Java واجهات برمجة تطبيقات شاملة لتطبيق تأثيرات متنوعة، مثل الظلال والانعكاسات والتدوير ثلاثي الأبعاد، على الأشكال المعبأة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

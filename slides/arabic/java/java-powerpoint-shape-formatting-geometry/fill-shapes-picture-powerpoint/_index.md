---
"description": "تعلّم كيفية ملء الأشكال بالصور في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. حسّن مظهرك بسهولة."
"linktitle": "ملء الأشكال بالصور في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ملء الأشكال بالصور في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ملء الأشكال بالصور في PowerPoint

## مقدمة
غالبًا ما تتطلب عروض PowerPoint التقديمية عناصر بصرية، مثل الأشكال المملوءة بالصور، لتعزيز جاذبيتها وعرض المعلومات بفعالية. يوفر Aspose.Slides لـ Java مجموعة أدوات فعّالة لإنجاز هذه المهمة بسلاسة. في هذا البرنامج التعليمي، سنتعلم كيفية ملء الأشكال بالصور باستخدام Aspose.Slides لـ Java خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2. تم تنزيل مكتبة Aspose.Slides لجافا. يمكنك الحصول عليها من [هنا](https://releases.aspose.com/slides/java/).
3. المعرفة الأساسية ببرمجة جافا.
## استيراد الحزم
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
تأكد من الاستبدال `"Your Document Directory"` مع المسار إلى دليل المشروع الخاص بك.
## الخطوة 2: إنشاء عرض تقديمي
```java
Presentation pres = new Presentation();
```
إنشاء مثيل `Presentation` فئة لإنشاء عرض تقديمي جديد في PowerPoint.
## الخطوة 3: إضافة شريحة وشكل
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
أضف شريحة إلى العرض التقديمي وقم بإنشاء شكل مستطيل عليها.
## الخطوة 4: تعيين نوع التعبئة إلى صورة
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
تعيين نوع التعبئة للشكل إلى صورة.
## الخطوة 5: ضبط وضع تعبئة الصورة
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
ضبط وضع ملء الصورة للشكل.
## الخطوة 6: تعيين الصورة
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
قم بتحميل الصورة وتعيينها كملء للشكل.
## الخطوة 7: حفظ العرض التقديمي
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدّل في ملف.

## خاتمة
مع Aspose.Slides لجافا، أصبح ملء الأشكال بالصور في عروض PowerPoint التقديمية عملية سهلة وبسيطة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة تحسين عروضك التقديمية بعناصر جذابة بصريًا.

## الأسئلة الشائعة
### هل يمكنني ملء أشكال مختلفة بالصور باستخدام Aspose.Slides لـ Java؟
نعم، يدعم Aspose.Slides for Java ملء الأشكال المختلفة بالصور، مما يوفر المرونة في التصميم.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يُنشئ Aspose.Slides for Java عروض تقديمية متوافقة مع PowerPoint 97 والإصدارات الأحدث، مما يضمن التوافق الواسع.
### كيف يمكنني تغيير حجم الصورة داخل الشكل؟
يمكنك تغيير حجم الصورة داخل الشكل عن طريق ضبط أبعاد الشكل أو تغيير مقياس الصورة وفقًا لذلك قبل تعيينها كملء.
### هل هناك أي قيود على تنسيقات الصور المدعومة لملء الأشكال؟
يدعم Aspose.Slides for Java مجموعة واسعة من تنسيقات الصور، بما في ذلك JPEG، PNG، GIF، BMP، وTIFF، وغيرها.
### هل يمكنني تطبيق التأثيرات على الأشكال المملوءة؟
نعم، يوفر Aspose.Slides for Java واجهات برمجة تطبيقات شاملة لتطبيق تأثيرات مختلفة، مثل الظلال والانعكاسات والدوران ثلاثي الأبعاد، على الأشكال المملوءة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
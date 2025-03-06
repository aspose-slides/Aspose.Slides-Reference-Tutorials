---
title: قم بتعيين تنسيق تعبئة التعداد النقطي في SmartArt باستخدام Java
linktitle: قم بتعيين تنسيق تعبئة التعداد النقطي في SmartArt باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين تنسيق تعبئة التعداد النقطي في SmartArt باستخدام Java باستخدام Aspose.Slides. دليل خطوة بخطوة لمعالجة العرض التقديمي بكفاءة.
type: docs
weight: 18
url: /ar/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## مقدمة
في عالم برمجة Java، يعد التعامل الفعال مع العروض التقديمية متطلبًا شائعًا، خاصة عند التعامل مع عناصر SmartArt. يظهر Aspose.Slides for Java كأداة قوية لمثل هذه المهام، حيث يقدم مجموعة من الوظائف للتعامل مع العروض التقديمية برمجيًا. في هذا البرنامج التعليمي، سنتعمق في عملية إعداد تنسيق تعبئة التعداد النقطي في SmartArt باستخدام Java مع Aspose.Slides، خطوة بخطوة.
## المتطلبات الأساسية
قبل الشروع في هذا البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
### مجموعة تطوير جافا (JDK)
 تحتاج إلى تثبيت JDK على نظامك. يمكنك تنزيله من[موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) واتبع تعليمات التثبيت.
### Aspose.Slides لجافا
 قم بتنزيل وتثبيت Aspose.Slides لـ Java من[رابط التحميل](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المتوفرة في الوثائق الخاصة بنظام التشغيل الخاص بك.

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#دعنا نقسم المثال المقدم إلى خطوات متعددة للحصول على فهم واضح لكيفية تعيين تنسيق تعبئة التعداد النقطي في SmartArt باستخدام Java مع Aspose.Slides.
## الخطوة 1: إنشاء كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
أولاً، قم بإنشاء مثيل جديد لفئة العرض التقديمي، والذي يمثل عرضًا تقديميًا لـ PowerPoint.
## الخطوة 2: إضافة SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
بعد ذلك، قم بإضافة شكل SmartArt إلى الشريحة. يقوم سطر التعليمات البرمجية هذا بتهيئة شكل SmartArt جديد بأبعاد وتخطيط محددين.
## الخطوة 3: الوصول إلى عقدة SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
الآن، قم بالوصول إلى العقدة الأولى (أو أي عقدة مرغوبة) داخل شكل SmartArt لتعديل خصائصها.
## الخطوة 4: تعيين تنسيق تعبئة التعداد النقطي
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
هنا، نتحقق مما إذا كان تنسيق تعبئة التعداد النقطي مدعومًا. إذا كان الأمر كذلك، فإننا نقوم بتحميل ملف صورة ونقوم بتعيينه كتعبئة نقطية لعقدة SmartArt.
## الخطوة 5: حفظ العرض التقديمي
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
وأخيرًا، احفظ العرض التقديمي المعدل في موقع محدد.

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تعيين تنسيق تعبئة التعداد النقطي في SmartArt باستخدام Java مع Aspose.Slides. تفتح هذه الإمكانية عالمًا من الإمكانيات للعروض التقديمية الديناميكية والجذابة بصريًا في تطبيقات Java.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java لإنشاء عروض تقديمية من البداية؟
قطعاً! يوفر Aspose.Slides واجهات برمجة تطبيقات شاملة لإنشاء العروض التقديمية وتعديلها ومعالجتها بالكامل من خلال التعليمات البرمجية.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يضمن Aspose.Slides التوافق مع الإصدارات المختلفة من Microsoft PowerPoint، مما يتيح التكامل السلس في سير العمل الخاص بك.
### هل يمكنني تخصيص عناصر SmartArt بما يتجاوز تنسيق تعبئة التعداد النقطي؟
في الواقع، يمكّنك Aspose.Slides من تخصيص كل جانب من جوانب أشكال SmartArt، بما في ذلك التخطيط والأسلوب والمحتوى والمزيد.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك استكشاف ميزات Aspose.Slides من خلال النسخة التجريبية المجانية. ما عليك سوى تنزيله من[موقع إلكتروني](https://releases.aspose.com/slides/java/) وابدأ في الاستكشاف.
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
 لأية استفسارات أو مساعدة، يمكنك زيارة منتدى Aspose.Slides على[هذا الرابط](https://forum.aspose.com/c/slides/11).
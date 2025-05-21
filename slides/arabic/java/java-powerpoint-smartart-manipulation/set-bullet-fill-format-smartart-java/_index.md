---
"description": "تعرّف على كيفية ضبط تنسيق تعبئة النقاط في SmartArt باستخدام Java مع Aspose.Slides. دليل خطوة بخطوة لإدارة العروض التقديمية بكفاءة."
"linktitle": "تعيين تنسيق تعبئة النقاط في SmartArt باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين تنسيق تعبئة النقاط في SmartArt باستخدام Java"
"url": "/ar/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين تنسيق تعبئة النقاط في SmartArt باستخدام Java

## مقدمة
في عالم برمجة جافا، يُعدّ التعامل الفعّال مع العروض التقديمية مطلبًا شائعًا، خاصةً عند التعامل مع عناصر SmartArt. تبرز Aspose.Slides for Java كأداة فعّالة لمثل هذه المهام، حيث تُقدّم مجموعةً من الوظائف لإدارة العروض التقديمية برمجيًا. في هذا البرنامج التعليمي، سنتناول بالتفصيل عملية ضبط تنسيق تعبئة النقاط في SmartArt باستخدام جافا مع Aspose.Slides، خطوةً بخطوة.
## المتطلبات الأساسية
قبل أن نبدأ في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
### مجموعة تطوير جافا (JDK)
يجب أن يكون لديك JDK مُثبّتًا على نظامك. يمكنك تنزيله من [موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) واتبع تعليمات التثبيت.
### Aspose.Slides لـ Java
قم بتنزيل Aspose.Slides وتثبيته لـ Java من [رابط التحميل](https://releases.aspose.com/slides/java/)اتبع تعليمات التثبيت الواردة في الوثائق الخاصة بنظام التشغيل الخاص بك.

## استيراد الحزم
للبدء، قم باستيراد الحزم اللازمة إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#دعونا نقسم المثال المقدم إلى خطوات متعددة لفهم واضح لكيفية تعيين تنسيق التعبئة النقطية في SmartArt باستخدام Java مع Aspose.Slides.
## الخطوة 1: إنشاء كائن العرض التقديمي
```java
Presentation presentation = new Presentation();
```
أولاً، قم بإنشاء مثيل جديد لفئة العرض التقديمي، والتي تمثل عرض تقديمي في PowerPoint.
## الخطوة 2: إضافة SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
بعد ذلك، أضف شكل SmartArt إلى الشريحة. يُنشئ هذا السطر من التعليمات البرمجية شكل SmartArt جديدًا بأبعاد وتخطيط محددين.
## الخطوة 3: الوصول إلى عقدة SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
الآن، قم بالوصول إلى العقدة الأولى (أو أي عقدة مرغوبة) داخل شكل SmartArt لتعديل خصائصها.
## الخطوة 4: تعيين تنسيق تعبئة النقاط
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
هنا، نتحقق من دعم تنسيق التعبئة النقطية. إذا كان كذلك، نحمّل ملف صورة ونعيّنه كملء نقطي لعقدة SmartArt.
## الخطوة 5: حفظ العرض التقديمي
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
وأخيرًا، احفظ العرض التقديمي المعدّل في الموقع المحدد.

## خاتمة
تهانينا! لقد نجحت في تعلم كيفية ضبط تنسيق تعبئة النقاط في SmartArt باستخدام جافا مع Aspose.Slides. تتيح لك هذه الميزة عالمًا واسعًا من الإمكانيات لإنشاء عروض تقديمية ديناميكية وجذابة بصريًا في تطبيقات جافا.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java لإنشاء عروض تقديمية من الصفر؟
بالتأكيد! يوفر Aspose.Slides واجهات برمجة تطبيقات شاملة لإنشاء العروض التقديمية وتعديلها ومعالجتها بالكامل من خلال الكود.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يضمن Aspose.Slides التوافق مع الإصدارات المختلفة من Microsoft PowerPoint، مما يتيح التكامل السلس في سير عملك.
### هل يمكنني تخصيص عناصر SmartArt بما يتجاوز تنسيق التعبئة النقطية؟
في الواقع، يتيح لك Aspose.Slides تخصيص كل جانب من جوانب أشكال SmartArt، بما في ذلك التخطيط والأسلوب والمحتوى والمزيد.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك استكشاف ميزات Aspose.Slides من خلال نسخة تجريبية مجانية. ما عليك سوى تنزيله من [موقع إلكتروني](https://releases.aspose.com/slides/java/) وابدأ بالاستكشاف.
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
لأي استفسارات أو مساعدة، يمكنك زيارة منتدى Aspose.Slides على [هذا الرابط](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
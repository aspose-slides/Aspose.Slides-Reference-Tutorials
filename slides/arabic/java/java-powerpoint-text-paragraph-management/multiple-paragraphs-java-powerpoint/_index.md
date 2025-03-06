---
title: فقرات متعددة في جافا باور بوينت
linktitle: فقرات متعددة في جافا باور بوينت
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء فقرات متعددة في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides for Java. دليل كامل مع أمثلة التعليمات البرمجية.
weight: 13
url: /ar/java/java-powerpoint-text-paragraph-management/multiple-paragraphs-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# فقرات متعددة في جافا باور بوينت

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء شرائح تحتوي على فقرات متعددة في Java باستخدام Aspose.Slides for Java. Aspose.Slides هي مكتبة قوية تسمح للمطورين بمعالجة عروض PowerPoint التقديمية برمجياً، مما يجعلها مثالية لأتمتة المهام المتعلقة بإنشاء الشرائح وتنسيقها.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (مجموعة تطوير Java).
- تم تثبيت IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
## حزم الاستيراد
ابدأ باستيراد فئات Aspose.Slides الضرورية إلى ملف Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## الخطوة 1: قم بإعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في IDE المفضل لديك وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة العرض التقديمي
 إنشاء مثيل أ`Presentation` الكائن الذي يمثل ملف PowerPoint:
```java
// المسار إلى الدليل الذي تريد حفظ العرض التقديمي فيه
String dataDir = "Your_Document_Directory/";
// إنشاء مثيل لكائن العرض التقديمي
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وإضافة الأشكال
قم بالوصول إلى الشريحة الأولى من العرض التقديمي وأضف شكل مستطيل (`IAutoShape`) إليها:
```java
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
// إضافة شكل تلقائي (مستطيل) إلى الشريحة
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 300, 150);
```
## الخطوة 4: الوصول إلى TextFrame وإنشاء الفقرات
 الوصول إلى`TextFrame` التابع`AutoShape` وإنشاء فقرات متعددة (`IParagraph`) فى خلال ذلك:
```java
// الوصول إلى TextFrame الخاص بالشكل التلقائي
ITextFrame tf = ashp.getTextFrame();
// إنشاء فقرات وأجزاء بتنسيقات نصية مختلفة
IParagraph para0 = tf.getParagraphs().get_Item(0);
IPortion port01 = new Portion();
IPortion port02 = new Portion();
para0.getPortions().add(port01);
para0.getPortions().add(port02);
// إنشاء فقرات إضافية
IParagraph para1 = new Paragraph();
tf.getParagraphs().add(para1);
IPortion port10 = new Portion();
IPortion port11 = new Portion();
IPortion port12 = new Portion();
para1.getPortions().add(port10);
para1.getPortions().add(port11);
para1.getPortions().add(port12);
IParagraph para2 = new Paragraph();
tf.getParagraphs().add(para2);
IPortion port20 = new Portion();
IPortion port21 = new Portion();
IPortion port22 = new Portion();
para2.getPortions().add(port20);
para2.getPortions().add(port21);
para2.getPortions().add(port22);
```
## الخطوة 5: تنسيق النص والفقرات
قم بتنسيق كل جزء من النص داخل الفقرات:
```java
// قم بالتكرار عبر الفقرات والأجزاء لتعيين النص والتنسيق
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        tf.getParagraphs().get_Item(i).getPortions().get_Item(j).setText("Portion0" + j);
        if (j == 0) {
            // تنسيق الجزء الأول في كل فقرة
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontBold(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(15);
        } else if (j == 1) {
            // تنسيق الجزء الثاني في كل فقرة
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontItalic(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(18);
        }
    }
}
```
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل على القرص:
```java
// احفظ PPTX على القرص
pres.save(dataDir + "multiParaPort_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية استخدام Aspose.Slides لـ Java لإنشاء عروض تقديمية لـ PowerPoint تحتوي على فقرات متعددة برمجيًا. يسمح هذا الأسلوب بإنشاء محتوى ديناميكي وتخصيصه مباشرةً من كود Java.

## الأسئلة الشائعة
### هل يمكنني إضافة المزيد من الفقرات أو تغيير التنسيق لاحقًا؟
نعم، يمكنك إضافة أكبر عدد ممكن من الفقرات وتخصيص التنسيق باستخدام أساليب واجهة برمجة التطبيقات الخاصة بـ Aspose.Slides.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
يمكنك استكشاف المزيد من الأمثلة والوثائق التفصيلية[هنا](https://reference.aspose.com/slides/java/).
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides تنسيقات PowerPoint المختلفة، مما يضمن التوافق عبر الإصدارات المختلفة.
### هل يمكنني تجربة Aspose.Slides مجانًا قبل الشراء؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم الفني إذا لزم الأمر؟
 يمكنك الحصول على الدعم من مجتمع Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

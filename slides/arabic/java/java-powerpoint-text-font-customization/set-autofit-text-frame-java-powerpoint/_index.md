---
title: ضبط الاحتواء التلقائي لإطار النص في Java PowerPoint
linktitle: ضبط الاحتواء التلقائي لإطار النص في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية ضبط الاحتواء التلقائي لإطارات النص في Java PowerPoint باستخدام Aspose.Slides لـ Java. قم بإنشاء عروض تقديمية ديناميكية دون عناء.
weight: 14
url: /ar/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ضبط الاحتواء التلقائي لإطار النص في Java PowerPoint

## مقدمة
في تطوير تطبيقات Java، يعد إنشاء عروض PowerPoint التقديمية الديناميكية والجذابة بصريًا برمجيًا مطلبًا شائعًا. يوفر Aspose.Slides for Java مجموعة قوية من واجهات برمجة التطبيقات لتحقيق ذلك دون عناء. إحدى الميزات الأساسية هي ضبط الاحتواء التلقائي لإطارات النص، مما يضمن ضبط النص بدقة داخل الأشكال دون تعديلات يدوية. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مع الاستفادة من Aspose.Slides لـ Java لأتمتة ملاءمة النص في شرائح PowerPoint.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك
- تم تنزيل Aspose.Slides لمكتبة Java والإشارة إليها في مشروع Java الخاص بك
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse
### حزم الاستيراد
أولاً، تأكد من استيراد فئات Aspose.Slides الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إنشاء عرض تقديمي جديد
ابدأ بإنشاء مثيل عرض تقديمي جديد لـ PowerPoint حيث ستضيف شرائح وأشكالًا.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة لإضافة الأشكال
قم بالوصول إلى الشريحة الأولى من العرض التقديمي حيث تريد إضافة شكل مع نص الاحتواء التلقائي.
```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل تلقائي (مستطيل)
قم بإضافة شكل تلقائي (مستطيل) إلى الشريحة بإحداثيات وأبعاد محددة.
```java
// إضافة شكل تلقائي لنوع المستطيل
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## الخطوة 4: إضافة TextFrame إلى المستطيل
أضف إطار نص إلى الشكل المستطيل.
```java
// أضف TextFrame إلى المستطيل
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## الخطوة 5: ضبط الاحتواء التلقائي لإطار النص
قم بتعيين خصائص الاحتواء التلقائي لإطار النص لضبط النص بناءً على حجم الشكل.
```java
// الوصول إلى إطار النص
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## الخطوة 6: إضافة نص إلى إطار النص
أضف محتوى النص إلى إطار النص داخل الشكل.
```java
// قم بإنشاء كائن الفقرة لإطار النص
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// إنشاء كائن جزء للفقرة
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## الخطوة 7: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل باستخدام إطار نص الاحتواء التلقائي.
```java
// حفظ العرض التقديمي
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية تعيين الاحتواء التلقائي لإطارات النص في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. باتباع هذه الخطوات، يمكنك أتمتة ملاءمة النص داخل الأشكال، مما يعزز سهولة القراءة وجماليات العروض التقديمية الخاصة بك برمجيًا.

## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات Java قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وقراءتها ومعالجتها وتحويلها.
### كيف يمكنني تنزيل Aspose.Slides لنظام Java؟
 يمكنك تنزيل Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـ Java مجانًا؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 يمكنك العثور على وثائق مفصلة عن Aspose.Slides لـ Java[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم المجتمعي والمهني لـ Aspose.Slides for Java من[هنا](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

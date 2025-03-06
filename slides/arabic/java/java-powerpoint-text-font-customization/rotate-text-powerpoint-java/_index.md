---
title: تدوير النص في PowerPoint باستخدام Java
linktitle: تدوير النص في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تدوير النص في PowerPoint باستخدام Java باستخدام Aspose.Slides. برنامج تعليمي خطوة بخطوة للمبتدئين للمستخدمين المتقدمين.
weight: 10
url: /ar/java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تدوير النص في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية تدوير النص في عروض PowerPoint التقديمية برمجياً باستخدام Java وAspose.Slides. يمكن أن يكون تدوير النص ميزة مفيدة عند تصميم الشرائح لإنشاء عروض تقديمية جذابة بصريًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة جافا.
- تم تثبيت JDK على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- تم إعداد IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse على جهازك.
## حزم الاستيراد
أولاً، تحتاج إلى استيراد فئات Aspose.Slides الضرورية للعمل مع ملفات PowerPoint في Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإنشاء مشروع Java جديد في IDE الخاص بك وإضافة ملف Aspose.Slides JAR إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة كائنات العرض التقديمي والشرائح
```java
// المسار إلى الدليل الذي تريد حفظ العرض التقديمي فيه
String dataDir = "Your_Document_Directory/";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// احصل على الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل مستطيل
```java
// إضافة شكل تلقائي لنوع المستطيل
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## الخطوة 4: إضافة نص إلى شكل المستطيل
```java
// أضف TextFrame إلى المستطيل
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
// الوصول إلى إطار النص
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);
```
## الخطوة 5: تعيين محتوى النص والتصميم
```java
// قم بإنشاء كائن الفقرة لإطار النص
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// إنشاء كائن جزء للفقرة
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## الخطوة 6: احفظ العرض التقديمي
```java
// حفظ العرض التقديمي
presentation.save(dataDir + "RotateText_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تدوير النص في عروض PowerPoint التقديمية باستخدام Java وAspose.Slides. باتباع هذه الخطوات، يمكنك معالجة اتجاه النص ديناميكيًا في شرائحك لتحسين التأثير البصري.
## الأسئلة الشائعة
### هل يمكنني تدوير النص إلى أي زاوية في PowerPoint باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تحديد أي زاوية مطلوبة لتدوير النص برمجياً.
### هل يدعم Aspose.Slides خيارات تنسيق النص الأخرى مثل حجم الخط والمحاذاة؟
بالتأكيد، يوفر Aspose.Slides واجهات برمجة تطبيقات شاملة للتعامل مع متطلبات تنسيق النص المختلفة.
### كيف يمكنني البدء باستخدام Aspose.Slides لـ Java؟
 يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides من[هنا](https://releases.aspose.com/) لاستكشاف ميزاته.
### أين يمكنني العثور على مزيد من الوثائق والدعم لـ Aspose.Slides؟
 للحصول على وثائق مفصلة، قم بزيارة[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) . يمكنك أيضًا الحصول على الدعم من المجتمع على[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/)لتقييم Aspose.Slides دون قيود.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

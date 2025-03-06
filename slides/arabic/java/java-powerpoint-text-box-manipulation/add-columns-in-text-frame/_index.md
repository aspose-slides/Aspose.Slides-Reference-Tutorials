---
title: إضافة أعمدة في إطار النص باستخدام Aspose.Slides لـ Java
linktitle: إضافة أعمدة في إطار النص باستخدام Aspose.Slides لـ Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة أعمدة في إطارات النص باستخدام Aspose.Slides for Java لتحسين عروض PowerPoint التقديمية. دليلنا خطوة بخطوة يبسط العملية.
type: docs
weight: 11
url: /ar/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية التعامل مع إطارات النص لإضافة أعمدة باستخدام Aspose.Slides لـ Java. Aspose.Slides هي مكتبة قوية تمكن مطوري Java من إنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً. تعمل إضافة أعمدة إلى إطارات النص على تحسين المظهر المرئي وتنظيم النص داخل الشرائح، مما يجعل العروض التقديمية أكثر جاذبية وأسهل في القراءة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- الفهم الأساسي لبرمجة جافا.
- بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA.
- الإلمام بإدارة تبعيات المشروع باستخدام أدوات مثل Maven أو Gradle.

## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة من Aspose.Slides للعمل مع العروض التقديمية وإطارات النص:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تهيئة العرض التقديمي
ابدأ بإنشاء كائن عرض تقديمي جديد في PowerPoint:
```java
String dataDir = "Your Document Directory";
String outPptxFileName = dataDir + "ColumnsTest.pptx";
// إنشاء كائن عرض تقديمي جديد
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة شكل تلقائي بإطار نص
قم بإضافة شكل تلقائي (على سبيل المثال، مستطيل) إلى الشريحة الأولى وقم بالوصول إلى إطار النص الخاص بها:
```java
// أضف شكلاً تلقائيًا إلى الشريحة الأولى
IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
// قم بالوصول إلى إطار النص الخاص بالشكل التلقائي
TextFrameFormat format = (TextFrameFormat) shape1.getTextFrame().getTextFrameFormat();
```
## الخطوة 3: تعيين عدد الأعمدة والنص
قم بتعيين عدد الأعمدة ومحتوى النص داخل إطار النص:
```java
// ضبط عدد الأعمدة
format.setColumnCount(2);
// ضبط محتوى النص
shape1.getTextFrame().setText("All these columns are limited to be within a single text container -- " +
    "you can add or delete text and the new or remaining text automatically adjusts " +
    "itself to flow within the container. You cannot have text flow from one container " +
    "to other though -- we told you PowerPoint's column options for text are limited!");
```
## الخطوة 4: احفظ العرض التقديمي
احفظ العرض التقديمي بعد إجراء التغييرات:
```java
// احفظ العرض التقديمي
pres.save(outPptxFileName, SaveFormat.Pptx);
```
## الخطوة 5: ضبط تباعد الأعمدة (اختياري)
إذا لزم الأمر، اضبط التباعد بين الأعمدة:
```java
// ضبط تباعد الأعمدة
format.setColumnSpacing(20);
// احفظ العرض التقديمي مع تباعد الأعمدة المحدث
pres.save(outPptxFileName, SaveFormat.Pptx);
// يمكنك تغيير عدد الأعمدة والتباعد مرة أخرى إذا لزم الأمر
format.setColumnCount(3);
format.setColumnSpacing(15);
pres.save(outPptxFileName, SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، أوضحنا كيفية استخدام Aspose.Slides لـ Java لإضافة أعمدة داخل إطارات النص في عروض PowerPoint التقديمية برمجيًا. تعمل هذه الإمكانية على تحسين العرض المرئي لمحتوى النص، وتحسين إمكانية القراءة والبنية في الشرائح.
## الأسئلة الشائعة
### هل يمكنني إضافة أكثر من ثلاثة أعمدة إلى إطار النص؟
 نعم يمكنك ضبط`setColumnCount` طريقة لإضافة المزيد من الأعمدة حسب الحاجة.
### هل يدعم Aspose.Slides ضبط عرض العمود بشكل فردي؟
لا، يقوم Aspose.Slides بتعيين العرض المتساوي للأعمدة داخل إطار النص تلقائيًا.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
 الوثائق التفصيلية متاحة[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides لـ Java؟
 يمكنك طلب الدعم من المجتمع[هنا](https://forum.aspose.com/c/slides/11).
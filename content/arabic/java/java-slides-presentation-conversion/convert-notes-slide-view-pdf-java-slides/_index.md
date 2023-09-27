---
title: تحويل عرض شرائح الملاحظات إلى PDF في شرائح Java
linktitle: تحويل عرض شرائح الملاحظات إلى PDF في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل عروض PowerPoint التقديمية المصحوبة بالملاحظات إلى ملفات PDF باستخدام Aspose.Slides لـ Java. اتبع دليلنا خطوة بخطوة مع الكود المصدري.
type: docs
weight: 16
url: /ar/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## مقدمة لتحويل عرض شرائح الملاحظات إلى PDF في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل عرض تقديمي لـ PowerPoint مع عرض شرائح الملاحظات إلى ملف PDF باستخدام مكتبة Aspose.Slides for Java. توفر هذه المكتبة ميزات قوية للعمل مع عروض PowerPoint التقديمية في Java.

## المتطلبات الأساسية
1. تم تثبيت مجموعة أدوات تطوير Java (JDK).
2. تمت إضافة مكتبة Aspose.Slides لـ Java إلى مشروعك.

## الخطوة 1: استيراد الفئات الضرورية
للبدء، ستحتاج إلى استيراد الفئات الضرورية من مكتبة Aspose.Slides. إليك الكود للقيام بذلك:

```java
import com.aspose.slides.*;
```

## الخطوة 2: قم بتحميل عرض PowerPoint التقديمي
 يجب أن يكون ملف عرض PowerPoint التقديمي جاهزًا. يستبدل`"Your Document Directory"` مع المسار إلى الدليل الذي يوجد به ملف العرض التقديمي الخاص بك. إليك الكود لتحميل العرض التقديمي:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## الخطوة 3: تكوين خيارات PDF
الآن، دعونا نقوم بتكوين خيارات تصدير PDF. على وجه التحديد، سنقوم بتعيين موضع الملاحظات على "BottomFull" لتضمين الملاحظات أسفل الشرائح في ملف PDF. إليك الكود:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

يمكنك تخصيص خيارات PDF الأخرى وفقًا لمتطلباتك.

## الخطوة 4: احفظ العرض التقديمي بصيغة PDF مع الملاحظات
أخيرًا، لنحفظ العرض التقديمي كملف PDF، بما في ذلك الملاحظات. يمكنك تحديد اسم ملف الإخراج (على سبيل المثال،`"Pdf_Notes_out.pdf"`) واختر التنسيق (`SaveFormat.Pdf`). إليك الكود للقيام بذلك:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## الخطوة 5: تنظيف الموارد
لا تنس إصدار الموارد بمجرد الانتهاء من العرض التقديمي:

```java
if (presentation != null) presentation.dispose();
```

## كود المصدر الكامل لتحويل عرض شرائح الملاحظات إلى PDF في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// حفظ العرض التقديمي في ملاحظات PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية تحويل عروض PowerPoint التقديمية مع عروض شرائح الملاحظات إلى ملفات PDF باستخدام مكتبة Aspose.Slides for Java. لقد اتبعنا دليلاً خطوة بخطوة مع الكود المصدري لتحقيق هذا التحويل. فيما يلي الوجبات الرئيسية:

## الأسئلة الشائعة

### كيف أقوم بتغيير موضع الملاحظات في ملف PDF؟

 يمكنك تغيير موضع الملاحظات في ملف PDF عن طريق تعديل`setNotesPosition` حجة الطريقة. على سبيل المثال، يمكنك ضبطه على`NotesPositions.RightFull` لوضع الملاحظات على الجانب الأيمن من الشرائح.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### هل يمكنني تخصيص تصدير PDF بشكل أكبر؟

نعم، يمكنك تخصيص تصدير PDF عن طريق ضبط الخيارات المتنوعة في ملف PDF`PdfOptions` هدف. على سبيل المثال، يمكنك ضبط الجودة والضغط والمعلمات الأخرى وفقًا لاحتياجاتك.

### كيف يمكنني الحصول على Aspose.Slides لجافا؟

 يمكنك تنزيل Aspose.Slides for Java من موقع الويب على[هنا](https://releases.aspose.com/slides/java/).

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides؟

نعم، يتطلب Aspose.Slides ترخيصًا صالحًا للاستخدام التجاري. يمكنك الحصول على ترخيص من موقع Aspose.

### أين يمكنني العثور على المزيد من الوثائق والأمثلة؟

 يمكنك العثور على وثائق وأمثلة شاملة لـ Aspose.Slides for Java على[هنا](https://reference.aspose.com/slides/java/).
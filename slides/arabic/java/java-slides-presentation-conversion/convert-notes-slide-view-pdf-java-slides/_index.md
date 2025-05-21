---
"description": "تعرّف على كيفية تحويل عروض PowerPoint التقديمية مع الملاحظات إلى ملفات PDF باستخدام Aspose.Slides لجافا. اتبع دليلنا خطوة بخطوة مع الكود المصدري."
"linktitle": "تحويل عرض شرائح الملاحظات إلى ملف PDF في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل عرض شرائح الملاحظات إلى ملف PDF في Java Slides"
"url": "/ar/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل عرض شرائح الملاحظات إلى ملف PDF في Java Slides


## مقدمة لتحويل عرض شرائح الملاحظات إلى PDF في Java Slides

في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل عرض تقديمي في PowerPoint مع عرض شرائح الملاحظات إلى ملف PDF باستخدام مكتبة Aspose.Slides لجافا. توفر هذه المكتبة ميزات فعّالة للعمل مع عروض PowerPoint التقديمية بلغة جافا.

## المتطلبات الأساسية
1. تم تثبيت Java Development Kit (JDK).
2. تمت إضافة مكتبة Aspose.Slides for Java إلى مشروعك.

## الخطوة 1: استيراد الفئات الضرورية
للبدء، ستحتاج إلى استيراد الفئات اللازمة من مكتبة Aspose.Slides. إليك الكود اللازم:

```java
import com.aspose.slides.*;
```

## الخطوة 2: تحميل عرض PowerPoint
يجب أن يكون ملف عرض PowerPoint جاهزًا. استبدل `"Your Document Directory"` مع مسار المجلد الذي يحتوي على ملف العرض التقديمي. إليك الكود لتحميل العرض التقديمي:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## الخطوة 3: تكوين خيارات PDF
الآن، لنُهيئ خيارات تصدير ملف PDF. على وجه التحديد، سنضبط موضع الملاحظات على "BottomFull" لتضمين الملاحظات أسفل الشرائح في ملف PDF. إليك الكود:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

يمكنك تخصيص خيارات PDF الأخرى وفقًا لمتطلباتك.

## الخطوة 4: حفظ العرض التقديمي بصيغة PDF مع الملاحظات
أخيرًا، لنحفظ العرض التقديمي كملف PDF، بما في ذلك الملاحظات. يمكنك تحديد اسم ملف الإخراج (مثلًا، `"Pdf_Notes_out.pdf"`) واختر التنسيق (`SaveFormat.Pdf`). هذا هو الكود للقيام بذلك:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## الخطوة 5: تنظيف الموارد
لا تنسَ إصدار الموارد بمجرد الانتهاء من العرض التقديمي:

```java
if (presentation != null) presentation.dispose();
```

## كود المصدر الكامل لتحويل عرض شرائح الملاحظات إلى PDF في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء كائن عرض تقديمي يمثل ملف عرض تقديمي
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

في هذا البرنامج التعليمي، استكشفنا كيفية تحويل عروض PowerPoint التقديمية مع ملاحظات لعرض الشرائح إلى ملفات PDF باستخدام مكتبة Aspose.Slides لجافا. اتبعنا دليلاً خطوة بخطوة مع الكود المصدري لتحقيق هذا التحويل. إليك أهم النقاط المستفادة:

## الأسئلة الشائعة

### كيف يمكنني تغيير موضع الملاحظات في ملف PDF؟

يمكنك تغيير موضع الملاحظات في ملف PDF عن طريق تعديل `setNotesPosition` وسيطة الطريقة. على سبيل المثال، يمكنك ضبطها على `NotesPositions.RightFull` لوضع الملاحظات على الجانب الأيمن من الشرائح.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### هل يمكنني تخصيص تصدير PDF بشكل أكبر؟

نعم، يمكنك تخصيص تصدير ملف PDF عن طريق ضبط الخيارات المختلفة في `PdfOptions` على سبيل المثال، يمكنك ضبط الجودة والضغط والمعلمات الأخرى وفقًا لاحتياجاتك.

### كيف يمكنني الحصول على Aspose.Slides لـ Java؟

يمكنك تنزيل Aspose.Slides لـ Java من موقع الويب على [هنا](https://releases.aspose.com/slides/java/).

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides؟

نعم، يتطلب Aspose.Slides ترخيصًا صالحًا للاستخدام التجاري. يمكنك الحصول على الترخيص من موقع Aspose الإلكتروني.

### أين يمكنني العثور على مزيد من الوثائق والأمثلة؟

يمكنك العثور على وثائق وأمثلة شاملة لـ Aspose.Slides لـ Java على [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
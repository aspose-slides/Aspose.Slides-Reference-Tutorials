---
title: تحويل مع حجم مخصص في شرائح جافا
linktitle: تحويل مع حجم مخصص في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل عروض PowerPoint التقديمية إلى صور TIFF بحجم مخصص باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية للمطورين.
weight: 31
url: /ar/java/presentation-conversion/convert-custom-size-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة للتحويل بحجم مخصص في شرائح Java

في هذه المقالة، سنستكشف كيفية تحويل عروض PowerPoint التقديمية إلى صور TIFF بحجم مخصص باستخدام Aspose.Slides for Java API. Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بالعمل مع ملفات PowerPoint برمجياً. سنذهب خطوة بخطوة ونزودك بكود Java اللازم لإنجاز هذه المهمة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت مجموعة أدوات تطوير Java (JDK).
- Aspose.Slides لمكتبة جافا

 يمكنك تنزيل مكتبة Aspose.Slides for Java من موقع الويب:[تنزيل Aspose.Slides للجافا](https://releases.aspose.com/slides/java/)

## الخطوة 1: استيراد مكتبة Aspose.Slides

للبدء، تحتاج إلى استيراد مكتبة Aspose.Slides إلى مشروع Java الخاص بك. وإليك كيف يمكنك القيام بذلك:

```java
// أضف بيان الاستيراد الضروري
import com.aspose.slides.*;
```

## الخطوة 2: قم بتحميل عرض PowerPoint التقديمي

 بعد ذلك، ستحتاج إلى تحميل عرض PowerPoint التقديمي الذي تريد تحويله إلى صورة TIFF. يستبدل`"Your Document Directory"` بالمسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## الخطوة 3: قم بتعيين خيارات تحويل TIFF

الآن، لنقم بتعيين خيارات تحويل TIFF. سنحدد نوع الضغط وDPI (النقاط في البوصة) وحجم الصورة وموضع الملاحظات. يمكنك تخصيص هذه الخيارات وفقًا لمتطلباتك.

```java
// إنشاء مثيل لفئة TiffOptions
TiffOptions opts = new TiffOptions();

// تحديد نوع الضغط
opts.setCompressionType(TiffCompressionTypes.Default);

// ضبط الصورة DPI
opts.setDpiX(200);
opts.setDpiY(100);

// ضبط حجم الصورة
opts.setImageSize(new Dimension(1728, 1078));

// ضبط موضع الملاحظات
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## الخطوة 4: احفظ باسم TIFF

بعد تكوين جميع الخيارات، يمكنك الآن حفظ العرض التقديمي كصورة TIFF بالإعدادات المحددة.

```java
// احفظ العرض التقديمي في TIFF بحجم الصورة المحدد
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## أكمل كود المصدر للتحويل بحجم مخصص في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// إنشاء مثيل لفئة TiffOptions
	TiffOptions opts = new TiffOptions();
	// تحديد نوع الضغط
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// أنواع الضغط
	// الافتراضي - يحدد نظام الضغط الافتراضي (LZW).
	// لا شيء - يحدد عدم وجود ضغط.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// يعتمد العمق على نوع الضغط ولا يمكن ضبطه يدويًا.
	// وحدة الدقة تساوي دائمًا "2" (نقطة في البوصة)
	// ضبط الصورة DPI
	opts.setDpiX(200);
	opts.setDpiY(100);
	// ضبط حجم الصورة
	opts.setImageSize(new Dimension(1728, 1078));
	// احفظ العرض التقديمي في TIFF بحجم الصورة المحدد
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

تهانينا! لقد نجحت في تحويل عرض PowerPoint التقديمي إلى صورة TIFF بحجم مخصص باستخدام Aspose.Slides لـ Java. يمكن أن تكون هذه ميزة قيمة عندما تحتاج إلى إنشاء صور عالية الجودة من العروض التقديمية الخاصة بك لأغراض مختلفة.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الضغط لصورة TIFF؟

 يمكنك تغيير نوع الضغط عن طريق تعديل`setCompressionType` الطريقة في`TiffOptions` فصل. هناك أنواع ضغط مختلفة متاحة، مثل Default، وNone، وCCITT3، وCCITT4، وLZW، وRLE.

### هل يمكنني ضبط DPI (النقاط في البوصة) لصورة TIFF؟

نعم، يمكنك ضبط DPI باستخدام`setDpiX` و`setDpiY` الأساليب في`TiffOptions` فصل. ما عليك سوى ضبط القيم المطلوبة للتحكم في دقة الصورة.

### ما هي الخيارات المتاحة لوضع الملاحظات في صورة TIFF؟

 يمكن تكوين موضع الملاحظات في صورة TIFF باستخدام`setNotesPosition` الطريقة مع خيارات مثل BottomFull، وBottomTruncated، وSlideOnly. اختر الخيار الذي يناسب احتياجاتك.

### هل من الممكن تحديد حجم صورة مخصص لتحويل TIFF؟

 قطعاً! يمكنك ضبط حجم الصورة المخصص باستخدام`setImageSize` الطريقة في`TiffOptions` فصل. قم بتوفير الأبعاد (العرض والارتفاع) التي تريدها لصورة الإخراج.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

 للحصول على وثائق مفصلة ومعلومات إضافية حول Aspose.Slides for Java، يرجى زيارة الوثائق:[Aspose.Slides لمرجع Java API](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

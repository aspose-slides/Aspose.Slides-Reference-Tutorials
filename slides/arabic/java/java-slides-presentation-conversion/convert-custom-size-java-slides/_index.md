---
"description": "تعرّف على كيفية تحويل عروض PowerPoint التقديمية إلى صور TIFF بحجم مخصص باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع أمثلة برمجية للمطورين."
"linktitle": "التحويل باستخدام الحجم المخصص في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "التحويل باستخدام الحجم المخصص في شرائح Java"
"url": "/ar/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# التحويل باستخدام الحجم المخصص في شرائح Java


## مقدمة للتحويل باستخدام الحجم المخصص في شرائح Java

في هذه المقالة، سنستكشف كيفية تحويل عروض PowerPoint التقديمية إلى صور TIFF بحجم مخصص باستخدام واجهة برمجة تطبيقات Aspose.Slides for Java. Aspose.Slides for Java هي مكتبة فعّالة تُمكّن المطورين من العمل مع ملفات PowerPoint برمجيًا. سنشرح خطوة بخطوة ونزودك بأكواد Java اللازمة لإنجاز هذه المهمة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK)
- مكتبة Aspose.Slides لـ Java

يمكنك تنزيل مكتبة Aspose.Slides for Java من موقع الويب: [تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/)

## الخطوة 1: استيراد مكتبة Aspose.Slides

للبدء، عليك استيراد مكتبة Aspose.Slides إلى مشروعك في Java. إليك الطريقة:

```java
// أضف بيان الاستيراد الضروري
import com.aspose.slides.*;
```

## الخطوة 2: تحميل عرض PowerPoint

بعد ذلك، ستحتاج إلى تحميل عرض PowerPoint التقديمي الذي تريد تحويله إلى صورة TIFF. استبدل `"Your Document Directory"` مع المسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء كائن عرض تقديمي يمثل ملف عرض تقديمي
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## الخطوة 3: تعيين خيارات تحويل TIFF

الآن، لنُحدد خيارات تحويل TIFF. سنحدد نوع الضغط، وعدد النقاط في البوصة (DPI)، وحجم الصورة، وموضع الملاحظات. يمكنك تخصيص هذه الخيارات حسب احتياجاتك.

```java
// إنشاء مثيل لفئة TiffOptions
TiffOptions opts = new TiffOptions();

// ضبط نوع الضغط
opts.setCompressionType(TiffCompressionTypes.Default);

// ضبط صورة DPI
opts.setDpiX(200);
opts.setDpiY(100);

// تعيين حجم الصورة
opts.setImageSize(new Dimension(1728, 1078));

// تعيين موضع الملاحظات
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## الخطوة 4: الحفظ بصيغة TIFF

بعد تكوين كافة الخيارات، يمكنك الآن حفظ العرض التقديمي كصورة TIFF باستخدام الإعدادات المحددة.

```java
// احفظ العرض التقديمي بصيغة TIFF بحجم الصورة المحدد
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## كود المصدر الكامل للتحويل بحجم مخصص في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء كائن عرض تقديمي يمثل ملف عرض تقديمي
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// إنشاء مثيل لفئة TiffOptions
	TiffOptions opts = new TiffOptions();
	// ضبط نوع الضغط
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// أنواع الضغط
	// افتراضي - يحدد مخطط الضغط الافتراضي (LZW).
	// لا شيء - لا يحدد أي ضغط.
	// CCITT3
	// CCITT4
	// إل زد دبليو
	// رل
	// يعتمد العمق على نوع الضغط ولا يمكن ضبطه يدويًا.
	// وحدة الدقة تساوي دائمًا "2" (نقطة لكل بوصة)
	// ضبط صورة DPI
	opts.setDpiX(200);
	opts.setDpiY(100);
	// تعيين حجم الصورة
	opts.setImageSize(new Dimension(1728, 1078));
	// احفظ العرض التقديمي بصيغة TIFF بحجم الصورة المحدد
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

تهانينا! لقد نجحت في تحويل عرض تقديمي من PowerPoint إلى صورة TIFF بحجم مخصص باستخدام Aspose.Slides لجافا. تُعد هذه ميزة قيّمة عند الحاجة إلى إنشاء صور عالية الجودة من عروضك التقديمية لأغراض متعددة.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الضغط لصورة TIFF؟

يمكنك تغيير نوع الضغط عن طريق تعديل `setCompressionType` الطريقة في `TiffOptions` تتوفر أنواع ضغط مختلفة، مثل Default، وNone، وCCITT3، وCCITT4، وLZW، وRLE.

### هل يمكنني تعديل DPI (نقاط لكل بوصة) لصورة TIFF؟

نعم، يمكنك ضبط DPI باستخدام `setDpiX` و `setDpiY` الأساليب في `TiffOptions` الصف. ما عليك سوى تعيين القيم المطلوبة للتحكم في دقة الصورة.

### ما هي الخيارات المتاحة لموضع الملاحظات في صورة TIFF؟

يمكن تكوين موضع الملاحظات في صورة TIFF باستخدام `setNotesPosition` طريقة بخيارات مثل BottomFull وBottomTruncated وSlideOnly. اختر الأنسب لاحتياجاتك.

### هل من الممكن تحديد حجم صورة مخصص لتحويل TIFF؟

بالتأكيد! يمكنك تحديد حجم الصورة باستخدام `setImageSize` الطريقة في `TiffOptions` قم بتوفير الأبعاد (العرض والارتفاع) التي تريدها للصورة الناتجة.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

للحصول على توثيق مفصل ومعلومات إضافية حول Aspose.Slides لـ Java، يرجى زيارة التوثيق: [مرجع واجهة برمجة تطبيقات Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
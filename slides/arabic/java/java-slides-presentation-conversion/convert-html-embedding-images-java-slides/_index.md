---
"description": "حوّل PowerPoint إلى HTML باستخدام الصور المضمنة. دليل خطوة بخطوة باستخدام Aspose.Slides لجافا. تعلّم كيفية أتمتة تحويلات العروض التقديمية في جافا بسهولة."
"linktitle": "تحويل صور HTML المضمنة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل صور HTML المضمنة في شرائح Java"
"url": "/ar/java/presentation-conversion/convert-html-embedding-images-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل صور HTML المضمنة في شرائح Java


## مقدمة لتحويل صور HTML المضمنة في شرائح Java

في هذا الدليل التفصيلي، سنشرح لك عملية تحويل عرض تقديمي من PowerPoint إلى مستند HTML مع تضمين الصور باستخدام Aspose.Slides لجافا. يفترض هذا البرنامج التعليمي أنك قمتَ بإعداد بيئة التطوير لديكَ وتثبيت مكتبة Aspose.Slides لجافا.

## متطلبات

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://downloads.aspose.com/slides/java).

2. ملف عرض تقديمي PowerPoint (تنسيق PPTX) الذي تريد تحويله إلى HTML.

3. تم إعداد بيئة تطوير Java.

## الخطوة 1: استيراد المكتبات المطلوبة

أولاً، عليك استيراد المكتبات والفئات الضرورية لمشروع Java الخاص بك.

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## الخطوة 2: تحميل عرض PowerPoint

بعد ذلك، قم بتحميل عرض PowerPoint الذي تريد تحويله إلى HTML. تأكد من استبدال `presentationName` مع المسار الفعلي لملف العرض التقديمي الخاص بك.

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## الخطوة 3: تكوين خيارات تحويل HTML

الآن، ستُهيئ خيارات تحويل HTML. في هذا المثال، سنُضمّن الصور في مستند HTML ونُحدّد مجلد الإخراج للصور الخارجية.

```java
Html5Options options = new Html5Options();
// فرض عدم حفظ الصور في مستند HTML5
options.setEmbedImages(true); // اضبط على "صحيح" لتضمين الصور
// تعيين المسار للصور الخارجية (إذا لزم الأمر)
options.setOutputPath("path/to/output/directory/");
```

## الخطوة 4: إنشاء دليل الإخراج

قبل حفظ مستند HTML، قم بإنشاء دليل الإخراج إذا لم يكن موجودًا.

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## الخطوة 5: حفظ العرض التقديمي بصيغة HTML

الآن، قم بحفظ العرض التقديمي بتنسيق HTML5 مع الخيارات المحددة.

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## الخطوة 6: تنظيف الموارد

لا تنس التخلص من كائن العرض لتحرير أي موارد مخصصة.

```java
if (pres != null) {
    pres.dispose();
}
```

## كود المصدر الكامل لتحويل صور HTML المضمنة في شرائح Java

```java
// المسار إلى عرض المصدر
String presentationName = "Your Document Directory";
// المسار إلى مستند HTML
String outFilePath = "Your Output Directory" + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	// فرض عدم حفظ الصور في مستند HTML5
	options.setEmbedImages(false);
	// تعيين المسار للصور الخارجية
	options.setOutputPath(outFilePath);
	// إنشاء دليل لمستند HTML الناتج
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	// حفظ العرض التقديمي بتنسيق HTML5.
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا الدليل الشامل، تعلمنا كيفية تحويل عرض تقديمي من PowerPoint إلى مستند HTML مع تضمين الصور باستخدام Aspose.Slides لجافا. باتباع التعليمات خطوة بخطوة، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات جافا وتحسين عمليات تحويل المستندات.

## الأسئلة الشائعة

### كيف يمكنني تغيير اسم ملف الإخراج؟

يمكنك تغيير اسم ملف الإخراج عن طريق تعديل الوسيطة في `pres.save()` طريقة.

### هل يمكنني تخصيص قالب HTML؟

نعم، يمكنك تخصيص قالب HTML بتعديل ملفات HTML وCSS المُنشأة بواسطة Aspose.Slides. ستجدها في مجلد الإخراج.

### كيف أتعامل مع الأخطاء أثناء التحويل؟

يمكنك تغليف كود التحويل في كتلة try-catch للتعامل مع الاستثناءات التي قد تحدث أثناء عملية التحويل.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
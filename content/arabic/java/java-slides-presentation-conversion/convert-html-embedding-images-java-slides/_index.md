---
title: تحويل صور تضمين HTML في شرائح جافا
linktitle: تحويل صور تضمين HTML في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تحويل PowerPoint إلى HTML مع الصور المضمنة. دليل خطوة بخطوة باستخدام Aspose.Slides لـ Java. تعلم كيفية أتمتة تحويلات العرض التقديمي في Java دون عناء.
type: docs
weight: 11
url: /ar/java/presentation-conversion/convert-html-embedding-images-java-slides/
---

## مقدمة لتحويل صور تضمين HTML في شرائح Java

في هذا الدليل خطوة بخطوة، سنرشدك خلال عملية تحويل عرض PowerPoint التقديمي إلى مستند HTML أثناء تضمين الصور باستخدام Aspose.Slides لـ Java. يفترض هذا البرنامج التعليمي أنك قمت بالفعل بإعداد بيئة التطوير الخاصة بك وقمت بتثبيت مكتبة Aspose.Slides for Java.

## متطلبات

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1.  تم تثبيت Aspose.Slides لمكتبة Java. يمكنك تنزيله من[هنا](https://downloads.aspose.com/slides/java).

2. ملف عرض PowerPoint التقديمي (تنسيق PPTX) الذي تريد تحويله إلى HTML.

3. تم إعداد بيئة تطوير Java.

## الخطوة 1: استيراد المكتبات المطلوبة

أولاً، تحتاج إلى استيراد المكتبات والفئات اللازمة لمشروع Java الخاص بك.

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## الخطوة 2: قم بتحميل عرض PowerPoint التقديمي

 بعد ذلك، ستقوم بتحميل عرض PowerPoint التقديمي الذي تريد تحويله إلى HTML. تأكد من استبدال`presentationName` بالمسار الفعلي لملف العرض التقديمي الخاص بك.

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## الخطوة 3: تكوين خيارات تحويل HTML

الآن، ستقوم بتكوين خيارات تحويل HTML. في هذا المثال، سنقوم بتضمين الصور في مستند HTML وتحديد دليل الإخراج للصور الخارجية.

```java
Html5Options options = new Html5Options();
//فرض عدم حفظ الصور في مستند HTML5
options.setEmbedImages(true); // اضبط على صحيح لتضمين الصور
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

## الخطوة 5: احفظ العرض التقديمي بتنسيق HTML

الآن، احفظ العرض التقديمي بتنسيق HTML5 بالخيارات المحددة.

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## الخطوة 6: تنظيف الموارد

لا تنس التخلص من كائن العرض التقديمي لتحرير أي موارد مخصصة.

```java
if (pres != null) {
    pres.dispose();
}
```

## كود المصدر الكامل لتحويل صور تضمين HTML في شرائح جافا

```java
// المسار إلى العرض التقديمي المصدر
String presentationName = RunExamples.getDataDir_Conversion() + "PresentationDemo.pptx";
// المسار إلى مستند HTML
String outFilePath = RunExamples.getOutPath() + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	//فرض عدم حفظ الصور في مستند HTML5
	options.setEmbedImages(false);
	// تحديد المسار للصور الخارجية
	options.setOutputPath(outFilePath);
	// إنشاء دليل لمستند HTML الإخراج
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

في هذا الدليل الشامل، تعلمنا كيفية تحويل عرض PowerPoint التقديمي إلى مستند HTML أثناء تضمين الصور باستخدام Aspose.Slides لـ Java. باتباع الإرشادات خطوة بخطوة، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات Java لديك وتحسين عمليات تحويل المستندات الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تغيير اسم ملف الإخراج؟

 يمكنك تغيير اسم ملف الإخراج عن طريق تعديل الوسيطة في ملف`pres.save()` طريقة.

### هل يمكنني تخصيص قالب HTML؟

نعم، يمكنك تخصيص قالب HTML عن طريق تعديل ملفات HTML وCSS التي تم إنشاؤها بواسطة Aspose.Slides. ستجدهم في دليل الإخراج.

### كيف أتعامل مع الأخطاء أثناء التحويل؟

يمكنك تغليف رمز التحويل في كتلة محاولة الالتقاط لمعالجة الاستثناءات التي قد تحدث أثناء عملية التحويل.

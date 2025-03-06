---
title: تحويل العرض التقديمي بالكامل إلى HTML باستخدام ملفات الوسائط في شرائح Java
linktitle: تحويل العرض التقديمي بالكامل إلى HTML باستخدام ملفات الوسائط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل العروض التقديمية إلى HTML باستخدام ملفات الوسائط باستخدام Java Slides. اتبع دليلنا خطوة بخطوة مع Aspose.Slides for Java API.
weight: 30
url: /ar/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لتحويل العرض التقديمي بالكامل إلى HTML باستخدام ملفات الوسائط في شرائح Java

في العصر الرقمي الحالي، تعد الحاجة إلى تحويل العروض التقديمية إلى تنسيقات مختلفة، بما في ذلك HTML، مطلبًا شائعًا. غالبًا ما يجد مطورو Java أنفسهم مكلفين بهذا التحدي. لحسن الحظ، باستخدام Aspose.Slides for Java API، يمكن إنجاز هذه المهمة بكفاءة. في هذا الدليل التفصيلي، سنستكشف كيفية تحويل عرض تقديمي كامل إلى HTML مع الحفاظ على ملفات الوسائط باستخدام Java Slides.

## المتطلبات الأساسية

قبل أن نتعمق في جانب البرمجة، دعونا نتأكد من إعداد كل شيء بشكل صحيح:

- Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
-  Aspose.Slides for Java: ستحتاج إلى تثبيت Aspose.Slides for Java API. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: استيراد الحزم الضرورية

للبدء، تحتاج إلى استيراد الحزم اللازمة. ستوفر هذه الحزم الفئات والأساليب المطلوبة لمهمتنا.

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## الخطوة 2: حدد دليل المستندات

 حدد المسار إلى دليل المستند الخاص بك حيث يوجد ملف العرض التقديمي. يستبدل`"Your Document Directory"` مع المسار الفعلي

```java
String dataDir = "Your Document Directory";
```

## الخطوة 3: تهيئة العرض التقديمي

 قم بتحميل العرض التقديمي الذي تريد تحويله إلى HTML. تأكد من استبدال`"presentationWith.pptx"` مع اسم ملف العرض التقديمي الخاص بك.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## الخطوة 4: إنشاء وحدة تحكم HTML

 سنقوم بإنشاء`VideoPlayerHtmlController` للتعامل مع عملية التحويل. استبدل عنوان URL بعنوان الويب الذي تريده.

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## الخطوة 5: تكوين خيارات HTML وSVG

قم بإعداد خيارات HTML وSVG للتحويل. هذا هو المكان الذي يمكنك فيه تخصيص التنسيق حسب الحاجة.

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## الخطوة 6: احفظ العرض التقديمي بتنسيق HTML

حان الوقت الآن لحفظ العرض التقديمي كملف HTML، بما في ذلك ملفات الوسائط.

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## كود المصدر الكامل لتحويل العرض التقديمي بالكامل إلى HTML باستخدام ملفات الوسائط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.example.com/");
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا عملية تحويل عرض تقديمي كامل إلى HTML باستخدام ملفات الوسائط باستخدام Java Slides وAspose.Slides for Java API. باتباع هذه الخطوات، يمكنك تحويل عروضك التقديمية بكفاءة إلى تنسيق متوافق مع الويب، مع الحفاظ على جميع عناصر الوسائط الأساسية.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لجافا؟

 لتثبيت Aspose.Slides لـ Java، قم بزيارة صفحة التنزيل على[هنا](https://releases.aspose.com/slides/java/) واتبع تعليمات التثبيت المقدمة.

### هل يمكنني تخصيص مخرجات HTML بشكل أكبر؟

 نعم، يمكنك تخصيص مخرجات HTML وفقًا لمتطلباتك. ال`HtmlOptions` يوفر class إعدادات متنوعة للتحكم في عملية التحويل، بما في ذلك خيارات التنسيق والتخطيط.

### هل يدعم Aspose.Slides for Java تنسيقات الإخراج الأخرى؟

نعم، يدعم Aspose.Slides for Java تنسيقات الإخراج المختلفة، بما في ذلك PDF وPPTX والمزيد. يمكنك استكشاف هذه الخيارات في الوثائق.

### هل Aspose.Slides for Java مناسب للمشاريع التجارية؟

نعم، يعد Aspose.Slides for Java حلاً قويًا ومجديًا تجاريًا للتعامل مع المهام المتعلقة بالعرض التقديمي في تطبيقات Java. ويستخدم على نطاق واسع في المشاريع على مستوى المؤسسة.

### كيف يمكنني الوصول إلى عرض HTML المحول؟

 بمجرد الانتهاء من التحويل، يمكنك الوصول إلى العرض التقديمي بتنسيق HTML عن طريق تحديد موقع الملف المحدد في ملف`htmlDocumentFileName` عامل.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

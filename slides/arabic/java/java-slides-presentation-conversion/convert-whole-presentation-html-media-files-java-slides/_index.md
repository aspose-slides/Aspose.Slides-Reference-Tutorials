---
"description": "تعرّف على كيفية تحويل العروض التقديمية إلى HTML مع ملفات الوسائط باستخدام Java Slides. اتبع دليلنا خطوة بخطوة مع واجهة برمجة تطبيقات Aspose.Slides لـ Java."
"linktitle": "تحويل العرض التقديمي بأكمله إلى HTML باستخدام ملفات الوسائط في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل العرض التقديمي بأكمله إلى HTML باستخدام ملفات الوسائط في Java Slides"
"url": "/ar/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/"
"weight": 30
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل العرض التقديمي بأكمله إلى HTML باستخدام ملفات الوسائط في Java Slides


## مقدمة لتحويل العرض التقديمي بأكمله إلى HTML باستخدام ملفات الوسائط في شرائح Java

في عصرنا الرقمي، يُعدّ تحويل العروض التقديمية إلى صيغ مختلفة، بما في ذلك HTML، مطلبًا شائعًا. غالبًا ما يواجه مطورو جافا هذا التحدي. لحسن الحظ، مع واجهة برمجة تطبيقات Aspose.Slides لجافا، يُمكن إنجاز هذه المهمة بكفاءة. في هذا الدليل المُفصّل، سنستكشف كيفية تحويل عرض تقديمي كامل إلى HTML مع الحفاظ على ملفات الوسائط باستخدام Java Slides.

## المتطلبات الأساسية

قبل أن نتعمق في جانب الترميز، دعونا نتأكد من إعداد كل شيء بشكل صحيح:

- مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
- Aspose.Slides لجافا: ستحتاج إلى تثبيت واجهة برمجة تطبيقات Aspose.Slides لجافا. يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: استيراد الحزم الضرورية

للبدء، عليك استيراد الحزم اللازمة. ستوفر هذه الحزم الفئات والأساليب اللازمة لمهمتنا.

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## الخطوة 2: تحديد دليل المستندات

حدد المسار إلى دليل المستندات الذي يحتوي على ملف العرض التقديمي. استبدل `"Your Document Directory"` مع المسار الفعلي.

```java
String dataDir = "Your Document Directory";
```

## الخطوة 3: تهيئة العرض التقديمي

حمّل العرض التقديمي الذي تريد تحويله إلى HTML. تأكد من استبدال `"presentationWith.pptx"` مع اسم ملف العرض التقديمي الخاص بك.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## الخطوة 4: إنشاء وحدة تحكم HTML

سوف نقوم بإنشاء `VideoPlayerHtmlController` لإدارة عملية التحويل. استبدل عنوان URL بعنوان الويب الذي تريده.

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## الخطوة 5: تكوين خيارات HTML وSVG

قم بإعداد خيارات HTML وSVG للتحويل. هنا يمكنك تخصيص التنسيق حسب الحاجة.

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## الخطوة 6: حفظ العرض التقديمي بصيغة HTML

الآن، حان الوقت لحفظ العرض التقديمي كملف HTML، بما في ذلك ملفات الوسائط.

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## كود المصدر الكامل لتحويل العرض التقديمي بأكمله إلى HTML مع ملفات الوسائط في شرائح Java

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

في هذا البرنامج التعليمي، شرحنا عملية تحويل عرض تقديمي كامل إلى HTML مع ملفات وسائط باستخدام Java Slides وواجهة برمجة تطبيقات Aspose.Slides لـ Java. باتباع هذه الخطوات، يمكنك تحويل عروضك التقديمية بكفاءة إلى تنسيق متوافق مع الويب، مع الحفاظ على جميع عناصر الوسائط الأساسية.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ Java؟

لتثبيت Aspose.Slides لـ Java، قم بزيارة صفحة التنزيل على [هنا](https://releases.aspose.com/slides/java/) واتبع تعليمات التثبيت المقدمة.

### هل يمكنني تخصيص إخراج HTML بشكل أكبر؟

نعم، يمكنك تخصيص مخرجات HTML وفقًا لمتطلباتك. `HtmlOptions` توفر الفئة إعدادات مختلفة للتحكم في عملية التحويل، بما في ذلك خيارات التنسيق والتخطيط.

### هل يدعم Aspose.Slides for Java تنسيقات إخراج أخرى؟

نعم، يدعم Aspose.Slides لجافا تنسيقات إخراج متنوعة، بما في ذلك PDF وPPTX وغيرها. يمكنك استكشاف هذه الخيارات في الوثائق.

### هل Aspose.Slides for Java مناسب للمشاريع التجارية؟

نعم، يُعد Aspose.Slides for Java حلاً قويًا ومجديًا تجاريًا لإدارة مهام العروض التقديمية في تطبيقات Java. ويُستخدم على نطاق واسع في المشاريع المؤسسية.

### كيف يمكنني الوصول إلى العرض التقديمي HTML المُحوّل؟

بمجرد الانتهاء من التحويل، يمكنك الوصول إلى عرض HTML من خلال تحديد موقع الملف المحدد في `htmlDocumentFileName` عامل.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
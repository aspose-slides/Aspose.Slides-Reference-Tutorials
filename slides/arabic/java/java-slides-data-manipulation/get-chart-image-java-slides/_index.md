---
title: الحصول على صورة المخطط في شرائح جافا
linktitle: الحصول على صورة المخطط في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية الحصول على صور المخططات في Java Slides باستخدام Aspose.Slides لـ Java. يوفر هذا الدليل خطوة بخطوة التعليمات البرمجية المصدر ونصائح للتكامل السلس.
weight: 19
url: /ar/java/data-manipulation/get-chart-image-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة للحصول على صورة المخطط في شرائح جافا

Aspose.Slides for Java هي مكتبة قوية تسمح لك بالعمل مع عروض PowerPoint التقديمية برمجياً. باستخدام هذه المكتبة، يمكنك إنشاء عناصر متنوعة ومعالجتها واستخراجها من العروض التقديمية، بما في ذلك المخططات. أحد المتطلبات الشائعة هو الحصول على صور المخططات من الشرائح، وسنوضح كيفية القيام بذلك في هذا الدليل.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تم تنزيل Aspose.Slides لمكتبة Java وتكوينها في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: قم بإعداد مشروعك

ابدأ بإنشاء مشروع Java في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من أنك قمت بإضافة مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.

## الخطوة 2: تهيئة العرض التقديمي

للبدء، تحتاج إلى تهيئة عرض PowerPoint التقديمي. في هذا المثال، نفترض أن لديك ملف PowerPoint باسم "test.pptx" في دليل المستند.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 3: أضف مخططًا واحصل على الصورة

بعد ذلك، يمكنك إضافة مخطط إلى الشريحة والحصول على صورته. في هذا المثال، سنقوم بإضافة مخطط عمودي متفاوت المسافات.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

في مقتطف الكود هذا، نقوم بإنشاء مخطط عمودي متفاوت المسافات على الشريحة الأولى من العرض التقديمي ثم نحصل على صورته المصغرة. يتم حفظ الصورة باسم "image.png" في الدليل المحدد.

## أكمل كود المصدر للحصول على صورة المخطط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

يعد الحصول على صور المخططات من Java Slides باستخدام Aspose.Slides لـ Java عملية مباشرة. باستخدام الكود المقدم، يمكنك بسهولة دمج هذه الوظيفة في تطبيقات Java الخاصة بك، مما يسمح لك بالعمل مع عروض PowerPoint التقديمية بفعالية.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

 يعد تثبيت Aspose.Slides لـ Java أمرًا بسيطًا. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/) واتبع تعليمات التثبيت المتوفرة في الوثائق.

### هل يمكنني تخصيص المخطط قبل الحصول على صورته؟

نعم، يمكنك تخصيص مظهر المخطط وبياناته وخصائصه الأخرى قبل الحصول على صورته. يوفر Aspose.Slides for Java خيارات واسعة لتخصيص المخطط.

### ما الميزات الأخرى التي يقدمها Aspose.Slides لـ Java؟

يوفر Aspose.Slides for Java مجموعة واسعة من الميزات للعمل مع عروض PowerPoint التقديمية، بما في ذلك إنشاء الشرائح ومعالجة النص وتحرير الأشكال وغير ذلك الكثير. يمكنك استكشاف الوثائق للحصول على معلومات مفصلة.

### هل Aspose.Slides for Java مناسب للاستخدام التجاري؟

نعم، يمكن استخدام Aspose.Slides for Java لأغراض تجارية. ويوفر خيارات الترخيص التي تلبي احتياجات كل من المطورين الأفراد والشركات.

### هل يمكنني حفظ صورة المخطط بتنسيق مختلف؟

 بالتأكيد! يمكنك حفظ صورة المخطط بتنسيقات مختلفة، مثل JPEG أو GIF، عن طريق تحديد امتداد الملف المناسب في`ImageIO.write` طريقة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

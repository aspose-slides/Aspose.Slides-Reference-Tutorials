---
"description": "تعرّف على كيفية الحصول على صور المخططات في شرائح جافا باستخدام Aspose.Slides لجافا. يوفر هذا الدليل خطوة بخطوة شفرة المصدر ونصائح للتكامل السلس."
"linktitle": "الحصول على صورة الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الحصول على صورة الرسم البياني في شرائح Java"
"url": "/ar/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على صورة الرسم البياني في شرائح Java


## مقدمة للحصول على صورة الرسم البياني في شرائح Java

Aspose.Slides for Java هي مكتبة فعّالة تُمكّنك من العمل مع عروض PowerPoint التقديمية برمجيًا. باستخدام هذه المكتبة، يُمكنك إنشاء عناصر مُختلفة من العروض التقديمية، بما في ذلك المخططات البيانية، ومعالجتها، واستخراجها. من المتطلبات الشائعة الحصول على صور المخططات البيانية من الشرائح، وسنوضح كيفية القيام بذلك في هذا الدليل.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل مكتبة Aspose.Slides لجافا وتهيئتها في مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد مشروعك

ابدأ بإنشاء مشروع جافا في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من إضافة مكتبة Aspose.Slides لجافا إلى تبعيات مشروعك.

## الخطوة 2: تهيئة العرض التقديمي

للبدء، عليك تهيئة عرض تقديمي لبرنامج PowerPoint. في هذا المثال، نفترض أن لديك ملف PowerPoint باسم "test.pptx" في مجلد المستندات.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 3: إضافة مخطط والحصول على الصورة

بعد ذلك، يمكنك إضافة مخطط إلى شريحة والحصول على صورته. في هذا المثال، سنضيف مخططًا عموديًا مجمعًا.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

في هذا المقطع البرمجي، نُنشئ مخططًا عموديًا مُجمّعًا على الشريحة الأولى من العرض التقديمي، ثم نحصل على صورته المصغرة. تُحفظ الصورة بصيغة "image.png" في المجلد المُحدد.

## كود المصدر الكامل للحصول على صورة الرسم البياني في شرائح Java

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

الحصول على صور مخططات من شرائح جافا باستخدام Aspose.Slides لجافا عملية سهلة. باستخدام الكود المُرفق، يمكنك دمج هذه الوظيفة بسهولة في تطبيقات جافا، مما يُتيح لك العمل مع عروض PowerPoint التقديمية بفعالية.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

تثبيت Aspose.Slides لجافا سهل للغاية. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/) واتبع تعليمات التثبيت الواردة في الوثائق.

### هل يمكنني تخصيص الرسم البياني قبل الحصول على صورته؟

نعم، يمكنك تخصيص مظهر الرسم البياني وبياناته وخصائصه الأخرى قبل الحصول على صورته. يوفر Aspose.Slides لـ Java خيارات شاملة لتخصيص الرسم البياني.

### ما هي الميزات الأخرى التي يقدمها Aspose.Slides لـ Java؟

يوفر Aspose.Slides لجافا مجموعة واسعة من الميزات للعمل مع عروض PowerPoint التقديمية، بما في ذلك إنشاء الشرائح، ومعالجة النصوص، وتحرير الأشكال، وغيرها الكثير. يمكنك الاطلاع على الوثائق لمزيد من المعلومات.

### هل Aspose.Slides for Java مناسب للاستخدام التجاري؟

نعم، يُمكن استخدام Aspose.Slides for Java لأغراض تجارية. فهو يُوفر خيارات ترخيص تُناسب المُطورين الأفراد والشركات على حدٍ سواء.

### هل يمكنني حفظ صورة الرسم البياني بتنسيق مختلف؟

بالتأكيد! يمكنك حفظ صورة الرسم البياني بتنسيقات مختلفة، مثل JPEG أو GIF، بتحديد امتداد الملف المناسب في `ImageIO.write` طريقة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
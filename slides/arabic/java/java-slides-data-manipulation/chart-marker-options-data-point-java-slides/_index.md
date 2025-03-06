---
title: خيارات علامة الرسم البياني على نقطة البيانات في شرائح جافا
linktitle: خيارات علامة الرسم البياني على نقطة البيانات في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين شرائح Java الخاصة بك باستخدام خيارات علامة الرسم البياني المخصصة. تعلم كيفية تحسين نقاط البيانات بشكل مرئي باستخدام Aspose.Slides لـ Java. استكشف الإرشادات والأسئلة الشائعة خطوة بخطوة.
weight: 14
url: /ar/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# خيارات علامة الرسم البياني على نقطة البيانات في شرائح جافا


## مقدمة إلى خيارات علامة المخطط على نقطة البيانات في شرائح Java

عندما يتعلق الأمر بإنشاء عروض تقديمية مؤثرة، فإن القدرة على تخصيص علامات المخطط ومعالجتها على نقاط البيانات يمكن أن تُحدث فرقًا كبيرًا. باستخدام Aspose.Slides for Java، لديك القدرة على تحويل مخططاتك إلى عناصر ديناميكية وجذابة بصريًا.

## المتطلبات الأساسية

قبل أن نتعمق في جزء البرمجة، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير جافا
- Aspose.Slides لمكتبة جافا
- بيئة تطوير جافا المتكاملة (IDE)
- نموذج مستند العرض التقديمي (على سبيل المثال، "Test.pptx")

## الخطوة 1: إعداد البيئة

أولاً، تأكد من أن الأدوات اللازمة مثبتة وجاهزة. قم بإنشاء مشروع Java في IDE الخاص بك وقم باستيراد Aspose.Slides لمكتبة Java.

## الخطوة 2: تحميل العرض التقديمي

للبدء، قم بتحميل نموذج مستند العرض التقديمي الخاص بك. في التعليمات البرمجية المتوفرة، نفترض أن المستند يسمى "Test.pptx."

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## الخطوة 3: إنشاء مخطط

الآن، لنقم بإنشاء مخطط في العرض التقديمي. سنستخدم مخططًا خطيًا مع علامات في هذا المثال.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## الخطوة 4: العمل مع بيانات الرسم البياني

لمعالجة بيانات المخطط، نحتاج إلى الوصول إلى مصنف بيانات المخطط وإعداد سلسلة البيانات. سنقوم بمسح السلسلة الافتراضية وإضافة بياناتنا المخصصة.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## الخطوة 5: إضافة علامات مخصصة

هنا يأتي الجزء المثير - تخصيص العلامات على نقاط البيانات. سنستخدم الصور كعلامات في هذا المثال.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// إضافة علامات مخصصة إلى نقاط البيانات
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// كرر لنقاط البيانات الأخرى
// ...

// تغيير حجم علامة سلسلة الرسم البياني
series.getMarker().setSize(15);
```

## الخطوة 6: حفظ العرض التقديمي

بمجرد تخصيص علامات المخطط، احفظ العرض التقديمي لترى التغييرات أثناء التنفيذ.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لخيارات علامة المخطط على نقطة البيانات في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//إنشاء المخطط الافتراضي
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//الحصول على فهرس ورقة عمل بيانات المخطط الافتراضي
int defaultWorksheetIndex = 0;
//الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//حذف السلسلة التجريبية
chart.getChartData().getSeries().clear();
//إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//تعيين الصورة
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//تعيين الصورة
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//أضف نقطة جديدة (1:3) هناك.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//تغيير علامة سلسلة الرسم البياني
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## خاتمة

باستخدام Aspose.Slides for Java، يمكنك رفع مستوى العروض التقديمية الخاصة بك عن طريق تخصيص علامات المخطط على نقاط البيانات. يتيح لك هذا إنشاء شرائح مذهلة وغنية بالمعلومات تأسر جمهورك.

## الأسئلة الشائعة

### كيف يمكنني تغيير حجم العلامة لنقاط البيانات؟

 لتغيير حجم العلامة لنقاط البيانات، استخدم`series.getMarker().setSize()` الطريقة وتوفير الحجم المطلوب كوسيطة.

### هل يمكنني استخدام الصور كعلامات مخصصة؟

 نعم، يمكنك استخدام الصور كعلامات مخصصة لنقاط البيانات. اضبط نوع التعبئة على`FillType.Picture` وتقديم الصورة التي تريد استخدامها.

### هل Aspose.Slides for Java مناسب لإنشاء مخططات ديناميكية؟

قطعاً! يوفر Aspose.Slides for Java إمكانات واسعة لإنشاء مخططات ديناميكية وتفاعلية في عروضك التقديمية.

### هل يمكنني تخصيص جوانب أخرى من المخطط باستخدام Aspose.Slides؟

نعم، يمكنك تخصيص جوانب مختلفة من المخطط، بما في ذلك العناوين والمحاور وتسميات البيانات والمزيد، باستخدام Aspose.Slides for Java.

### أين يمكنني الوصول إلى وثائق وتنزيلات Aspose.Slides for Java؟

 يمكنك العثور على الوثائق في[هنا](https://reference.aspose.com/slides/java/) وتحميل المكتبة في[هنا](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

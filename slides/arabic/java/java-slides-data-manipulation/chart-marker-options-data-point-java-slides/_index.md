---
"description": "حسّن عروض شرائح جافا باستخدام خيارات علامات المخططات المخصصة. تعلّم كيفية تحسين نقاط البيانات بصريًا باستخدام Aspose.Slides لجافا. استكشف الإرشادات خطوة بخطوة والأسئلة الشائعة."
"linktitle": "خيارات علامة الرسم البياني على نقطة البيانات في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "خيارات علامة الرسم البياني على نقطة البيانات في شرائح Java"
"url": "/ar/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خيارات علامة الرسم البياني على نقطة البيانات في شرائح Java


## مقدمة لخيارات علامة الرسم البياني على نقطة البيانات في شرائح Java

عندما يتعلق الأمر بإنشاء عروض تقديمية مؤثرة، فإن القدرة على تخصيص علامات المخططات على نقاط البيانات والتحكم بها تُحدث فرقًا كبيرًا. مع Aspose.Slides لجافا، يمكنك تحويل مخططاتك إلى عناصر ديناميكية وجذابة بصريًا.

## المتطلبات الأساسية

قبل أن نتعمق في جزء الترميز، تأكد من أن لديك المتطلبات الأساسية التالية:

- بيئة تطوير جافا
- Aspose.Slides لمكتبة Java
- بيئة تطوير متكاملة بلغة Java (IDE)
- نموذج مستند عرض تقديمي (على سبيل المثال، "Test.pptx")

## الخطوة 1: إعداد البيئة

أولاً، تأكد من تثبيت الأدوات اللازمة وتجهيزها. أنشئ مشروع جافا في بيئة التطوير المتكاملة (IDE) لديك، واستورد مكتبة Aspose.Slides for Java.

## الخطوة 2: تحميل العرض التقديمي

للبدء، حمّل نموذج عرضك التقديمي. في الكود المُرفق، نفترض أن اسم الملف هو "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## الخطوة 3: إنشاء مخطط بياني

الآن، لنُنشئ مخططًا للعرض التقديمي. سنستخدم مخططًا خطيًا مع علامات في هذا المثال.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## الخطوة 4: العمل مع بيانات الرسم البياني

لمعالجة بيانات المخطط، نحتاج إلى الوصول إلى مصنف بيانات المخطط وإعداد سلسلة البيانات. سنمسح السلسلة الافتراضية ونضيف بياناتنا المخصصة.

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

// كرر ذلك لنقاط البيانات الأخرى
// ...

// تغيير حجم علامة سلسلة الرسم البياني
series.getMarker().setSize(15);
```

## الخطوة 6: حفظ العرض التقديمي

بمجرد تخصيص علامات الرسم البياني، احفظ العرض التقديمي لرؤية التغييرات أثناء العمل.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لخيارات علامة الرسم البياني على نقطة البيانات في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//إنشاء الرسم البياني الافتراضي
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//الحصول على فهرس ورقة عمل بيانات الرسم البياني الافتراضية
int defaultWorksheetIndex = 0;
//الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//حذف سلسلة العروض التوضيحية
chart.getChartData().getSeries().clear();
//إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//ضبط الصورة
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//ضبط الصورة
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//خذ أول سلسلة مخططات
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

مع Aspose.Slides لجافا، يمكنك الارتقاء بعروضك التقديمية من خلال تخصيص علامات المخططات على نقاط البيانات. يتيح لك هذا إنشاء شرائح بصرية مبهرة وغنية بالمعلومات تجذب جمهورك.

## الأسئلة الشائعة

### كيف يمكنني تغيير حجم العلامة لنقاط البيانات؟

لتغيير حجم العلامة لنقاط البيانات، استخدم `series.getMarker().setSize()` الطريقة وتوفير الحجم المطلوب كحجة.

### هل يمكنني استخدام الصور كعلامات مخصصة؟

نعم، يمكنك استخدام الصور كعلامات مخصصة لنقاط البيانات. اضبط نوع التعبئة على `FillType.Picture` وتوفير الصورة التي تريد استخدامها.

### هل Aspose.Slides for Java مناسب لإنشاء مخططات ديناميكية؟

بالتأكيد! يوفر Aspose.Slides for Java إمكانيات واسعة لإنشاء مخططات ديناميكية وتفاعلية في عروضك التقديمية.

### هل يمكنني تخصيص جوانب أخرى من الرسم البياني باستخدام Aspose.Slides؟

نعم، يمكنك تخصيص جوانب مختلفة من الرسم البياني، بما في ذلك العناوين، والمحاور، وعلامات البيانات، والمزيد، باستخدام Aspose.Slides لـ Java.

### أين يمكنني الوصول إلى وثائق Aspose.Slides for Java والتنزيلات؟

يمكنك العثور على الوثائق في [هنا](https://reference.aspose.com/slides/java/) وتحميل المكتبة من [هنا](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
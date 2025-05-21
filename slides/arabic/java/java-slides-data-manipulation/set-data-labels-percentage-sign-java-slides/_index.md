---
"description": "تعلّم كيفية تعيين تسميات البيانات بعلامات النسبة المئوية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. أنشئ مخططات بيانية جذابة مع إرشادات خطوة بخطوة وشيفرة المصدر."
"linktitle": "تعيين نسب تسميات البيانات تسجيل الدخول إلى شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين نسب تسميات البيانات تسجيل الدخول إلى شرائح Java"
"url": "/ar/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين نسب تسميات البيانات تسجيل الدخول إلى شرائح Java


## مقدمة لتعيين نسب تسميات البيانات تسجيل الدخول إلى Aspose.Slides لـ Java

في هذا الدليل، سنشرح لك عملية إعداد تسميات البيانات بعلامة النسبة المئوية باستخدام Aspose.Slides لجافا. سننشئ عرضًا تقديميًا في PowerPoint بمخطط عمودي مكدس، ونُهيئ تسميات البيانات لعرض النسب المئوية.

## المتطلبات الأساسية

قبل البدء، تأكد من إضافة مكتبة Aspose.Slides لجافا إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، نقوم بإنشاء عرض تقديمي جديد في PowerPoint باستخدام Aspose.Slides.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة شريحة ومخطط

بعد ذلك، نضيف شريحة ومخططًا عموديًا مكدسًا إلى العرض التقديمي.

```java
// احصل على مرجع الشريحة
ISlide slide = presentation.getSlides().get_Item(0);

// إضافة مخطط PercentsStackedColumn إلى شريحة
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## الخطوة 3: تكوين تنسيق أرقام المحور

لعرض النسب المئوية، نحتاج إلى تكوين تنسيق الأرقام للمحور الرأسي للرسم البياني.

```java
// تعيين NumberFormatLinkedToSource إلى false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## الخطوة 4: إضافة بيانات الرسم البياني

نضيف البيانات إلى الرسم البياني بإنشاء سلاسل ونقاط بيانات. في هذا المثال، نضيف سلسلتين مع نقاط بياناتهما.

```java
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// إضافة سلسلة جديدة
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// إضافة سلسلة جديدة
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## الخطوة 5: تخصيص تسميات البيانات

الآن، دعونا نقوم بتخصيص مظهر تسميات البيانات.

```java
// إعداد خصائص LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## الخطوة 6: حفظ العرض التقديمي

وأخيرًا، نحفظ العرض التقديمي في ملف PowerPoint.

```java
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء عرض تقديمي على PowerPoint بمخطط عمودي مكدس، وقمت بتكوين تسميات البيانات لعرض النسب المئوية باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل لمجموعة تسميات البيانات النسبة المئوية تسجيل الدخول إلى شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// احصل على مرجع الشريحة
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط PercentsStackedColumn إلى شريحة
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// تعيين NumberFormatLinkedToSource إلى false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// إضافة سلسلة جديدة
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// ضبط لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// إعداد خصائص LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// إضافة سلسلة جديدة
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// ضبط نوع التعبئة واللون
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## خاتمة

من خلال اتباع هذا الدليل، ستتعلم كيفية إنشاء عروض تقديمية جذابة باستخدام تسميات بيانات تعتمد على النسبة المئوية، وهو ما قد يكون مفيدًا بشكل خاص في نقل المعلومات بشكل فعال في التقارير التجارية والمواد التعليمية والمزيد.

## الأسئلة الشائعة

### كيف يمكنني تغيير ألوان سلسلة الرسم البياني؟

يمكنك تغيير لون تعبئة سلسلة الرسم البياني باستخدام `setFill` الطريقة كما هو موضح في المثال.

### هل يمكنني تخصيص حجم الخط لملصقات البيانات؟

نعم، يمكنك تخصيص حجم الخط الخاص بعلامات البيانات عن طريق ضبط `setFontHeight` الخاصية كما هو موضح في الكود.

### كيف يمكنني إضافة المزيد من السلاسل إلى الرسم البياني؟

يمكنك إضافة سلسلة إضافية إلى الرسم البياني باستخدام `add` الطريقة على `IChartSeriesCollection` هدف.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
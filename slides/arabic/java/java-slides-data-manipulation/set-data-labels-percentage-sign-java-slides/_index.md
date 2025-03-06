---
title: تعيين النسبة المئوية لتسميات البيانات، تسجيل الدخول إلى شرائح Java
linktitle: تعيين النسبة المئوية لتسميات البيانات، تسجيل الدخول إلى شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين تسميات البيانات بعلامات النسبة المئوية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. قم بإنشاء مخططات جذابة مع إرشادات خطوة بخطوة وكود المصدر.
type: docs
weight: 17
url: /ar/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## مقدمة لتعيين النسبة المئوية لتسميات البيانات تسجيل الدخول Aspose.Slides لـ Java

في هذا الدليل، سنرشدك خلال عملية تعيين تسميات البيانات بعلامة النسبة المئوية باستخدام Aspose.Slides لـ Java. سنقوم بإنشاء عرض تقديمي لبرنامج PowerPoint باستخدام مخطط عمودي مكدس وتكوين تسميات البيانات لعرض النسب المئوية.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من إضافة مكتبة Aspose.Slides for Java إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، نقوم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint باستخدام Aspose.Slides.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة شريحة ومخطط

بعد ذلك، نضيف شريحة ومخططًا عموديًا مكدسًا إلى العرض التقديمي.

```java
// الحصول على مرجع الشريحة
ISlide slide = presentation.getSlides().get_Item(0);

// إضافة مخطط PercentsStackedColumn على الشريحة
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## الخطوة 3: تكوين تنسيق رقم المحور

لعرض النسب المئوية، نحتاج إلى تكوين تنسيق الأرقام للمحور الرأسي للمخطط.

```java
// اضبط NumberFormatLinkedToSource على خطأ
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## الخطوة 4: إضافة بيانات المخطط

نضيف البيانات إلى المخطط عن طريق إنشاء نقاط متسلسلة وبيانات. في هذا المثال، نضيف سلسلتين مع نقاط البيانات الخاصة بكل منهما.

```java
// الحصول على ورقة عمل بيانات المخطط
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

الآن، دعونا نخصص مظهر تسميات البيانات.

```java
// تحديد خصائص تنسيق التسمية
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

## الخطوة 6: احفظ العرض التقديمي

وأخيرا، نقوم بحفظ العرض التقديمي في ملف PowerPoint.

```java
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء عرض تقديمي لـ PowerPoint باستخدام مخطط عمودي مكدس وتسميات البيانات التي تم تكوينها لعرض النسب المئوية باستخدام Aspose.Slides لـ Java.

## أكمل كود المصدر لتعيين تسميات البيانات والنسبة المئوية لتسجيل الدخول في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// الحصول على مرجع الشريحة
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط PercentsStackedColumn على الشريحة
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// اضبط NumberFormatLinkedToSource على خطأ
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// إضافة سلسلة جديدة
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// ضبط لون تعبئة السلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// تحديد خصائص تنسيق التسمية
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
// تحديد نوع التعبئة واللون
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

باتباع هذا الدليل، تعلمت كيفية إنشاء عروض تقديمية جذابة باستخدام تسميات البيانات المستندة إلى النسبة المئوية، والتي يمكن أن تكون مفيدة بشكل خاص لنقل المعلومات بشكل فعال في تقارير الأعمال والمواد التعليمية والمزيد.

## الأسئلة الشائعة

### كيف يمكنني تغيير ألوان سلسلة المخططات؟

 يمكنك تغيير لون تعبئة سلسلة المخططات باستخدام`setFill` الطريقة كما هو موضح في المثال

### هل يمكنني تخصيص حجم خط تسميات البيانات؟

نعم، يمكنك تخصيص حجم خط تسميات البيانات عن طريق تعيين`setFontHeight` الخاصية كما هو موضح في الكود.

### كيف يمكنني إضافة المزيد من السلاسل إلى المخطط؟

 يمكنك إضافة سلسلة إضافية إلى المخطط باستخدام`add` الطريقة على`IChartSeriesCollection` هدف.

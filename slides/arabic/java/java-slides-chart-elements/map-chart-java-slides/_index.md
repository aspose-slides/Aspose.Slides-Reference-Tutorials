---
title: مخطط الخريطة في شرائح جافا
linktitle: مخطط الخريطة في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بإنشاء مخططات خريطة مذهلة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة والكود المصدري لمطوري Java.
type: docs
weight: 15
url: /ar/java/chart-elements/map-chart-java-slides/
---

## مقدمة إلى مخطط الخريطة في شرائح Java باستخدام Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط خريطة في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. تعد مخططات الخرائط طريقة رائعة لتصور البيانات الجغرافية في عروضك التقديمية.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من دمج مكتبة Aspose.Slides for Java في مشروع Java الخاص بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: قم بإعداد مشروعك

تأكد من قيامك بإعداد مشروع Java الخاص بك وإضافة مكتبة Aspose.Slides for Java إلى مسار الفصل الخاص بمشروعك.

## الخطوة 2: إنشاء عرض تقديمي ل PowerPoint

أولاً، لنقم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## الخطوة 3: إضافة مخطط الخريطة

الآن، سنقوم بإضافة مخطط خريطة إلى العرض التقديمي.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## الخطوة 4: إضافة البيانات إلى مخطط الخريطة

دعونا نضيف بعض البيانات إلى مخطط الخريطة. سنقوم بإنشاء سلسلة وإضافة نقاط البيانات إليها.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## الخطوة 5: إضافة الفئات

نحتاج إلى إضافة فئات إلى مخطط الخريطة، تمثل مناطق جغرافية مختلفة.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## الخطوة 6: تخصيص نقاط البيانات

يمكنك تخصيص نقاط البيانات الفردية. في هذا المثال، نقوم بتغيير لون وقيمة نقطة بيانات محددة.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## الخطوة 7: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام مخطط الخريطة.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

هذا كل شيء! لقد قمت بإنشاء مخطط خريطة في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكنك تخصيص المخطط بشكل أكبر واستكشاف الميزات الأخرى التي تقدمها Aspose.Slides لتحسين العروض التقديمية الخاصة بك.

## أكمل كود المصدر لمخطط الخريطة في شرائح جافا

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//إنشاء مخطط فارغ
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//أضف سلسلة ونقاط بيانات قليلة
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//إضافة فئات
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//تغيير قيمة نقطة البيانات
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//تعيين مظهر نقطة البيانات
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا عملية إنشاء مخطط خريطة في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. تعد مخططات الخرائط طريقة فعالة لتصور البيانات الجغرافية، مما يجعل عروضك التقديمية أكثر جاذبية وغنية بالمعلومات. دعونا نلخص الخطوات الرئيسية:

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع مخطط الخريطة؟

 يمكنك تغيير نوع المخطط عن طريق الاستبدال`ChartType.Map` بنوع المخطط المطلوب عند إنشاء المخطط في الخطوة 3.

### كيف يمكنني تخصيص مظهر مخطط الخريطة؟

 يمكنك تخصيص مظهر المخطط عن طريق تعديل خصائص الملف`dataPoint` الكائن في الخطوة 6. يمكنك تغيير الألوان والقيم والمزيد.

### هل يمكنني إضافة المزيد من نقاط البيانات والفئات؟

 نعم، يمكنك إضافة أي عدد من نقاط البيانات والفئات حسب الحاجة. ببساطة استخدم`series.getDataPoints().addDataPointForMapSeries()` و`chart.getChartData().getCategories().add()` طرق إضافتها.

### كيف يمكنني دمج Aspose.Slides for Java في مشروعي؟

 تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/) وإضافته إلى مسار الفصل الخاص بمشروعك.
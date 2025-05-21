---
"description": "أنشئ مخططات خرائط مذهلة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة وشيفرة المصدر لمطوري جافا."
"linktitle": "مخطط الخريطة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط الخريطة في شرائح Java"
"url": "/ar/java/chart-elements/map-chart-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط الخريطة في شرائح Java


## مقدمة إلى مخطط الخريطة في شرائح Java باستخدام Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط خريطة في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُعد مخططات الخرائط وسيلة رائعة لعرض البيانات الجغرافية في عروضك التقديمية.

## المتطلبات الأساسية

قبل البدء، تأكد من دمج مكتبة Aspose.Slides لجافا في مشروع جافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد مشروعك

تأكد من إعداد مشروع Java الخاص بك وإضافة مكتبة Aspose.Slides for Java إلى مسار فئة مشروعك.

## الخطوة 2: إنشاء عرض تقديمي في PowerPoint

أولاً، دعنا ننشئ عرض تقديمي جديد في PowerPoint.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## الخطوة 3: إضافة مخطط خريطة

الآن، سنضيف مخطط الخريطة إلى العرض التقديمي.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## الخطوة 4: إضافة البيانات إلى مخطط الخريطة

لنُضِف بعض البيانات إلى مخطط الخريطة. سنُنشئ سلسلة ونُضيف إليها نقاط بيانات.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## الخطوة 5: إضافة الفئات

نحن بحاجة إلى إضافة فئات إلى مخطط الخريطة، تمثل مناطق جغرافية مختلفة.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## الخطوة 6: تخصيص نقاط البيانات

يمكنك تخصيص نقاط بيانات فردية. في هذا المثال، نغيّر لون وقيمة نقطة بيانات محددة.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## الخطوة 7: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع مخطط الخريطة.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

هذا كل شيء! لقد أنشأتَ مخططًا لخريطة في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يمكنك تخصيص المخطط بشكل أكبر واستكشاف ميزات أخرى يقدمها Aspose.Slides لتحسين عروضك التقديمية.

## كود المصدر الكامل لرسم الخرائط في شرائح Java

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//إنشاء مخطط فارغ
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//أضف سلسلة وعدد قليل من نقاط البيانات
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

في هذا البرنامج التعليمي، شرحنا عملية إنشاء مخطط خريطة في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُعد مخططات الخرائط طريقة فعّالة لعرض البيانات الجغرافية، مما يجعل عروضك التقديمية أكثر تشويقًا وإثراءً بالمعلومات. لنلخص الخطوات الرئيسية:

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع مخطط الخريطة؟

يمكنك تغيير نوع الرسم البياني عن طريق استبدال `ChartType.Map` مع نوع الرسم البياني المطلوب عند إنشاء الرسم البياني في الخطوة 3.

### كيف يمكنني تخصيص مظهر مخطط الخريطة؟

يمكنك تخصيص مظهر الرسم البياني عن طريق تعديل خصائصه `dataPoint` الكائن في الخطوة 6. يمكنك تغيير الألوان والقيم والمزيد.

### هل يمكنني إضافة المزيد من نقاط البيانات والفئات؟

نعم، يمكنك إضافة أي عدد من نقاط البيانات والفئات حسب الحاجة. ببساطة، استخدم `series.getDataPoints().addDataPointForMapSeries()` و `chart.getChartData().getCategories().add()` طرق لإضافتها.

### كيف يمكنني دمج Aspose.Slides for Java في مشروعي؟

تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/) وأضفه إلى مسار مشروعك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
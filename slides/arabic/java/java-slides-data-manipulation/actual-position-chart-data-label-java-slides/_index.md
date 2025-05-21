---
"description": "تعرّف على كيفية الحصول على الموضع الفعلي لعلامات بيانات المخططات في شرائح جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "الحصول على الموضع الفعلي لملصق بيانات الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الحصول على الموضع الفعلي لملصق بيانات الرسم البياني في شرائح Java"
"url": "/ar/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على الموضع الفعلي لملصق بيانات الرسم البياني في شرائح Java


## مقدمة للحصول على الموضع الفعلي لعلامة بيانات الرسم البياني في شرائح Java

في هذا البرنامج التعليمي، ستتعلم كيفية استرجاع الموضع الفعلي لعلامات بيانات المخطط باستخدام Aspose.Slides لجافا. سننشئ برنامج جافا يُنشئ عرضًا تقديميًا في PowerPoint يحتوي على مخطط، ويُخصص علامات البيانات، ثم يُضيف أشكالًا تُمثل مواضع هذه العلامات.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من إعداد مكتبة Aspose.Slides for Java في مشروع Java الخاص بك.

## الخطوة 1: إنشاء عرض تقديمي في PowerPoint

أولاً، لنُنشئ عرضًا تقديميًا جديدًا في PowerPoint ونُضيف إليه مخططًا بيانيًا. سنُخصص تسميات بيانات المخطط لاحقًا في هذا البرنامج التعليمي.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## الخطوة 2: تخصيص تسميات البيانات
الآن، لنُخصّص تسميات البيانات لسلسلة المخططات. سنُحدّد موقعها ونعرض قيمها.

```java
try {
    // ... (الكود السابق)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (الرمز المتبقي)
} finally {
    if (pres != null) pres.dispose();
}
```

## الخطوة 3: الحصول على الموضع الفعلي لعلامات البيانات
في هذه الخطوة، سوف نكرر نقاط البيانات في سلسلة الرسم البياني ونسترد الموضع الفعلي لعلامات البيانات التي تحتوي على قيمة أكبر من 4. سنضيف بعد ذلك علامات حذف لتمثيل هذه المواضع.

```java
try {
    // ... (الكود السابق)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (الرمز المتبقي)
} finally {
    if (pres != null) pres.dispose();
}
```

## الخطوة 4: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الناتج في ملف.

```java
try {
    // ... (الكود السابق)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## كود المصدر الكامل للحصول على الموضع الفعلي لملصق بيانات الرسم البياني في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//المهام
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استرجاع الموضع الفعلي لعناوين بيانات المخططات في شرائح جافا باستخدام Aspose.Slides لجافا. يمكنك الآن استخدام هذه المعرفة لتحسين عروض PowerPoint التقديمية بإضافة عناوين بيانات مخصصة وتمثيلات مرئية لمواضعها.

## الأسئلة الشائعة

### كيف يمكنني تخصيص تسميات البيانات في الرسم البياني؟

لتخصيص تسميات البيانات في مخطط، يمكنك استخدام `setDefaultDataLabelFormat` استخدم طريقةً لسلسلة المخططات، واضبط خصائص مثل الموضع والرؤية. على سبيل المثال:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### كيف يمكنني إضافة أشكال لتمثيل مواضع تسميات البيانات؟

يمكنك تكرار نقاط البيانات لسلسلة الرسم البياني واستخدامها `getActualX`، `getActualY`، `getActualWidth`، و `getActualHeight` استخدم أساليب تسمية البيانات لتحديد موقعها. بعد ذلك، يمكنك إضافة الأشكال باستخدام `addAutoShape` الطريقة. إليك مثال:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### كيف يمكنني حفظ العرض التقديمي الناتج؟

يمكنك حفظ العرض التقديمي الناتج باستخدام `save` الطريقة. قم بتوفير مسار الملف المطلوب و `SaveFormat` كمعلمات. على سبيل المثال:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
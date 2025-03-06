---
title: احصل على الموضع الفعلي لتسمية بيانات المخطط في شرائح Java
linktitle: احصل على الموضع الفعلي لتسمية بيانات المخطط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية الحصول على الموضع الفعلي لتسميات بيانات المخطط في Java Slides باستخدام Aspose.Slides for Java. دليل خطوة بخطوة مع كود المصدر.
weight: 18
url: /ar/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة للحصول على الموضع الفعلي لتسمية بيانات المخطط في شرائح Java

في هذا البرنامج التعليمي، ستتعلم كيفية استرداد الموضع الفعلي لتسميات بيانات المخطط باستخدام Aspose.Slides لـ Java. سنقوم بإنشاء برنامج Java الذي يقوم بإنشاء عرض تقديمي لـ PowerPoint مع مخطط، وتخصيص تسميات البيانات، ثم إضافة أشكال تمثل مواضع تسميات البيانات هذه.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من إعداد مكتبة Aspose.Slides for Java في مشروع Java الخاص بك.

## الخطوة 1: إنشاء عرض تقديمي لـ PowerPoint

أولاً، لنقم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint ونضيف إليه مخططًا. سنقوم بتخصيص تسميات بيانات المخطط لاحقًا في البرنامج التعليمي.

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
الآن، دعونا نخصص تسميات البيانات لسلسلة المخططات. سوف نقوم بتعيين موقفهم وإظهار القيم.

```java
try {
    // ... (الكود السابق)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ...(الرمز المتبقي)
} finally {
    if (pres != null) pres.dispose();
}
```

## الخطوة 3: احصل على الموضع الفعلي لتسميات البيانات
في هذه الخطوة، سنقوم بالتكرار عبر نقاط البيانات في سلسلة المخططات واسترداد الموضع الفعلي لتسميات البيانات التي لها قيمة أكبر من 4. وسنقوم بعد ذلك بإضافة علامات الحذف لتمثيل هذه المواضع.

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
    // ...(الرمز المتبقي)
} finally {
    if (pres != null) pres.dispose();
}
```

## الخطوة 4: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الذي تم إنشاؤه في ملف.

```java
try {
    // ... (الكود السابق)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## أكمل كود المصدر للحصول على الموضع الفعلي لتسمية بيانات المخطط في شرائح Java

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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//لكى يفعل
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

في هذا البرنامج التعليمي، تعلمت كيفية استرداد الموضع الفعلي لتسميات بيانات المخطط في Java Slides باستخدام Aspose.Slides لـ Java. يمكنك الآن استخدام هذه المعرفة لتحسين عروض PowerPoint التقديمية الخاصة بك باستخدام تسميات البيانات المخصصة والتمثيلات المرئية لمواقعها.

## الأسئلة الشائعة

### كيف يمكنني تخصيص تسميات البيانات في المخطط؟

 لتخصيص تسميات البيانات في مخطط، يمكنك استخدام`setDefaultDataLabelFormat` الطريقة في سلسلة المخططات وتعيين خصائص مثل الموضع والرؤية. على سبيل المثال:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### كيف يمكنني إضافة أشكال لتمثيل مواضع تسمية البيانات؟

 يمكنك التكرار من خلال نقاط البيانات الخاصة بسلسلة المخططات واستخدام`getActualX`, `getActualY`, `getActualWidth` ، و`getActualHeight`طرق تسمية البيانات للحصول على موقفها. وبعد ذلك، يمكنك إضافة أشكال باستخدام`addAutoShape` طريقة. هنا مثال:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### كيف يمكنني حفظ العرض التقديمي الذي تم إنشاؤه؟

 يمكنك حفظ العرض التقديمي الذي تم إنشاؤه باستخدام`save` طريقة. توفير مسار الملف المطلوب و`SaveFormat` كمعلمات. على سبيل المثال:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

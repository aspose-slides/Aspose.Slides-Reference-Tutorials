---
"description": "تعلم كيفية إنشاء مخططات بيانية رائعة وإدارة خصائص شرائح جافا باستخدام Aspose.Slides. دليل خطوة بخطوة مع الكود المصدري لعروض تقديمية فعّالة."
"linktitle": "إدارة مخططات الخصائص في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إدارة مخططات الخصائص في شرائح Java"
"url": "/ar/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إدارة مخططات الخصائص في شرائح Java


## مقدمة لإدارة الخصائص والرسوم البيانية في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنستكشف كيفية إدارة الخصائص وإنشاء المخططات البيانية في شرائح جافا باستخدام Aspose.Slides. Aspose.Slides هي واجهة برمجة تطبيقات جافا فعّالة للعمل مع عروض PowerPoint التقديمية. سنشرح العملية خطوة بخطوة، بما في ذلك أمثلة على الكود المصدري.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## إضافة مخطط إلى شريحة

لإضافة مخطط إلى شريحة، اتبع الخطوات التالية:

1. قم باستيراد الفئات اللازمة وإنشاء مثيل لفئة العرض التقديمي.

```java
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

2. انتقل إلى الشريحة التي تريد إضافة الرسم البياني إليها. في هذا المثال، ننتقل إلى الشريحة الأولى.

```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```

3. أضف مخططًا ببيانات افتراضية. في هذه الحالة، نضيف مخططًا ثلاثي الأبعاد StackedColumn.

```java
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## إعداد بيانات الرسم البياني

لضبط بيانات الرسم البياني، نحتاج إلى إنشاء مصنف بيانات الرسم البياني وإضافة سلاسل وفئات. اتبع الخطوات التالية:

4. تعيين فهرس ورقة بيانات الرسم البياني.

```java
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
```

5. احصل على مصنف بيانات الرسم البياني.

```java
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. أضف سلسلة إلى الرسم البياني. في هذا المثال، نضيف سلسلتين باسم "السلسلة ١" و"السلسلة ٢".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. أضف فئات إلى المخطط. هنا، نضيف ثلاث فئات.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ضبط خصائص الدوران ثلاثي الأبعاد

الآن، دعنا نحدد خصائص الدوران ثلاثي الأبعاد للرسم البياني:

8. ضبط محاور الزاوية القائمة.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. اضبط زوايا الدوران لمحوري X وY. في هذا المثال، نقوم بتدوير X بمقدار 40 درجة وY بمقدار 270 درجة.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. ضبط نسبة العمق إلى 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## ملء بيانات السلسلة

11. خذ سلسلة المخططات الثانية وقم بملئها بنقاط البيانات.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ضبط التداخل

12. حدّد قيمة التداخل للسلسلة. على سبيل المثال، يمكنك ضبطها على ١٠٠ لعدم وجود تداخل.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي على القرص.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط عمودي ثلاثي الأبعاد بخصائص مخصصة باستخدام Aspose.Slides في Java.

## كود المصدر الكامل لإدارة مخططات الخصائص في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// إضافة سلسلة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// إضافة الفئات
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// تعيين خصائص Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// خذ سلسلة الرسم البياني الثانية
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// تعيين قيمة التداخل
series.getParentSeriesGroup().setOverlap((byte) 100);
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعمقنا في عالم إدارة الخصائص وإنشاء المخططات البيانية في شرائح جافا باستخدام Aspose.Slides. Aspose.Slides هي واجهة برمجة تطبيقات Java فعّالة تُمكّن المطورين من العمل مع عروض PowerPoint التقديمية بكفاءة. غطينا الخطوات الأساسية وقدمنا أمثلة على الكود المصدري لإرشادك خلال العملية.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

يمكنك تغيير نوع الرسم البياني عن طريق تعديل `ChartType` عند إضافة المخطط، راجع وثائق Aspose.Slides للاطلاع على أنواع المخططات المتاحة.

### هل يمكنني تخصيص ألوان الرسم البياني؟

نعم، يمكنك تخصيص ألوان الرسم البياني عن طريق تعيين خصائص التعبئة لنقاط البيانات أو الفئات المتسلسلة.

### كيف يمكنني إضافة المزيد من نقاط البيانات إلى سلسلة؟

يمكنك إضافة المزيد من نقاط البيانات إلى سلسلة باستخدام `series.getDataPoints().addDataPointForBarSeries()` الطريقة وتحديد الخلية التي تحتوي على قيمة البيانات.

### كيف يمكنني ضبط زاوية دوران مختلفة؟

لتعيين زاوية دوران مختلفة لمحوري X وY، استخدم `chart.getRotation3D().setRotationX()` و `chart.getRotation3D().setRotationY()` مع قيم الزاوية المطلوبة.

### ما هي خصائص ثلاثية الأبعاد الأخرى التي يمكنني تخصيصها؟

يمكنك استكشاف خصائص ثلاثية الأبعاد أخرى للرسم البياني، مثل العمق والمنظور والإضاءة، من خلال الرجوع إلى وثائق Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
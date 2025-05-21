---
"description": "تعلّم كيفية إنشاء مخططات دائرية ديناميكية بألوان شرائح تلقائية في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "ضبط ألوان شرائح المخطط الدائري تلقائيًا في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ضبط ألوان شرائح المخطط الدائري تلقائيًا في شرائح Java"
"url": "/ar/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ضبط ألوان شرائح المخطط الدائري تلقائيًا في شرائح Java


## مقدمة لتعيين ألوان شرائح المخطط الدائري التلقائية في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء مخطط دائري في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا، وتعيين ألوان الشرائح تلقائيًا للمخطط. سنقدم إرشادات خطوة بخطوة مع الكود المصدري.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيل المكتبة من موقع Aspose الإلكتروني: [تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

## الخطوة 1: استيراد الحزم المطلوبة

أولاً، عليك استيراد الحزم اللازمة من Aspose.Slides لـ Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## الخطوة 2: إنشاء عرض تقديمي في PowerPoint

إنشاء مثيل `Presentation` الفصل لإنشاء عرض تقديمي جديد في PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## الخطوة 3: إضافة شريحة

انتقل إلى الشريحة الأولى من العرض التقديمي وأضف إليها مخططًا بالبيانات الافتراضية:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## الخطوة 4: تعيين عنوان الرسم البياني

تعيين عنوان للرسم البياني:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## الخطوة 5: تكوين بيانات الرسم البياني

قم بضبط الرسم البياني لإظهار القيم للسلسلة الأولى وقم بتكوين بيانات الرسم البياني:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## الخطوة 6: إضافة الفئات والسلاسل

إضافة فئات وسلاسل جديدة إلى الرسم البياني:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## الخطوة 7: ملء بيانات السلسلة

ملء بيانات السلسلة للمخطط الدائري:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## الخطوة 8: تمكين ألوان الشريحة المتنوعة

تمكين ألوان شرائح متنوعة لمخطط الفطيرة:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## الخطوة 9: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في ملف PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لتعيين ألوان شرائح الرسم البياني الدائري تلقائيًا في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation presentation = new Presentation();
try
{
	// الوصول إلى الشريحة الأولى
	ISlide slides = presentation.getSlides().get_Item(0);
	// إضافة مخطط بالبيانات الافتراضية
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// عنوان مخطط الإعداد
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// تعيين السلسلة الأولى لإظهار القيم
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// ضبط فهرس ورقة بيانات الرسم البياني
	int defaultWorksheetIndex = 0;
	// الحصول على ورقة عمل بيانات الرسم البياني
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// حذف السلسلة والفئات المولدة افتراضيًا
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// إضافة فئات جديدة
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// إضافة سلسلة جديدة
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// يتم الآن ملء بيانات السلسلة
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

لقد نجحتَ في إنشاء مخطط دائري في عرض تقديمي لبرنامج PowerPoint باستخدام Aspose.Slides لجافا، وقمتَ بتهيئته لعرض ألوان الشرائح تلقائيًا. يوفر لك هذا الدليل التفصيلي الكود المصدري اللازم لتحقيق ذلك. يمكنك تخصيص المخطط والعرض التقديمي حسب الحاجة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص ألوان الشرائح الفردية في المخطط الدائري؟

لتخصيص ألوان الشرائح الفردية في مخطط الفطيرة، يمكنك استخدام `getAutomaticSeriesColors` طريقة لاسترجاع نظام الألوان الافتراضي، ثم تعديل الألوان حسب الحاجة. إليك مثال:

```java
// احصل على مخطط الألوان الافتراضي
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// تعديل الألوان حسب الحاجة
colors.get_Item(0).setColor(Color.RED); // اضبط لون الشريحة الأولى إلى اللون الأحمر
colors.get_Item(1).setColor(Color.BLUE); // اضبط لون الشريحة الثانية إلى اللون الأزرق
// أضف المزيد من تعديلات الألوان حسب الحاجة
```

### كيف يمكنني إضافة أسطورة إلى الرسم البياني الدائري؟

لإضافة أسطورة إلى مخطط الفطيرة، يمكنك استخدام `getLegend` الطريقة وتكوينها على النحو التالي:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // تعيين موضع الأسطورة
legend.setOverlay(true); // عرض الأسطورة فوق الرسم البياني
```

### هل يمكنني تغيير الخط ونمط العنوان؟

نعم، يمكنك تغيير خط ونمط العنوان. استخدم الكود التالي لتعيين خط ونمط العنوان:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // ضبط حجم الخط
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // اجعل العنوان غامقًا
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // اجعل العنوان مائلًا
```

يمكنك تعديل حجم الخط، والخط العريض، والنمط المائل حسب الحاجة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
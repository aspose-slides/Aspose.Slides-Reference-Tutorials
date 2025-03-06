---
title: ضبط ألوان شريحة المخطط الدائري التلقائي في شرائح Java
linktitle: ضبط ألوان شريحة المخطط الدائري التلقائي في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات دائرية ديناميكية بألوان الشرائح التلقائية في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides for Java. دليل خطوة بخطوة مع كود المصدر.
weight: 24
url: /ar/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لإعداد ألوان شريحة المخطط الدائري التلقائي في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء مخطط دائري في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java وتعيين ألوان الشرائح التلقائية للمخطط. سنقدم إرشادات خطوة بخطوة مع كود المصدر.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من موقع Aspose:[تنزيل Aspose.Slides للجافا](https://releases.aspose.com/slides/java/).

## الخطوة 1: استيراد الحزم المطلوبة

أولاً، تحتاج إلى استيراد الحزم الضرورية من Aspose.Slides لـ Java:

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

## الخطوة 2: إنشاء عرض تقديمي ل PowerPoint

 إنشاء مثيل`Presentation` فئة لإنشاء عرض تقديمي جديد لـ PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## الخطوة 3: إضافة شريحة

قم بالوصول إلى الشريحة الأولى من العرض التقديمي وأضف مخططًا إليها بالبيانات الافتراضية:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## الخطوة 4: تعيين عنوان المخطط

تعيين عنوان للمخطط:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## الخطوة 5: تكوين بيانات المخطط

قم بتعيين المخطط لإظهار قيم السلسلة الأولى وتكوين بيانات المخطط:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## الخطوة 6: إضافة الفئات والسلسلة

إضافة فئات وسلاسل جديدة إلى المخطط:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## الخطوة 7: تعبئة بيانات السلسلة

تعبئة بيانات السلسلة للمخطط الدائري:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## الخطوة 8: تمكين ألوان الشرائح المتنوعة

تمكين ألوان الشرائح المتنوعة للمخطط الدائري:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## الخطوة 9: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في ملف PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لإعداد ألوان شريحة المخطط الدائري التلقائي في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation presentation = new Presentation();
try
{
	// الوصول إلى الشريحة الأولى
	ISlide slides = presentation.getSlides().get_Item(0);
	// إضافة مخطط بالبيانات الافتراضية
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// إعداد عنوان المخطط
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// قم بتعيين السلسلة الأولى لإظهار القيم
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// إعداد فهرس ورقة بيانات الرسم البياني
	int defaultWorksheetIndex = 0;
	// الحصول على ورقة عمل بيانات المخطط
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// حذف السلسلة والفئات الافتراضية التي تم إنشاؤها
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// إضافة فئات جديدة
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// إضافة سلسلة جديدة
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// الآن ملء بيانات السلسلة
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

لقد نجحت في إنشاء مخطط دائري في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java وقمت بتكوينه بحيث يحتوي على ألوان شرائح تلقائية. يوفر لك هذا الدليل خطوة بخطوة التعليمات البرمجية المصدر اللازمة لتحقيق ذلك. يمكنك أيضًا تخصيص المخطط والعرض التقديمي حسب الحاجة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص ألوان الشرائح الفردية في المخطط الدائري؟

 لتخصيص ألوان الشرائح الفردية في المخطط الدائري، يمكنك استخدام`getAutomaticSeriesColors` طريقة لاسترداد نظام الألوان الافتراضي ومن ثم تعديل الألوان حسب الحاجة. هنا مثال:

```java
//احصل على نظام الألوان الافتراضي
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// تعديل الألوان حسب الحاجة
colors.get_Item(0).setColor(Color.RED); // اضبط لون الشريحة الأولى على اللون الأحمر
colors.get_Item(1).setColor(Color.BLUE); // اضبط لون الشريحة الثانية على اللون الأزرق
// أضف المزيد من تعديلات الألوان حسب الحاجة
```

### كيف يمكنني إضافة وسيلة إيضاح إلى المخطط الدائري؟

 لإضافة وسيلة إيضاح إلى المخطط الدائري، يمكنك استخدام`getLegend` الطريقة وتكوينها على النحو التالي:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // اضبط موضع الأسطورة
legend.setOverlay(true); // عرض وسيلة الإيضاح على الرسم البياني
```

### هل يمكنني تغيير خط العنوان ونمطه؟

نعم، يمكنك تغيير خط العنوان ونمطه. استخدم الكود التالي لتعيين خط العنوان ونمطه:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // ضبط حجم الخط
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // اجعل العنوان غامقًا
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // اجعل العنوان مائلًا
```

يمكنك ضبط حجم الخط والخط والنمط المائل حسب الحاجة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

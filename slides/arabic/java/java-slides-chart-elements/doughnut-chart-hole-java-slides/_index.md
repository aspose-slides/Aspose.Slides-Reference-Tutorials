---
"description": "أنشئ مخططات دائرية بأحجام فتحات مخصصة في شرائح جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لتخصيص المخطط."
"linktitle": "ثقب مخطط الدونات في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ثقب مخطط الدونات في شرائح جافا"
"url": "/ar/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ثقب مخطط الدونات في شرائح جافا


## مقدمة إلى مخطط الدونات مع وجود ثقب في شرائح جافا

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط دائري مثقوب باستخدام Aspose.Slides لجافا. سيشرح لك هذا الدليل خطوة بخطوة العملية مع أمثلة من الكود المصدري.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيلها من [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

## الخطوة 1: استيراد المكتبات المطلوبة

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## الخطوة 2: تهيئة العرض التقديمي

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 3: إنشاء مخطط الكعكة الدائرية

```java
try {
    // إنشاء مخطط دائري على الشريحة الأولى
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // ضبط حجم الفتحة في مخطط الدونات (بالنسبة المئوية)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // حفظ العرض التقديمي على القرص
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // التخلص من كائن العرض
    if (presentation != null) presentation.dispose();
}
```

## الخطوة 4: تشغيل الكود

شغّل كود جافا في بيئة التطوير المتكاملة (IDE) أو محرر النصوص لإنشاء مخطط دائري بحجم ثقب محدد. تأكد من استبدال `"Your Document Directory"` مع المسار الفعلي الذي تريد حفظ العرض التقديمي فيه.

## كود المصدر الكامل لثقب مخطط الدونات في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// كتابة العرض التقديمي على القرص
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط دائري بفتحة باستخدام Aspose.Slides لجافا. يمكنك تخصيص حجم الفتحة بتعديل `setDoughnutHoleSize` معلمة الطريقة.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون أجزاء الرسم البياني؟

لتغيير لون أجزاء الرسم البياني، يمكنك استخدام `setDataPointsInLegend` الطريقة على `IChart` الكائن وتعيين اللون المطلوب لكل نقطة بيانات.

### هل يمكنني إضافة تسميات إلى أجزاء الرسم البياني الدائري؟

نعم، يمكنك إضافة تسميات إلى أجزاء مخطط الدونات باستخدام `setDataPointsLabelValue` الطريقة على `IChart` هدف.

### هل من الممكن إضافة عنوان للرسم البياني؟

بالتأكيد! يمكنك إضافة عنوان للرسم البياني باستخدام `setTitle` الطريقة على `IChart` الكائن وتوفير نص العنوان المطلوب.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: ثقب الرسم البياني الدائري في شرائح جافا
linktitle: ثقب الرسم البياني الدائري في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بإنشاء مخططات دائرية بأحجام فتحات مخصصة في شرائح Java باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع الكود المصدري لتخصيص المخطط.
weight: 11
url: /ar/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة إلى المخطط الدائري المجوف مع وجود ثقب في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال إنشاء مخطط دائري مجوف به فتحة باستخدام Aspose.Slides لـ Java. سيرشدك هذا الدليل خطوة بخطوة خلال العملية مع أمثلة التعليمات البرمجية المصدر.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تنزيله من[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).

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

## الخطوة 3: إنشاء مخطط الكعكة

```java
try {
    // أنشئ مخططًا دائريًا على الشريحة الأولى
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // تعيين حجم الثقب في المخطط الدائري المجوف (بالنسبة المئوية)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // احفظ العرض التقديمي على القرص
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // تخلص من كائن العرض التقديمي
    if (presentation != null) presentation.dispose();
}
```

## الخطوة 4: قم بتشغيل الكود

 قم بتشغيل كود Java في IDE أو محرر النصوص الخاص بك لإنشاء مخطط دائري بحجم ثقب محدد. تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي الذي تريد حفظ العرض التقديمي فيه.

## كود المصدر الكامل لفتحة مخطط الدونات في شرائح جافا

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

 في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط دائري مجوف به فتحة باستخدام Aspose.Slides لـ Java. يمكنك تخصيص حجم الثقب عن طريق ضبط`setDoughnutHoleSize` معلمة الطريقة.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون أجزاء الرسم البياني؟

 لتغيير لون أجزاء المخطط، يمكنك استخدام`setDataPointsInLegend` الطريقة على`IChart` الكائن وتعيين اللون المطلوب لكل نقطة بيانات.

### هل يمكنني إضافة تسميات إلى مقاطع المخطط الدائري المجوف؟

 نعم، يمكنك إضافة تسميات إلى مقاطع المخطط الدائري المجوف باستخدام`setDataPointsLabelValue` الطريقة على`IChart` هدف.

### هل من الممكن إضافة عنوان إلى الرسم البياني؟

 بالتأكيد! يمكنك إضافة عنوان إلى المخطط باستخدام`setTitle` الطريقة على`IChart` الكائن وتوفير نص العنوان المطلوب.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

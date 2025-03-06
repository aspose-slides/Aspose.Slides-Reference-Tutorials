---
title: مخطط القمع في شرائح جافا
linktitle: مخطط القمع في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعلم كيفية إنشاء مخططات قمعية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع التعليمات البرمجية المصدر لتصور البيانات بشكل فعال.
weight: 18
url: /ar/java/chart-data-manipulation/funnel-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لإنشاء مخطط قمع في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط قمع في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. تعتبر المخططات القمعية مفيدة لتصور البيانات التي تقوم بتضييق نطاق البيانات أو "المسارات" بشكل تدريجي عبر مراحل أو فئات مختلفة. سنقدم لك تعليمات خطوة بخطوة بالإضافة إلى التعليمات البرمجية المصدر لمساعدتك في تحقيق ذلك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لمكتبة Java وإعدادها في مشروعك.
- ملف عرض تقديمي لـ PowerPoint (PPTX) حيث تريد إدراج المخطط القمعي.

## الخطوة 1: استيراد Aspose.Slides إلى Java

أولاً، تحتاج إلى استيراد مكتبة Aspose.Slides for Java إلى مشروع Java الخاص بك. تأكد من إضافة التبعيات الضرورية إلى تكوين البناء الخاص بك.

```java
import com.aspose.slides.*;
```

## الخطوة 2: تهيئة العرض التقديمي والمخطط

في هذه الخطوة، نقوم بتهيئة عرض تقديمي وإضافة مخطط قمع إلى الشريحة.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    //أضف مخططًا قمعيًا إلى الشريحة الأولى عند الإحداثيات (50، 50) والأبعاد (500، 400).
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## الخطوة 3: تحديد بيانات الرسم البياني

بعد ذلك، نحدد البيانات الخاصة بالمخطط القمعي الخاص بنا. يمكنك تخصيص الفئات ونقاط البيانات وفقًا لمتطلباتك.

```java
// مسح بيانات الرسم البياني الموجودة.
wb.clear(0);

// تحديد فئات للمخطط.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// إضافة نقاط بيانات لسلسلة المخطط القمعي.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، نقوم بحفظ العرض التقديمي مع المخطط القمعي في ملف محدد.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط قمعي باستخدام Aspose.Slides لـ Java وأدرجته في عرض PowerPoint التقديمي.

## أكمل كود المصدر للمخطط القمعي في شرائح Java

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## خاتمة

في هذا الدليل خطوة بخطوة، أوضحنا كيفية إنشاء مخطط قمع في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. تعد المخططات القمعية أداة قيمة لتصور البيانات التي تتبع نمط التقدم أو التضييق، مما يجعل من السهل نقل المعلومات بشكل فعال. 

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر المخطط القمعي؟

يمكنك تخصيص مظهر المخطط القمعي عن طريق تعديل خصائص المخطط المختلفة مثل الألوان والتسميات والأنماط. راجع وثائق Aspose.Slides للحصول على معلومات تفصيلية حول خيارات تخصيص المخطط.

### هل يمكنني إضافة المزيد من نقاط البيانات أو الفئات إلى المخطط القمعي؟

نعم، يمكنك إضافة نقاط بيانات وفئات إضافية إلى المخطط القمعي عن طريق توسيع الكود المقدم في الخطوة 3. ما عليك سوى إضافة المزيد من تسميات الفئات ونقاط البيانات حسب الحاجة.

### كيف يمكنني تغيير موضع وحجم المخطط القمعي على الشريحة؟

يمكنك ضبط موضع وحجم المخطط القمعي عن طريق تعديل الإحداثيات والأبعاد المتوفرة عند إضافة المخطط إلى الشريحة في الخطوة 2. قم بتحديث القيم (50، 50، 500، 400) وفقًا لذلك.

### هل يمكنني تصدير المخطط إلى تنسيقات مختلفة، مثل PDF أو صورة؟

نعم، يتيح لك Aspose.Slides for Java تصدير العرض التقديمي باستخدام Funnel Chart إلى تنسيقات مختلفة، بما في ذلك PDF وتنسيقات الصور والمزيد. يمكنك استخدام ال`SaveFormat` خيارات لتحديد تنسيق الإخراج المطلوب عند حفظ العرض التقديمي.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

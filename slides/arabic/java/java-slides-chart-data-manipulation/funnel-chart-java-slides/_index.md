---
"description": "تعلم كيفية إنشاء مخططات قمعية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لتصور البيانات بفعالية."
"linktitle": "مخطط القمع في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط القمع في شرائح Java"
"url": "/ar/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط القمع في شرائح Java


## مقدمة لإنشاء مخطط قمعي في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط قمعي في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُعدّ المخططات القمعية مفيدة لعرض البيانات بشكل مُفصّل، أو ما يُعرف بـ "القمعات" عبر مراحل أو فئات مُختلفة. سنقدم لك تعليمات خطوة بخطوة مع شفرة المصدر لمساعدتك في تحقيق ذلك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لمكتبة Java وإعدادها في مشروعك.
- ملف عرض تقديمي بتنسيق PowerPoint (PPTX) حيث تريد إدراج مخطط القمع.

## الخطوة 1: استيراد Aspose.Slides لـ Java

أولاً، عليك استيراد مكتبة Aspose.Slides لجافا إلى مشروع جافا. تأكد من إضافة التبعيات اللازمة إلى إعدادات البناء.

```java
import com.aspose.slides.*;
```

## الخطوة 2: تهيئة العرض التقديمي والمخطط

في هذه الخطوة، نقوم بتهيئة العرض التقديمي وإضافة مخطط قمعي إلى الشريحة.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // أضف مخططًا قمعيًا إلى الشريحة الأولى عند الإحداثيات (50، 50) مع الأبعاد (500، 400).
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

بعد ذلك، نُحدد بيانات مخطط القمع. يمكنك تخصيص الفئات ونقاط البيانات وفقًا لاحتياجاتك.

```java
// مسح بيانات الرسم البياني الموجودة.
wb.clear(0);

// تحديد الفئات للرسم البياني.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// أضف نقاط البيانات لسلسلة مخطط القمع.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، نقوم بحفظ العرض التقديمي باستخدام مخطط القمع في ملف محدد.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط قمعي باستخدام Aspose.Slides لجافا، وأدرجته في عرض تقديمي على PowerPoint.

## كود المصدر الكامل لمخطط القمع في شرائح Java

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

في هذا الدليل المُفصّل، شرحنا كيفية إنشاء مخطط قمعي في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُعدّ المخططات القمعية أداة قيّمة لعرض البيانات التي تتبع نمطًا تصاعديًا أو تضييقيًا، مما يُسهّل نقل المعلومات بفعالية. 

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر مخطط القمع؟

يمكنك تخصيص مظهر مخطط القمع عن طريق تعديل خصائصه المختلفة، مثل الألوان والتسميات والأنماط. راجع وثائق Aspose.Slides لمزيد من المعلومات حول خيارات تخصيص المخطط.

### هل يمكنني إضافة المزيد من نقاط البيانات أو الفئات إلى مخطط المبيعات؟

نعم، يمكنك إضافة نقاط بيانات وفئات إضافية إلى مخطط المبيعات عن طريق توسيع الكود المقدم في الخطوة 3. ما عليك سوى إضافة المزيد من تسميات الفئات ونقاط البيانات حسب الحاجة.

### كيف يمكنني تغيير موضع وحجم مخطط القمع على الشريحة؟

يمكنك تعديل موضع وحجم مخطط القمع عن طريق تعديل الإحداثيات والأبعاد المقدمة عند إضافة المخطط إلى الشريحة في الخطوة 2. قم بتحديث القيم (50، 50، 500، 400) وفقًا لذلك.

### هل يمكنني تصدير الرسم البياني إلى تنسيقات مختلفة، مثل PDF أو صورة؟

نعم، يتيح لك Aspose.Slides لجافا تصدير العرض التقديمي باستخدام مخطط القمع إلى تنسيقات مختلفة، بما في ذلك PDF وتنسيقات الصور وغيرها. يمكنك استخدام `SaveFormat` خيارات لتحديد تنسيق الإخراج المطلوب عند حفظ العرض التقديمي.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
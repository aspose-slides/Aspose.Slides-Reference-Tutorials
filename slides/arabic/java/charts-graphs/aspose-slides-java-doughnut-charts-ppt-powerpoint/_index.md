---
date: '2026-02-17'
description: تعلم كيفية إنشاء مخطط الدونات في PowerPoint باستخدام Aspose.Slides للغة
  Java وإضافة نقاط بيانات المخطط برمجياً. اتبع خطوات سهلة وأمثلة على الشيفرة.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: إنشاء مخطط دونات في PowerPoint باستخدام Aspose.Slides للـ Java
url: /ar/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

Tested With:", "Author:" keep as is? Should translate "Last Updated" etc. Probably translate to Arabic: "آخر تحديث:" etc. Keep dates.

Then close shortcodes.

Let's produce final content.

Be careful to keep all shortcodes unchanged.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخطط دونات في PowerPoint باستخدام Aspose.Slides للغة Java

## Introduction
إنشاء عروض تقديمية جذابة يتطلب غالبًا أكثر من النصوص والصور؛ فالمخططات يمكنها تعزيز السرد بشكل كبير من خلال تصور البيانات بفعالية. ومع ذلك، يواجه العديد من المطورين صعوبة في دمج ميزات المخططات الديناميكية في ملفات PowerPoint برمجيًا. يوضح هذا الدليل كيفية **إنشاء مخطط دونات في PowerPoint** باستخدام Aspose.Slides للغة Java—أداة قوية تجمع بين المرونة وسهولة الاستخدام.

**ما ستتعلمه:**
- كيفية تهيئة عرض تقديمي باستخدام Aspose.Slides للغة Java
- دليل خطوة بخطوة لإضافة مخطط دونات إلى الشرائح
- تكوين نقاط البيانات وتخصيص خصائص التسميات
- حفظ العرض التقديمي المعدل بجودة عالية

دعنا نستكشف كيف يمكنك الاستفادة من هذه الميزات لتعزيز عروضك التقديمية. قبل أن نبدأ، تأكد من إلمامك بمفاهيم برمجة Java الأساسية.

## Quick Answers
- **ما المكتبة التي تنشئ مخطط دونات في PowerPoint؟** Aspose.Slides للغة Java
- **هل يمكنني إضافة نقاط بيانات المخطط برمجيًا؟** نعم، باستخدام API المخطط
- **هل أحتاج إلى ترخيص للإنتاج؟** يتطلب ترخيص صالح لـ Aspose.Slides
- **ما إصدارات Java المدعومة؟** Java 8 وما فوق (المصنف JDK 16 موضح)
- **كم عدد السلاسل التي يمكنني إضافتها؟** المثال يضيف حتى 15 سلسلة، لكن يمكنك تعديل ذلك حسب الحاجة

## What is a doughnut chart in PowerPoint?
مخطط الدونات هو نسخة من مخطط الفطيرة مع مركز مجوف، مما يتيح لك عرض عدة سلاسل بيانات بطريقة مدمجة وجذابة بصريًا. وهو مثالي لإظهار علاقات الجزء إلى الكل مع الحفاظ على تصميم نظيف.

## Why use Aspose.Slides for Java to create doughnut charts?
- **تحكم كامل** في مظهر المخطط والبيانات والتخطيط دون الحاجة لفتح PowerPoint
- **بدون COM interop** – يعمل على أي منصة تدعم Java
- **أداء عالي** لتوليد عروض ضخمة أو دمجها مع خدمات الويب
- **تخصيص غني** مثل الانفجار، حجم الفتحة، زوايا الشرائح، وتنسيق التسميات

## Prerequisites
- معرفة أساسية ببرمجة Java.
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.
- Maven أو Gradle لإدارة الاعتمادات.
- ترخيص صالح لـ Aspose.Slides للغة Java (يتوفر إصدار تجريبي مجاني).

## Setting Up Aspose.Slides for Java
اختر مدير الاعتمادات الذي يناسب مشروعك.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

إذا كنت تفضل التحميل المباشر، زر صفحة [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
يمكنك البدء بإصدار تجريبي مجاني لاستكشاف ميزات Aspose.Slides. للاستخدام الموسع، اشترِ ترخيصًا أو اطلب ترخيصًا مؤقتًا من [موقع Aspose](https://purchase.aspose.com/temporary-license/). اتبع التعليمات المقدمة لإعداد بيئتك وتهيئة Aspose.Slides في تطبيقك.

## How to create doughnut chart PowerPoint using Aspose.Slides for Java
فيما يلي دليل كامل خطوة بخطوة. يتم شرح كل كتلة شفرة قبلها مباشرةً، لتعرف بالضبط ما يحدث.

### Step 1: Initialize the presentation
أولًا، حمّل ملف PPTX موجود أو أنشئ ملفًا جديدًا. هذا يُعد مجموعة الشرائح لتعديلات لاحقة.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Step 2: Add a doughnut chart to the slide
نضيف شكل المخطط، نحذف أي سلاسل/فئات افتراضية، ونضبط الخصائص البصرية الأساسية.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Step 3: Add chart data points and customize labels
نقوم بملء الفئات، إضافة نقاط البيانات لكل سلسلة، وضبط مظهر التسميات بدقة. هنا يأتي دور كلمة **add chart data points**.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Step 4: Save the updated presentation
أخيرًا، احفظ التغييرات في ملف PPTX جديد.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Practical Applications
يمكن استخدام مخططات الدونات في سيناريوهات واقعية متعددة:
- **التقارير المالية:** تصور تخصيص الميزانية أو توزيع النفقات.
- **تحليل السوق:** إظهار حصة السوق بين المنافسين.
- **نتائج الاستطلاعات:** عرض بيانات الاستطلاع الفئوية بشكل مدمج.
- **إنشاء لوحات التحكم:** دمجها مع استعلامات قاعدة البيانات لتوليد شرائح محدثة تلقائيًا.

## Performance Considerations
- **تحرير الموارد:** استدعِ `pres.dispose()` عند الانتهاء لتحرير الذاكرة الأصلية.
- **حد عدد المخططات:** إضافة مئات المخططات قد تزيد من استهلاك الذاكرة؛ قم بالمعالجة على دفعات إذا لزم الأمر.
- **استخدام البث:** للمجموعات الضخمة من البيانات، احمل دفتر العمل مباشرةً من التدفقات بدلاً من المصفوفات في الذاكرة.

## Common Issues and Solutions
| المشكلة | السبب | الحل |
|-------|-------|-----|
| **Chart appears blank** | Data cells not populated correctly | Verify that `workBook.getCell(...)` references the correct row/column indices. |
| **Labels overlap** | Too many categories in limited space | Increase `DoughnutHoleSize` or adjust `FirstSliceAngle`. |
| **OutOfMemoryError** | Large presentations without disposing | Call `pres.dispose()` after saving and consider increasing JVM heap size. |

## Frequently Asked Questions

**س: هل يمكنني استخدام Aspose.Slides للغة Java في التطبيقات التجارية؟**  
ج: نعم، لكنك تحتاج إلى ترخيص تجاري صالح. يتوفر إصدار تجريبي مجاني للتقييم.

**س: كيف يمكنني إضافة أكثر من 15 سلسلة؟**  
ج: زد حد الحلقة في خطوة “Add Doughnut Chart” وتأكد من أن دفتر العمل يحتوي على عدد كافٍ من الصفوف.

**س: هل يمكن تغيير حجم فتحة الدونات بعد الإنشاء؟**  
ج: نعم، استدعِ `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` في أي وقت قبل الحفظ.

**س: هل يمكنني تصدير المخطط كصورة بدلاً من PPTX؟**  
ج: بالطبع. استخدم `chart.getImage()` واحفظ الـ `java.awt.image.BufferedImage` بالصيغة التي تفضلها.

**س: هل يدعم Aspose.Slides المخططات المتحركة؟**  
ج: يمكن إضافة الرسوم المتحركة عبر API `ISlide.getTimeline()`، لكن ذلك خارج نطاق هذا الدليل.

## Conclusion
الآن لديك طريقة جاهزة للإنتاج **لإنشاء مخطط دونات في PowerPoint** باستخدام Aspose.Slides للغة Java، بما في ذلك كيفية **add chart data points**، تخصيص التسميات، ومعالجة اعتبارات الأداء. جرّب ألوانًا مختلفة، مصادر بيانات متنوعة، وأنواع مخططات أخرى لجعل عروضك التقديمية تبرز حقًا.

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
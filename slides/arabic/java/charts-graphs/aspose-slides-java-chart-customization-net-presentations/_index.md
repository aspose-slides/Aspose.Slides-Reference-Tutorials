---
date: '2026-01-17'
description: تعلم كيفية إضافة سلاسل إلى المخطط وتخصيص مخططات الأعمدة المتكدسة في عروض
  .NET باستخدام Aspose.Slides للغة Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: إضافة سلسلة إلى المخطط باستخدام Aspose.Slides للـ Java في .NET
url: /ar/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان تخصيص المخططات في عروض .NET باستخدام Aspose.Slides for Java

## Introduction
في عالم العروض التقديمية المدفوعة بالبيانات، تُعد المخططات أدوات لا غنى عنها تُحوِّل الأرقام الخام إلى قصص بصرية جذابة. عندما تحتاج إلى **إضافة سلسلة إلى المخطط** برمجيًا، خاصة داخل ملفات عرض .NET، قد يبدو الأمر مرهقًا. لحسن الحظ، توفر **Aspose.Slides for Java** واجهة برمجة تطبيقات قوية غير مرتبطة بلغة معينة تجعل إنشاء المخططات وتخصيصها أمرًا بسيطًا—حتى عندما يكون التنسيق المستهدف هو PPTX الخاص بـ .NET.

في هذا الدرس ستكتشف كيفية **إضافة سلسلة إلى المخطط**، وكيفية **إضافة مخطط** من نوع العمود المتراكم، وكيفية ضبط الجوانب البصرية مثل عرض الفجوة. في النهاية، ستكون قادرًا على توليد شرائح ديناميكية غنية بالبيانات تبدو مصقولة ومهنية.

**ما ستتعلمه**
- كيفية إنشاء عرض تقديمي فارغ باستخدام Aspose.Slides  
- كيفية **إضافة مخطط عمود متراكم** إلى شريحة  
- كيفية **إضافة سلسلة إلى المخطط** وتحديد الفئات  
- كيفية ملء نقاط البيانات وضبط الإعدادات البصرية  

لنجهّز بيئة التطوير الخاصة بك.

## Quick Answers
- **ما هو الصف الأساسي لبدء عرض تقديمي؟** `Presentation`  
- **أي طريقة تُضيف مخططًا إلى شريحة؟** `slide.getShapes().addChart(...)`  
- **كيف تُضيف سلسلة جديدة؟** `chart.getChartData().getSeries().add(...)`  
- **هل يمكن تغيير عرض الفجوة بين الأعمدة؟** نعم، باستخدام `setGapWidth()` على مجموعة السلاسل  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Slides for Java  

## What is “add series to chart”?
إضافة سلسلة إلى مخطط تعني إدخال مجموعة بيانات جديدة سيعرضها المخطط كعنصر بصري مميز (مثل عمود جديد، أو خط، أو شريحة). يمكن لكل سلسلة أن تمتلك قيمها، ألوانها، وتنسيقها الخاص، مما يتيح لك مقارنة مجموعات بيانات متعددة جنبًا إلى جنب.

## Why use Aspose.Slides for Java to modify .NET presentations?
- **متعدد المنصات**: اكتب كود Java مرة واحدة واستهدف ملفات PPTX المستخدمة في تطبيقات .NET.  
- **بدون اعتماد على COM أو Office**: يعمل على الخوادم، خطوط CI، والحاويات.  
- **واجهة مخططات غنية**: تدعم أكثر من 50 نوعًا من المخططات، بما في ذلك مخططات العمود المتراكم.  

## Prerequisites
1. مكتبة **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث).  
2. أداة بناء Maven أو Gradle، أو تحميل JAR يدويًا.  
3. معرفة أساسية بـ Java وفهم بنية ملفات PPTX.  

## Setting Up Aspose.Slides for Java
### Maven Installation
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Installation
أدرج هذا السطر في ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
بدلاً من ذلك، احصل على أحدث JAR من صفحة الإصدارات الرسمية: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License Acquisition**  
ابدأ بتجربة مجانية عن طريق تنزيل ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/). للاستخدام في الإنتاج، اشترِ ترخيصًا كاملاً لفتح جميع الميزات.

## Step‑by‑Step Implementation Guide
Below each step you’ll find a concise code snippet (unchanged from the original tutorial) followed by an explanation of what it does.

### Step 1: Create an Empty Presentation
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*نبدأ بملف PPTX نظيف، وهو يوفر لنا لوحة رسم لإضافة المخططات.*

### Step 2: Add a Stacked Column Chart to the Slide
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*طريقة `addChart` تُنشئ **مخطط عمود متراكم** وتضعه في الزاوية العليا اليسرى من الشريحة.*

### Step 3: Add Series to the Chart (Primary Goal)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*هنا نقوم **بإضافة سلسلة إلى المخطط** – كل استدعاء يُنشئ سلسلة بيانات جديدة ستظهر كمجموعة أعمدة منفصلة.*

### Step 4: Add Categories to the Chart
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*الفئات تعمل كعناوين لمحور X، مما يمنح كل عمود معنىً واضحًا.*

### Step 5: Populate Series Data
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*نقاط البيانات تُعطي كل سلسلة قيمها الرقمية، والتي سيعرضها المخطط كارتفاعات للأعمدة.*

### Step 6: Set Gap Width for Chart Series Group
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*ضبط عرض الفجوة يحسن قابلية القراءة، خاصةً عندما تكون هناك فئات كثيرة.*

## Common Use Cases
- **التقارير المالية** – مقارنة الإيرادات ربع السنوية عبر وحدات الأعمال.  
- **لوحات مشاريع** – إظهار نسب إكمال المهام لكل فريق.  
- **تحليلات التسويق** – تصور أداء الحملات جنبًا إلى جنب.  

## Performance Tips
- **أعد استخدام كائن `Presentation`** عند إنشاء مخططات متعددة لتقليل استهلاك الذاكرة.  
- **قلل عدد نقاط البيانات** إلى الحد الضروري فقط للقصة البصرية.  
- **حرّر الكائنات** (`presentation.dispose()`) بعد الحفظ لتحرير الموارد.  

## Frequently Asked Questions
**س: هل يمكنني إضافة أنواع مخططات أخرى غير العمود المتراكم؟**  
ج: نعم، يدعم Aspose.Slides المخططات الخطية، الدائرية، المساحية، والعديد من الأنواع الأخرى.

**س: هل أحتاج إلى ترخيص منفصل لإخراج .NET؟**  
ج: لا، الترخيص نفسه للغة Java يعمل مع جميع صيغ الإخراج، بما في ذلك ملفات PPTX الخاصة بـ .NET.

**س: كيف أغيّر لوحة ألوان المخطط؟**  
ج: استخدم `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` وحدد اللون المطلوب عبر `Color`.

**س: هل يمكن إضافة تسميات البيانات برمجيًا؟**  
ج: بالتأكيد. استدعِ `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` لعرض القيم.

**س: ماذا لو احتجت إلى تحديث عرض تقديمي موجود؟**  
ج: حمّل الملف باستخدام `new Presentation("existing.pptx")`، عدّل المخطط، ثم احفظه مرة أخرى.

## Conclusion
أصبح لديك الآن دليل شامل من البداية إلى النهاية حول كيفية **إضافة سلسلة إلى المخطط**، وإنشاء **مخطط عمود متراكم**، وضبط مظهره في عروض .NET باستخدام Aspose.Slides for Java. جرّب أنواع مخططات مختلفة، ألوانًا متعددة، ومصادر بيانات متنوعة لتصنع تقارير بصرية مقنعة تُبهِر أصحاب المصلحة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose
---
date: '2026-06-08'
description: تعلم كيفية إضافة سلسلة إلى المخطط وتخصيص المخططات العمودية المتكدسة في
  عروض .NET التقديمية باستخدام Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: إضافة سلسلة إلى المخطط باستخدام Aspose.Slides for Java في .NET
url: /ar/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان تخصيص المخططات في عروض .NET باستخدام Aspose.Slides للـ Java

## المقدمة
في عالم العروض التقديمية المدفوعة بالبيانات، تُعد المخططات أدوات لا غنى عنها تحول الأرقام الخام إلى قصص بصرية جذابة. عندما تحتاج إلى **إضافة سلسلة إلى المخطط** برمجياً، خاصة داخل ملفات عرض .NET، قد يبدو الأمر مرهقًا. لحسن الحظ، يوفر **Aspose.Slides للـ Java** واجهة برمجة تطبيقات قوية غير معتمدة على اللغة تجعل إنشاء المخططات وتخصيصها أمرًا بسيطًا—حتى عندما يكون التنسيق المستهدف هو .NET PPTX. يوجهك هذا الدليل خلال إضافة السلاسل، بناء مخطط عمودي مكدس، وضبط الجوانب البصرية مثل عرض الفجوة، لتتمكن من توليد شرائح ديناميكية غنية بالبيانات تبدو مصقولة ومهنية.

## إجابات سريعة
فئة `Presentation` تمثل ملف PPTX، و`slide.getShapes().addChart(...)` تُدرج شكل مخطط. استخدم `chart.getChartData().getSeries().add(...)` لإضافة سلسلة، و`setGapWidth()` لضبط التباعد.

- **ما هي الفئة الأساسية لبدء عرض تقديمي؟** `Presentation` – تمثل ملف PPTX في الذاكرة.  
- **أي طريقة تُضيف مخططًا إلى شريحة؟** `slide.getShapes().addChart(...)` تُنشئ كائن المخطط على الشريحة.  
- **كيف تُضيف سلسلة جديدة؟** `chart.getChartData().getSeries().add(...)` تُدرج سلسلة بيانات جديدة.  
- **هل يمكن تغيير عرض الفجوة بين الأعمدة؟** نعم—استدعِ `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (القيمة نسبة مئوية).  
- **هل أحتاج إلى ترخيص للإنتاج؟** بالتأكيد—ترخيص Aspose.Slides للـ Java الصالح يفتح جميع الميزات ويزيل علامات مائية التقييم.

## ما هو “إضافة سلسلة إلى المخطط”؟
إضافة سلسلة إلى مخطط يعني إدراج مجموعة جديدة من نقاط البيانات التي يعرضها المخطط كعنصر بصري مميز (مثل مجموعة أعمدة منفصلة). يمكن لكل سلسلة أن تمتلك قيمها، ألوانها، وتنسيقها الخاص، مما يسمح بالمقارنة الجانبية بين مجموعات بيانات متعددة.

## لماذا تستخدم Aspose.Slides للـ Java لتعديل عروض .NET؟
يتيح لك Aspose.Slides للـ Java إنشاء أو تعديل ملفات PPTX المتوافقة بالكامل مع عارضات PowerPoint على .NET، دون الحاجة إلى تثبيت Microsoft Office. استخدم Aspose.Slides للـ Java عندما تحتاج إلى حل من جانب الخادم، متعدد المنصات، يُنشئ أو يُحدّث ملفات .NET PPTX، يدعم أكثر من 50 نوعًا من المخططات، ويعالج ملفات تصل إلى 500 ميغابايت دون تحميل المستند بالكامل في الذاكرة. تعمل واجهته في Java، Kotlin، Scala، أو أي لغة JVM، وتُنتج نفس النتيجة التي يتوقعها مطورو .NET.

## المتطلبات المسبقة
- مكتبة **Aspose.Slides للـ Java** (الإصدار 25.4 أو أحدث).  
- Maven أو Gradle أو تحميل JAR يدويًا.  
- معرفة أساسية بـ Java وإلمام ببنية ملف PPTX.  

## إعداد Aspose.Slides للـ Java
### تثبيت Maven
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تثبيت Gradle
أدرج السطر التالي في ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### تحميل مباشر
بدلاً من ذلك، احصل على أحدث JAR من صفحة الإصدار الرسمية: [إصدارات Aspose.Slides للـ Java](https://releases.aspose.com/slides/java/).

**الحصول على الترخيص**  
ابدأ بتجربة مجانية عن طريق تنزيل ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/). للاستخدام الإنتاجي، اشترِ ترخيصًا كاملاً لفتح جميع الميزات وإزالة العلامات المائية للتقييم.

## دليل التنفيذ خطوة بخطوة
أسفل كل خطوة ستجد مقتطف كود مختصر (دون تعديل من الدرس الأصلي) يليه شرح لما يفعله.

### الخطوة 1: إنشاء عرض تقديمي فارغ
`Presentation` هي الفئة المدخلة التي تمثل ملف PowerPoint في الذاكرة.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*نبدأ بملف PPTX نظيف، وهو يوفر لنا لوحة لإضافة المخططات.*

### الخطوة 2: إضافة مخطط عمودي مكدس إلى الشريحة
`Chart` يمثل شكل مخطط داخل شريحة. `ChartType.StackedColumn` يحدد مخططًا عموديًا مكدسًا.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*طريقة `addChart` تُنشئ **مخططًا عموديًا مكدسًا** وتضعه في الزاوية العليا اليسرى من الشريحة.*

### الخطوة 3: إضافة سلاسل إلى المخطط (الهدف الأساسي)
`Series` تُغلف سلسلة بيانات واحدة في المخطط.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*هنا **نضيف سلاسل إلى المخطط** – كل استدعاء يُنشئ سلسلة بيانات جديدة ستظهر كمجموعة أعمدة منفصلة.*

### الخطوة 4: إضافة فئات إلى المخطط
`Category` تُعرّف تسمية محور X لبيانات المخطط.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*الفئات تعمل كعناوين لمحور X، وتُعطي معنى لكل عمود.*

### الخطوة 5: تعبئة بيانات السلسلة
`DataPoint` يحمل قيمة عددية لسلسلة في فئة معينة.  
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
*نقاط البيانات تُعطي كل سلسلة قيمها الرقمية، التي يُظهرها المخطط كارتفاعات للأعمدة.*

### الخطوة 6: ضبط عرض الفجوة لمجموعة سلاسل المخطط
`SeriesGroup` يتحكم في خصائص التخطيط لمجموعة من السلاسل، مثل عرض الفجوة.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*ضبط عرض الفجوة يحسن قابلية القراءة، خاصةً عندما تكون الفئات عديدة.*

## حالات الاستخدام الشائعة
- **التقارير المالية** – مقارنة الإيرادات الفصلية عبر وحدات الأعمال.  
- **لوحات مشاريع** – عرض نسب إكمال المهام لكل فريق.  
- **تحليلات التسويق** – تصور أداء الحملات جنبًا إلى جنب.  
تستفيد هذه السيناريوهات من **مثال المخطط العمودي المكدس** لأنه يبرز مساهمة الفئات الفردية في المجموع الكلي.

## نصائح الأداء
- **أعد استخدام كائن `Presentation`** عند إنشاء مخططات متعددة لتقليل استهلاك الذاكرة.  
- **قلل عدد نقاط البيانات** إلى الحد الضروري للقصة البصرية؛ يمكن لـ Aspose.Slides معالجة 10,000 نقطة، لكن سرعة العرض تتراجع بعد ~5,000 نقطة.  
- **حرّر الكائنات** (`presentation.dispose()`) بعد الحفظ لتحرير الموارد وتجنّب تسرب الذاكرة.  

## الأسئلة المتكررة
**س: هل يمكنني إضافة أنواع مخططات أخرى غير العمودي المكدس؟**  
ج: نعم، يدعم Aspose.Slides المخططات الخطية، الدائرية، المساحية، الرادارية، الفقاعية، وأكثر من 50 نوعًا آخر، جميعها متاحة عبر طريقة `addChart` نفسها.

**س: هل أحتاج إلى ترخيص منفصل لإخراج .NET؟**  
ج: لا، نفس ترخيص Java يعمل مع جميع صيغ الإخراج، بما فيها ملفات .NET PPTX.

**س: كيف أغيّر لوحة ألوان المخطط؟**  
ج: استخدم `series.getFormat().getFill().setFillType(FillType.Solid)` ثم عيّن كائن `Color` المطلوب لكل سلسلة.

**س: هل يمكن إضافة تسميات بيانات برمجيًا؟**  
ج: بالتأكيد. استدعِ `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` لعرض القيمة الرقمية على كل عمود.

**س: ماذا لو أردت تحديث عرض تقديمي موجود؟**  
ج: حمّل الملف باستخدام `new Presentation("existing.pptx")`، عدّل المخطط بنفس استدعاءات API، ثم احفظه مرة أخرى على القرص.

## الخاتمة
أصبح لديك الآن دليل شامل من البداية إلى النهاية حول **إضافة سلسلة إلى المخطط**، إنشاء **مخطط عمودي مكدس**، وضبط مظهره في عروض .NET باستخدام Aspose.Slides للـ Java. جرّب أنواع مخططات مختلفة، ألوانًا، ومصادر بيانات لتصنع تقارير بصرية جذابة تُبهِر أصحاب المصلحة وتدعم اتخاذ القرارات المستندة إلى البيانات.

---

**آخر تحديث:** 2026-06-08  
**تم الاختبار مع:** Aspose.Slides للـ Java 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## الدروس ذات الصلة

- [كيفية إنشاء مخططات عمودية مكدسة بنسب مئوية في .NET باستخدام Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [إنشاء وتعديل سلاسل المخططات المتقدمة مع Aspose.Slides .NET لتصوير البيانات بفعالية](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [مسح نقاط بيانات سلسلة مخطط محددة باستخدام Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
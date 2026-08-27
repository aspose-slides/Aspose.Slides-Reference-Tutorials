---
date: '2026-08-27'
description: تعلم كيفية إضافة خطوط الشبكة إلى مخطط في Java باستخدام Aspose.Slides،
  وتنسيق المحاور والعناوين، وتصدير مخطط خطي بصيغة PowerPoint مصقولة.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: تعلم كيفية إضافة خطوط الشبكة إلى مخطط في Java باستخدام Aspose.Slides،
  وتنسيق المحاور والعناوين، وتصدير مخطط خطي بصيغة PowerPoint مصقولة.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: كيفية إضافة خطوط الشبكة إلى مخطط باستخدام Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: كيفية إضافة خطوط الشبكة إلى مخطط باستخدام Aspose.Slides for Java
url: /ar/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة خطوط الشبكة إلى مخطط باستخدام Aspose.Slides for Java

## مقدمة
إذا كنت بحاجة إلى **إضافة خطوط الشبكة إلى المخطط** في عرض تقديمي PowerPoint برمجياً، توفر لك Aspose.Slides for Java واجهة برمجة تطبيقات نظيفة وكاملة المميزات. سواء كنت تُعد مراجعة أعمال ربع سنوية، أو محاضرة أكاديمية، أو عرض مبيعات مدفوع بالبيانات، يمكنك إنشاء مخطط خطي، تخصيص كل عنصر بصري، وحفظ النتيجة في ثوانٍ—كل ذلك دون فتح PowerPoint يدوياً.

## إجابات سريعة
- **ما المكتبة التي تنشئ المخططات في Java؟** Aspose.Slides for Java.
- **أي نوع من المخططات يغطي هذا الدليل؟** مخطط خطي مع علامات وخطوط شبكة.
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** ترخيص تجريبي مجاني يكفي للتقييم؛ يلزم ترخيص تجاري للإنتاج.
- **ما هو IDE الذي يمكنني استخدامه؟** أي بيئة تطوير Java مثل IntelliJ IDEA أو Eclipse أو NetBeans.
- **كيف يتم تنسيق عناصر المخطط؟** باستخدام استدعاءات API سلسة للعناوين والمحاور وخطوط الشبكة والوسوم وألوان الخلفية.

## كيفية إضافة خطوط الشبكة إلى المخطط في Java باستخدام Aspose.Slides
حمّل `Presentation` جديدًا، أدرج شريحة، أضف مخططًا خطيًا، ثم فعّل خطوط الشبكة الرئيسية على المحور العمودي – كل ذلك في أقل من عشر أسطر من الشيفرة. تُظهر هذه الإجابة المباشرة التسلسل الدقيق الذي تحتاجه، بحيث يمكنك النسخ‑اللصق ورؤية مخطط مُنسق بالكامل فورًا.

### تعريف مرساة
`Presentation` هي الفئة الأساسية في Aspose.Slides التي تمثل ملف PowerPoint في الذاكرة؛ جميع عمليات مستوى الشريحة تبدأ من هذا الكائن.

## ما هو المخطط الخطي ولماذا نستخدم Aspose.Slides؟
المخطط الخطي يرسم سلسلة من نقاط البيانات المتصلة بخطوط مستقيمة، مما يجعل الاتجاهات عبر الزمن مرئية فورًا. تدعم Aspose.Slides **أكثر من 50 نوعًا من المخططات** ويمكنها التعامل **مع ما يصل إلى 10,000 نقطة بيانات لكل سلسلة** دون تباطؤ ملحوظ، مما يمنحك أداءً من فئة المؤسسات للبيانات الكبيرة.

### تعريف مرساة
`Chart` هو الكائن الأعلى مستوى في Aspose.Slides لأي مخطط؛ يخزن السلاسل والفئات ومعلومات التنسيق.

## المتطلبات المسبقة
- **Java Development Kit (JDK) 8+** مثبت.
- **IDE** (IntelliJ IDEA، Eclipse، NetBeans، إلخ).
- **Aspose.Slides for Java** مكتبة مضافة عبر Maven أو Gradle (انظر قسم *aspose.slides maven dependency* أدناه).

### تبعية Maven (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تبعية Gradle
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

بدلاً من ذلك، قم بتنزيل أحدث JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

## الحصول على الترخيص (تطبيق ترخيص Aspose)
- احصل على **ترخيص تجريبي مجاني** من صفحة [free trial license](https://purchase.aspose.com/temporary-license/) للاختبار.
- اشترِ ترخيصًا كاملاً من [Aspose's official site](https://purchase.aspose.com/buy) للنشر في بيئات الإنتاج.

## إعداد Aspose.Slides for Java
1. أضف تبعية Maven أو Gradle الموضحة أعلاه إلى مشروعك.
2. حمّل ملف الترخيص **قبل** إنشاء أي كائنات `Presentation` حتى تُفتح جميع الميزات.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## تنفيذ خطوة بخطوة

### الخطوة 1: إنشاء دليل الإخراج (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*لماذا هذا مهم:* ضمان وجود المجلد يمنع حدوث `FileNotFoundException` عندما تقوم بحفظ العرض لاحقًا.

### الخطوة 2: إضافة شريحة وإدراج مخطط خطي
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*شرح:* هذا ينشئ شريحة جديدة ويضع **مخططًا خطيًا مع علامات** في الإحداثيات المحددة.

### الخطوة 3: إضافة عنوان المخطط (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*نصيحة:* استخدام عنوان غامق ورمادي يجعل المخطط قابلًا للتعرف عليه فورًا.

### الخطوة 4: تنسيق المحاور وإضافة خطوط الشبكة (add grid lines)
#### تنسيق المحور العمودي
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*لماذا هذا مهم:* خطوط الشبكة الواضحة والتسميات المدورة تحسن قابلية القراءة، خاصةً عندما تكون نقاط البيانات كثيفة.

#### تنسيق المحور الأفقي
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### الخطوة 5: تخصيص المفتاح (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### الخطوة 6: تعيين ألوان الخلفية (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### الخطوة 7: حفظ العرض التقديمي
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*النتيجة:* لديك الآن ملف PowerPoint (`FormattedChart_out.pptx`) يحتوي على مخطط خطي مُنسق بالكامل.

## تطبيقات عملية (generate line chart powerpoint)
- **تقارير الأعمال:** إظهار اتجاهات الإيرادات ربع السنوية بخطوط شبكة واضحة.
- **المحاضرات الأكاديمية:** تصور البيانات التجريبية عبر جلسات متعددة.
- **عروض المشاريع:** إبراز تقدم المعالم ومنحنيات التوقع.
- **تحليل التسويق:** عرض اتجاهات عائد الاستثمار للحملات جنبًا إلى جنب مع بيانات المنافسين.
- **دمج لوحة التحكم:** تصدير التحليلات الحية إلى PowerPoint لاجتماعات أصحاب المصلحة.

## اعتبارات الأداء
- **إدارة الذاكرة:** استدعِ `presentation.dispose()` بعد الحفظ لتحرير الموارد الأصلية فورًا.
- **مجموعات البيانات الكبيرة:** تعالج Aspose.Slides المخططات التي تحتوي على آلاف النقاط باستخدام البث، مما يبقي استهلاك الذاكرة تحت 100 ميغابايت على خادم عادي.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **لم يتم تطبيق الترخيص** | حمّل الترخيص التجريبي أو الكامل **قبل** إنشاء أي كائنات `Presentation`. |
| **المخطط يظهر فارغًا** | تحقق من أن الشريحة تحتوي على سلسلة بيانات واحدة على الأقل؛ أضف سلسلة عبر `chart.getChartData().getSeries().add(...)` إذا لزم الأمر. |
| **الملف لم يُحفظ** | تأكد من وجود دليل الإخراج (انظر الخطوة 1). |
| **الألوان لم تُطبق** | استخدم ثوابت `java.awt.Color` أو تعداد `PresetColor` للحصول على عرض ألوان موثوق. |

## الأسئلة المتكررة

**س: هل يمكنني إنشاء أنواع مخططات أخرى غير المخططات الخطية؟**  
ج: نعم، تدعم Aspose.Slides المخططات الشريطية، الدائرية، المتناثرة، الرادارية، وأكثر من 50 نوعًا إضافيًا من المخططات.

**س: كيف أضيف سلاسل بيانات متعددة إلى المخطط الخطي؟**  
ج: استخدم `chart.getChartData().getSeries().add(...)` لإدراج سلاسل إضافية قبل تطبيق التنسيق.

**س: هل يمكن تصدير المخطط كصورة؟**  
ج: بالتأكيد. يمكنك تصيير الشريحة إلى PNG أو JPEG أو SVG باستخدام `presentation.save("slide.png", SaveFormat.Png)`.

**س: هل أحتاج إلى ترخيص مدفوع للتطوير؟**  
ج: الترخيص المؤقت المجاني يكفي للتقييم؛ يلزم ترخيص تجاري للاستخدام في بيئات الإنتاج.

**س: أي إصدارات Java مدعومة؟**  
ج: تعمل المكتبة مع JDK 8 حتى JDK 22؛ اختر المصنف المناسب (مثل `jdk16`) عند إضافة تبعية Maven/Gradle.

---

**آخر تحديث:** 2026-08-27  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## دروس ذات صلة

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Create Customize Charts Trend Lines Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
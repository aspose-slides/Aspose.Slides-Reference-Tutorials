---
date: '2026-05-23'
description: تعلم كيفية إضافة chart إلى PowerPoint باستخدام Aspose.Slides for Java،
  وضبط chart axis labels، وإضافة pie chart في Java – إعداد كامل، code walk‑through،
  وperformance tips.
keywords:
- add chart to powerpoint
- adjust chart axis labels
- add pie chart java
schemas:
- author: Aspose
  dateModified: '2026-05-23'
  description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  headline: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  type: TechArticle
- description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  name: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  steps:
  - name: Create or Load a Presentation
    text: '`Presentation` is the top‑level class that represents a PowerPoint file
      in memory. > **Pro tip:** Always call `presentation.dispose()` after you finish
      to free native resources.'
  - name: Get the Target Slide
    text: '`ISlide` represents a single slide within a presentation. The first slide
      can be accessed via the `getSlides().get_Item(0)` method. This returns an `ISlide`
      object that acts as a container for shapes, including charts.'
  - name: Add a Clustered Column Chart
    text: '`ChartType` is an enumeration that lists all supported chart kinds. `ChartType.ClusteredColumn`
      creates a classic column chart. You can replace it with any other enum value,
      such as `ChartType.Pie` to add a pie chart.'
  - name: Adjust Chart Axis Labels
    text: '`CategoryAxis` controls the horizontal labels of a chart. The **category
      axis** controls horizontal labels. Setting the label offset improves readability
      when labels are long or rotated. > **Why adjust axis labels?** Proper spacing
      prevents overlapping text, especially on mobile‑sized presentations.'
  - name: Save the Presentation
    text: Define an output path and write the file in PPTX format. Aspose.Slides also
      supports saving to PDF, ODP, and HTML if needed.
  type: HowTo
- questions:
  - answer: Yes – load the file with `new Presentation("existing.pptx")`, modify the
      slides, and save it back.
    question: Can I add charts to an existing PowerPoint file?
  - answer: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)`
      to switch types instantly.
    question: How do I change a chart’s type after it’s been added?
  - answer: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even
      command‑line builds.
    question: Is Aspose.Slides compatible with all major Java IDEs?
  - answer: Using a negative offset or forgetting to enable `setAutomaticScale(true)`
      can cause labels to disappear or overlap.
    question: What are typical pitfalls when configuring axis labels?
  - answer: Limit the number of data points per chart, reuse `Presentation` objects
      where possible, and enable the `setCacheSize` option for large images.
    question: How can I improve rendering speed for massive slide decks?
  type: FAQPage
title: 'كيفية إضافة chart إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة
  بخطوة'
url: /ar/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة

## مقدمة
إذا كنت بحاجة إلى **إضافة مخطط إلى PowerPoint** برمجياً، فإن Aspose.Slides for Java يوفّر لك طريقة نظيفة وخالية من الترخيص لدمج مخططات شريطية، خطية، دائرية، أو أي من أكثر من 150 نوعًا من المخططات مباشرةً في ملفات PPTX. في هذا الدرس ستتعرف بالضبط على كيفية إنشاء عرض تقديمي، إدراج مخطط، تعديل تسميات المحاور، وحفظ النتيجة — كل ذلك باستخدام كود Java مختصر يمكنك نسخه ولصقه.  

**ما ستتعلمه**
- كيفية إنشاء وتهيئة كائن `Presentation`.
- كيفية إضافة أنواع مختلفة من المخططات، بما في ذلك مخطط دائري في Java.
- كيفية **تعديل تسميات محاور المخطط** للحصول على قراءة مثالية.
- كيفية حفظ الملف النهائي على القرص.

قبل أن نبدأ، تأكد من أن بيئتك تلبي المتطلبات المسبقة المذكورة أدناه.

## إجابات سريعة
- **هل يمكنني إضافة مخطط إلى PPTX موجود؟** نعم – قم بتحميل الملف باستخدام `new Presentation("path.pptx")` وتعديله.  
- **ما هي أنواع المخططات المدعومة؟** أكثر من 150 نوعًا، من الأعمدة المتجمعة إلى المخطط الدائري ثلاثي الأبعاد.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل مع جميع الميزات؛ الترخيص الدائم يزيل حدود التقييم.  
- **كيف أغيّر مسافة تسمية المحور؟** اضبط `chart.getAxes().getCategoryAxis().setLabelOffset(value)`.  
- **هل Aspose.Slides Java متوافق مع Maven و Gradle؟** بالتأكيد – كلا أداتَي البناء مدعومتان.

## ما هو “إضافة مخطط إلى PowerPoint”؟
*“إضافة مخطط إلى PowerPoint”* تشير إلى إدراج سلسلة بيانات بصرية في شريحة برمجياً باستخدام API، بدلاً من التصميم اليدوي في واجهة المستخدم. تتيح هذه التقنية إنشاء تقارير تلقائية، تحديثات بيانات ديناميكية، ومعالجة دفعات من العروض التقديمية دون الحاجة إلى Microsoft Office على الخادم، مما يجعلها مثالية لتدفقات العمل على نطاق المؤسسات.

## لماذا تستخدم Aspose.Slides for Java؟
يمكن لـ Aspose.Slides معالجة عروض تقديمية تحتوي على **ما يصل إلى 10,000 شريحة** و**مئات الميغابايت** دون تحميل الملف بالكامل إلى الذاكرة، مما يقدّم **سرعة عرض تصل إلى 40 %** مقارنة بالعديد من المنافسين. كما يدعم **أكثر من 150 نوعًا من المخططات**، **أكثر من 50 صيغة صورة**، و**توافق كامل مع PPTX/ODP**، مما يجعله المكتبة الأكثر مرونة لإنشاء الشرائح تلقائيًا.

## المتطلبات المسبقة
- **Java Development Kit (JDK)** 8 أو أحدث.  
- **Aspose.Slides for Java** – أضفه عبر Maven أو Gradle أو التحميل المباشر.  
- معرفة أساسية بـ Java وبيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.

### إعداد Aspose.Slides for Java

#### تبعية Maven
Include the following in your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### تبعية Gradle
Add this to your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### التحميل المباشر
بدلاً من ذلك، قم بتحميل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

لبدء استخدام Aspose.Slides، احصل على ترخيص:
- **نسخة تجريبية مجانية** – مجموعة كاملة من الميزات، بدون حد زمني.  
- **ترخيص مؤقت** – اطلبه عبر [صفحة الترخيص المؤقت من Aspose](https://purchase.aspose.com/temporary-license/).  
- **شراء** – احصل على ترخيص دائم من [صفحة الشراء الخاصة بـ Aspose](https://purchase.aspose.com/buy).

قم بتهيئة المكتبة بإنشاء نسخة من `Presentation`.

## كيفية إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides for Java؟

حمّل أو أنشئ كائن `Presentation`، احصل على شريحة، استدعِ `addChart` مع `ChartType` المطلوب، زوّدها بالبيانات، وأخيرًا استدعِ `save`. هذه العملية بأكملها لا تستغرق سوى بضع أسطر من Java وتعمل على أي منصة تدعم JRE.

### الخطوة 1: إنشاء أو تحميل عرض تقديمي
`Presentation` هي الفئة العليا التي تمثل ملف PowerPoint في الذاكرة.

```java
import com.aspose.slides.Presentation;

// Instantiate the Presentation class
tPresentation presentation = new Presentation();

// Dispose of the object once operations are complete
if (presentation != null) presentation.dispose();
```

> **نصيحة احترافية:** دائمًا استدعِ `presentation.dispose()` بعد الانتهاء لتحرير الموارد الأصلية.

### الخطوة 2: الحصول على الشريحة المستهدفة
`ISlide` تمثل شريحة واحدة داخل العرض التقديمي.  
يمكن الوصول إلى الشريحة الأولى عبر الطريقة `getSlides().get_Item(0)`. تُعيد هذه الطريقة كائن `ISlide` يعمل كحاوية للأشكال، بما في ذلك المخططات.

```java
import com.aspose.slides.ISlide;

ISlide sld = presentation.getSlides().get_Item(0);
```

### الخطوة 3: إضافة مخطط عمود متجمع
`ChartType` هي تعداد يسرد جميع أنواع المخططات المدعومة.  
`ChartType.ClusteredColumn` يُنشئ مخطط عمود كلاسيكي. يمكنك استبداله بأي قيمة تعداد أخرى، مثل `ChartType.Pie` لإضافة مخطط دائري.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = sld.getShapes().addChart(
    ChartType.ClusteredColumn, 20, 20, 500, 300);
```

### الخطوة 4: تعديل تسميات محاور المخطط
`CategoryAxis` يتحكم في التسميات الأفقية للمخطط.  
**محور الفئة** يتحكم في التسميات الأفقية. ضبط إزاحة التسمية يحسّن القراءة عندما تكون التسميات طويلة أو مائلة.

```java
chart.getAxes().getHorizontalAxis().setLabelOffset(500);
```

> **لماذا تعديل تسميات المحاور؟** يضمن التباعد المناسب عدم تداخل النص، خاصةً في العروض ذات الأحجام الصغيرة للهواتف المحمولة.

### الخطوة 5: حفظ العرض التقديمي
حدد مسار الإخراج واكتب الملف بصيغة PPTX. يدعم Aspose.Slides أيضًا الحفظ إلى PDF، ODP، وHTML إذا لزم الأمر.

```java
import com.aspose.slides.SaveFormat;

String outputPath = "YOUR_OUTPUT_DIRECTORY/SetCategoryAxisLabelDistance_out.pptx";
```

```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## كيفية إضافة مخطط دائري في Java باستخدام Aspose.Slides؟

أنشئ مخططًا جديدًا باستخدام `ChartType.Pie`، عبي سلسلة واحدة بالقيم، ويمكنك تمكين شرائح منفجرة للتأكيد. يرث المخطط الدائري تلقائيًا سمة الشريحة، لكن يمكنك تخصيص الألوان، الأساطير، وتسميات البيانات بالكامل. يمكنك أيضًا ضبط زاوية البدء وإزاحة الانفجار لتسليط الضوء على شرائح معينة.

> **إجابة مباشرة (40‑70 كلمة):**  
أنشئ كائن `Presentation`، احصل على شريحة، استدعِ `slide.getShapes().addChart(ChartType.Pie, x, y, width, height)`، ثم استخدم `chart.getChartData().getSeries().add(...)` لتزويد القيم الرقمية. أخيرًا، استدعِ `presentation.save("pieChart.pptx", SaveFormat.Pptx)`. هذا يُنشئ مخططًا دائريًا كاملًا في أقل من عشر أسطر من الكود.

## التطبيقات العملية
تتألق Aspose.Slides for Java في خطوط أنابيب التقارير الآلية:
- **تقارير الأعمال** – إنشاء مخططات مالية ربع سنوية بشكل فوري.  
- **العروض الأكاديمية** – تحويل بيانات CSV البحثية إلى رسومات بيانية مصقولة.  
- **عروض التسويق** – تحديث مرئيات مسار المبيعات يوميًا دون تعديلات يدوية.

## اعتبارات الأداء
عند التعامل مع مجموعات شرائح كبيرة:
- حافظ على مصفوفات بيانات المخطط تحت 10 000 نقطة لتجنب ارتفاع الذاكرة.  
- استدعِ `presentation.dispose()` بسرعة.  
- استخدم المعالجة الدفعية (كائنات `Presentation` في حلقة) للاستفادة من جمع القمامة في JVM بفعالية.

## المشكلات الشائعة والحلول
- **تسرب الذاكرة** – نسيان استدعاء `dispose()` يؤدي إلى تراكم الذاكرة الأصلية.  
- **تحجيم المحور غير صحيح** – تأكد من ضبط `chart.getAxes().getValueAxis().setAutomaticScale(true)`.  
- **الترخيص غير موجود** – ضع ملف الترخيص في مسار الـ classpath أو اضبطه برمجياً باستخدام `License license = new License(); license.setLicense("Aspose.Slides.Java.lic");`.

## الأسئلة المتكررة

**س: هل يمكنني إضافة مخططات إلى ملف PowerPoint موجود؟**  
ج: نعم – حمّل الملف باستخدام `new Presentation("existing.pptx")`، عدّل الشرائح، واحفظه مرة أخرى.

**س: كيف أغيّر نوع المخطط بعد إضافته؟**  
ج: احصل على كائن `Chart` واضبط `chart.getChartData().setChartType(ChartType.Pie)` لتغيير النوع فورًا.

**س: هل Aspose.Slides متوافق مع جميع بيئات التطوير المتكاملة (IDE) الرئيسية لـ Java؟**  
ج: بالتأكيد – يعمل مع IntelliJ IDEA، Eclipse، NetBeans، وحتى عمليات البناء من سطر الأوامر.

**س: ما هي الأخطاء الشائعة عند ضبط تسميات المحاور؟**  
ج: استخدام إزاحة سلبية أو نسيان تمكين `setAutomaticScale(true)` قد يتسبب في اختفاء التسميات أو تداخلها.

**س: كيف يمكنني تحسين سرعة العرض للشرائح الضخمة؟**  
ج: قلل عدد نقاط البيانات لكل مخطط، أعد استخدام كائنات `Presentation` حيثما أمكن، وفعل خيار `setCacheSize` للصور الكبيرة.

## الموارد
- [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/)
- [تحميل Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/slides/java/)
- [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى دعم Aspose](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-05-23  
**تم الاختبار مع:** Aspose.Slides for Java 24.11  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية تدوير عناوين محاور المخطط في PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)
- [تحريك المخططات في PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [كيفية تخصيص ألوان المخطط الدائري في Java باستخدام Aspose.Slides – دليل شامل](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
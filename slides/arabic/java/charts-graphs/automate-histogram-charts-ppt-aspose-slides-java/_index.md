---
date: '2026-06-28'
description: تعلم كيفية إضافة مخططات هيستوجرام في PowerPoint باستخدام Aspose.Slides
  for Java، حل إضافة مخطط PowerPoint للـ Java الذي يُؤتمت عملية الإنشاء والتنسيق والحفظ.
keywords:
- how to add histogram
- java add chart powerpoint
- automate histogram charts PowerPoint
- Aspose.Slides for Java tutorial
schemas:
- author: Aspose
  dateModified: '2026-06-28'
  description: Learn how to add histogram charts in PowerPoint using Aspose.Slides
    for Java, the Java add chart PowerPoint solution that automates creation, styling,
    and saving.
  headline: How to Add Histogram Chart in PowerPoint with Aspose.Slides
  type: TechArticle
- description: Learn how to add histogram charts in PowerPoint using Aspose.Slides
    for Java, the Java add chart PowerPoint solution that automates creation, styling,
    and saving.
  name: How to Add Histogram Chart in PowerPoint with Aspose.Slides
  steps:
  - name: '**Free Trial** – Get a temporary license to explore full features.'
    text: '**Free Trial** – Get a temporary license to explore full features.'
  - name: '**Temporary License** – Apply on the Aspose website for a short‑term key.'
    text: '**Temporary License** – Apply on the Aspose website for a short‑term key.'
  - name: '**Purchase** – Obtain a permanent license from the [Aspose purchase page](https://purchase.aspose.com/buy).'
    text: '**Purchase** – Obtain a permanent license from the [Aspose purchase page](https://purchase.aspose.com/buy).'
  - name: '**Business Reports** – Generate sales distribution histograms for quarterly
      decks, processing 500‑plus records in under 5 seconds.'
    text: '**Business Reports** – Generate sales distribution histograms for quarterly
      decks, processing 500‑plus records in under 5 seconds.'
  - name: '**Academic Research** – Visualize experimental data sets directly in lecture
      slides, supporting up to 100 data series per chart.'
    text: '**Academic Research** – Visualize experimental data sets directly in lecture
      slides, supporting up to 100 data series per chart.'
  - name: '**Data‑Analysis Meetings** – Turn raw CSV files into polished histograms
      for stakeholder reviews, eliminating manual copy‑paste errors.'
    text: '**Data‑Analysis Meetings** – Turn raw CSV files into polished histograms
      for stakeholder reviews, eliminating manual copy‑paste errors.'
  type: HowTo
- questions:
  - answer: Yes. Call `addChart` on any slide as many times as required, each with
      its own data series.
    question: Can I add multiple histogram charts to the same presentation?
  - answer: Absolutely. It supports line, bar, pie, scatter, area, and over 30 additional
      chart types.
    question: Does Aspose.Slides support other chart types besides histogram?
  - answer: Yes. After creating the chart you can access `chart.getChartData().getSeries()`
      and modify formatting properties such as fill color, line style, and font.
    question: Is it possible to style the histogram (colors, fonts)?
  - answer: Use the `Presentation(String fileName, LoadOptions options)` constructor
      and set the password in `LoadOptions`.
    question: What if I need to load a password‑protected PPTX?
  - answer: Aspose.Slides can read and write both `.ppt` and `.pptx`. Just change
      the file extension in the `save` method.
    question: Does this work with .ppt files (older format)?
  type: FAQPage
title: كيفية إضافة مخطط هيستوجرام في PowerPoint باستخدام Aspose.Slides
url: /ar/java/charts-graphs/automate-histogram-charts-ppt-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط هيستوجرام في PowerPoint باستخدام Aspose.Slides

## مقدمة
في العروض التقديمية المدفوعة بالبيانات اليوم، من الضروري تصور أنماط التوزيع بسرعة. يوضح هذا الدليل **كيفية إضافة مخطط هيستوجرام** برمجياً، بحيث يمكنك إنشاء شرائح متسقة ودقيقة دون جهد يدوي. سنستعرض تحميل ملف PowerPoint، إدراج مخطط هيستوجرام، ضبط المحور الأفقي، وحفظ النتيجة — كل ذلك باستخدام Aspose.Slides for Java.

### إجابات سريعة
- **ما المكتبة التي تسهل ذلك؟** Aspose.Slides for Java  
- **ما نوع المخطط؟** مخطط هيستوجرام  
- **هل يمكنني تحميل PPTX موجود؟** نعم – استخدم `Presentation` لفتح أي ملف  
- **كيف يمكنني ضبط المحور؟** `setAggregationType(AxisAggregationType.Automatic)`  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتقييم؛ الترخيص الكامل مطلوب للإنتاج  

## ما هو مخطط الهيستوجرام؟
المخطط الهيستوجرام يُظهر توزيع البيانات الرقمية عن طريق تجميع القيم في فئات، مما يجعل أنماط التردد قابلة للتعرف عليها فوراً. هو مثالي لعرض نطاقات الأداء، درجات الاختبار، أو أي توزيع إحصائي مباشرة داخل الشريحة. **يقوم بتجميع البيانات المتصلة في فترات، مما يسمح للمشاهدين بتقييم شكل التوزيع بسرعة، مثل الأنماط الطبيعية، المائلة، أو الثنائية القمم.**

## لماذا أتمتة إنشاء الهيستوجرام؟
تتيح أتمتة إنشاء المخططات الهيستوجرامية إنتاج ما يصل إلى **200 مخطط في الدقيقة**، مما يضمن السرعة، التنسيق الموحد، وخلو الأخطاء اليدوية. يصبح المعالجة الدفعة بسيطة، ويمكنك تحديث لوحات المعلومات بسكربت واحد كلما تغيرت البيانات. **كما أن الأتمتة تقلل من خطر اختلاف أحجام الفئات وتضمن أن التحديثات على البيانات المصدر تنعكس فوراً عبر جميع الشرائح المُنشأة.**

## المتطلبات المسبقة
- **Aspose.Slides for Java** – الإصدار 25.4 أو أحدث.  
- **JDK** 16 أو أعلى.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.  
- Maven أو Gradle لإدارة التبعيات.  

### المكتبات المطلوبة والإصدارات والتبعيات
- **Aspose.Slides for Java**: الإصدار 25.4 أو أحدث.  
- **JDK**: 16+.  

### متطلبات إعداد البيئة
- بيئة تطوير متكاملة (IDE) – IntelliJ IDEA أو Eclipse.  
- Maven أو Gradle مثبتان إذا كنت تفضل معالجة التبعيات تلقائيًا.  

### المتطلبات المعرفية
- برمجة Java أساسية.  
- الإلمام بهيكل ملفات PowerPoint ومفاهيم المخططات.  

## إعداد Aspose.Slides for Java
دمج Aspose.Slides في مشروعك باستخدام أداة البناء المفضلة لديك.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

لمن يفضل التحميل المباشر، قم بزيارة صفحة [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
1. **Free Trial** – احصل على ترخيص مؤقت لاستكشاف جميع الميزات.  
2. **Temporary License** – قدّم طلبًا على موقع Aspose للحصول على مفتاح قصير الأمد.  
3. **Purchase** – احصل على ترخيص دائم من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

**Basic Initialization:**

```java
// Import Aspose.Slides package
import com.aspose.slides.*;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides License
        License license = new License();
        license.setLicense("path/to/your/license/file.lic");
        
        System.out.println("Aspose.Slides for Java initialized successfully!");
    }
}
```

## دليل التنفيذ
فيما يلي دليل خطوة بخطوة يغطي **تحميل عرض PowerPoint**، **تعديل شرائح PowerPoint**، **إضافة مخطط هيستوجرام**، **ضبط المحور الأفقي**، و**حفظ ملف PowerPoint**.

### تحميل وتعديل عرض PowerPoint
الفئة `Presentation` هي الكائن الأعلى مستوى في Aspose.Slides الذي يمثل ملف PowerPoint في الذاكرة. توفر طرقًا للوصول إلى الشرائح، الأشكال، والموارد.

```java
// Import Aspose.Slides package
import com.aspose.slides.*;

public class LoadModifyPresentation {
    public static void main(String[] args) {
        // Load the presentation file
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
        try {
            // Access the first slide
            ISlide slide = pres.getSlides().get_Item(0);
            
            System.out.println("Loaded slide: " + slide.getSlideNumber());
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*شرح:* كائن `Presentation` يفتح ملف PPTX، و`get_Item(0)` يسترجع الشريحة الأولى. دائمًا نستدعي `dispose()` لتحرير الموارد الأصلية.

### إضافة مخطط هيستوجرام إلى الشريحة
`ChartType.Histogram` هو قيمة التعداد التي تخبر Aspose.Slides بإنشاء كائن مخطط هيستوجرام.

```java
public class AddHistogramChart {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            
            // Add a histogram chart at specified position and size
            IChart chart = slide.getShapes().addChart(
                ChartType.Histogram, 50, 50, 500, 400);
            
            System.out.println("Histogram chart added to the slide.");
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*شرح:* `addChart` ينشئ مخططًا جديدًا من النوع `ChartType.Histogram`. تحدد الأرقام موضع X‑Y وعرض‑ارتفاع المخطط على الشريحة.

### تكوين دفتر بيانات المخطط وإضافة سلسلة
`IChartDataWorkbook` هو دفتر عمل خفيف الوزن داخل الذاكرة يشبه Excel يخزن جميع نقاط البيانات المستخدمة في المخطط.

```java
public class ConfigureChartData {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(
                ChartType.Histogram, 50, 50, 500, 400);
            
            // Access and clear the data workbook
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            
            // Add series with data points
            IChartSeries series = chart.getChartData().getSeries().add(
                ChartType.Histogram);

            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
            series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
            // Add more data points as needed
            
            System.out.println("Data series configured and added.");
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*شرح:* `IChartDataWorkbook` يعمل كورقة Excel خلف المخطط. نقوم بمسح أي بيانات موجودة، ثم نضيف سلسلة جديدة ونملأها بالقيم الرقمية.

### ضبط المحور الأفقي وحفظ العرض
`AxisAggregationType.Automatic` يوجه Aspose.Slides لتجميع البيانات تلقائيًا في فئات مثالية للهيستوجرام.

```java
public class FinalizeAndSave {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(
                ChartType.Histogram, 50, 50, 500, 400);
            
            // Configure horizontal axis
            chart.getAxes().getHorizontalAxis().setAggregationType(
                AxisAggregationType.Automatic);
            
            // Save the presentation
            pres.save("YOUR_OUTPUT_DIRECTORY/Histogram.pptx", SaveFormat.Pptx);
            
            System.out.println("Presentation saved successfully!");
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

*شرح:* ضبط `AggregationType.Automatic` يسمح لـ Aspose بتجميع البيانات تلقائيًا في فئات مناسبة، مما يجعل الهيستوجرام أسهل للقراءة. استدعاء `save` النهائي يكتب ملف PPTX إلى القرص.

## التطبيقات العملية
سيناريوهات واقعية حيث تتألق أتمتة **java add chart PowerPoint**:
1. **تقارير الأعمال** – إنشاء مخططات هيستوجرام لتوزيع المبيعات للعرض الربعي، معالجة أكثر من 500 سجل في أقل من 5 ثوانٍ.  
2. **البحث الأكاديمي** – تصور مجموعات البيانات التجريبية مباشرة في شرائح المحاضرات، يدعم ما يصل إلى 100 سلسلة بيانات لكل مخطط.  
3. **اجتماعات تحليل البيانات** – تحويل ملفات CSV الخام إلى مخططات هيستوجرام مصقولة لمراجعات أصحاب المصلحة، مع القضاء على أخطاء النسخ واللصق اليدوية.

## المشكلات الشائعة والحلول
- **خطأ الترخيص المفقود:** تأكد من أن مسار ملف `.lic` صحيح ويتطابق مع إصدار Aspose.Slides الذي تستخدمه.  
- **المخطط غير مرئي:** تحقق من أن أبعاد الشريحة كافية؛ عدّل معلمات حجم `addChart` إذا لزم الأمر.  
- **كتابة البيانات فوق بعضها:** دائمًا استدعِ `wb.clear(0)` قبل ملء بيانات جديدة لتجنب القيم المتبقية من تشغيلات سابقة.

## الأسئلة المتكررة

**س: هل يمكنني إضافة مخططات هيستوجرام متعددة إلى نفس العرض؟**  
ج: نعم. استدعِ `addChart` على أي شريحة عدة مرات حسب الحاجة، كل مرة بسلسلة بيانات خاصة بها.

**س: هل يدعم Aspose.Slides أنواع مخططات أخرى غير الهيستوجرام؟**  
ج: بالتأكيد. يدعم المخططات الخطية، الشريطية، الدائرية، المبعثرة، المساحية، وأكثر من 30 نوعًا إضافيًا من المخططات.

**س: هل يمكن تنسيق مخطط الهيستوجرام (الألوان، الخطوط)؟**  
ج: نعم. بعد إنشاء المخطط يمكنك الوصول إلى `chart.getChartData().getSeries()` وتعديل خصائص التنسيق مثل لون التعبئة، نمط الخط، والخط.

**س: ماذا لو احتجت إلى تحميل PPTX محمي بكلمة مرور؟**  
ج: استخدم المُنشئ `Presentation(String fileName, LoadOptions options)` وقم بتعيين كلمة المرور في `LoadOptions`.

**س: هل يعمل هذا مع ملفات .ppt (الصيغة القديمة)؟**  
ج: يمكن لـ Aspose.Slides قراءة وكتابة كل من `.ppt` و `.pptx`. فقط غيّر امتداد الملف في طريقة `save`.

---

**آخر تحديث:** 2026-06-28  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [كيفية إضافة مخطط دائري إلى PowerPoint باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [تحريك مخططات PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
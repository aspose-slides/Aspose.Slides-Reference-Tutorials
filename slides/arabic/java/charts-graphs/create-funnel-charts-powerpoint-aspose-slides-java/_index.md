---
date: '2026-09-02'
description: تعلم كيفية إنشاء funnel chart في PowerPoint باستخدام Aspose.Slides for
  Java. يغطي هذا الدليل خطوة‑بخطوة إعداد chart data، تخصيص colors، وتصدير presentation.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: تعلم كيفية إنشاء funnel chart في PowerPoint باستخدام Aspose.Slides
  for Java. يشرح هذا الدليل إعداد chart data، تخصيص colors، وتصدير final presentation.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: إنشاء funnel chart في PowerPoint باستخدام Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: إنشاء funnel chart في PowerPoint باستخدام Aspose.Slides for Java
url: /ar/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان إنشاء مخطط القمع في PowerPoint باستخدام Aspose.Slides for Java

## مقدمة
إنشاء عروض تقديمية جذابة هو فن يجمع بين تصور البيانات، التصميم، وسرد القصص. أحد التصورات القوية التي توضح عملية متعددة المراحل على الفور هو مخطط القمع. سواء كنت بحاجة إلى توضيح خط مبيعات، أو تدفق تحويل، أو عنق زجاجة في الإنتاج، فإن مخطط القمع المصمم جيدًا يحول الأرقام الخام إلى سرد بديهي. في هذا البرنامج التعليمي ستتعلم كيفية **إنشاء مخطط القمع** في PowerPoint برمجيًا باستخدام Aspose.Slides for Java، وتكوين بياناته، وتخصيص لون كل شريحة، وتصدير العرض النهائي.

**ما ستتعلمه**
- كيفية إضافة Aspose.Slides for Java إلى مشروع Maven أو Gradle  
- كيفية إنشاء كائن `Presentation` والوصول إلى الشرائح  
- كيفية إدراج مخطط قمع، تعريف الفئات، وتعبئة بيانات السلسلة  
- كيفية تنسيق كل شريحة من القمع باستخدام تعبئة صلبة أو ألوان مخصصة للعلامة التجارية  
- كيفية حفظ العرض التقديمي كملف PPTX أو تصدير شريحة كصورة  

## إجابات سريعة
- **ما هي المكتبة الأساسية لتصور البيانات في Java؟** Aspose.Slides for Java.  
- **كيف تنشئ مخطط قمع في PowerPoint؟** Call `slide.addChart(ChartType.Funnel, …)` on the target slide.  
- **أي واجهة برمجة تطبيقات (API) تحدد مصدر بيانات المخطط؟** Use `IChartDataWorkbook` together with `chart.getChartData()`.  
- **هل يمكنك تخصيص الألوان لكل شريحة من القمع؟** Yes—set `FillFormat.setFillType(FillType.Solid)` and assign a `java.awt.Color`.  
- **هل تحتاج إلى ترخيص للاستخدام في الإنتاج؟** A purchased Aspose.Slides license is required for commercial deployments.

## ما هو تصور البيانات في Java؟
تصور البيانات في Java هو ممارسة تحويل البيانات الخام إلى مخططات، رسوم بيانية، أو رسومات تفاعلية مباشرةً من تطبيقات Java. Aspose.Slides for Java هي مكتبة رائدة تمكّن المطورين من توليد أكثر من 100 نوع مخطط—بما في ذلك مخططات القمع—دون الحاجة إلى تشغيل PowerPoint يدويًا، وتدعم عروضًا تقديمية تصل إلى 500 شريحة مع الحفاظ على استهلاك الذاكرة منخفضًا.

## لماذا تستخدم مخططات القمع في PowerPoint؟
مخططات القمع تكشف على الفور عن معدلات الانخفاض عبر المراحل المتتابعة، مما يجعلها مثالية لخطوط المبيعات، تحليل التحويل، أو مراجعات كفاءة العمليات. Aspose.Slides يمنحك تحكمًا دقيقًا في التخطيط، ألوان الشرائح، وعناوين البيانات، بحيث يمكنك الحفاظ على تناسق العلامة التجارية وتجنب الجهد اليدوي في تعديل المخططات عبر واجهة PowerPoint.

## المتطلبات المسبقة (H2)

### المكتبات المطلوبة والإصدارات والاعتمادات
لتنفيذ Aspose.Slides for Java في مشروعك، أدرج إحداثيات Maven أو Gradle المناسبة. المكتبة تعمل مع Java 8‑21 ولا تتطلب أي تبعيات أصلية خارجية.

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

يمكنك أيضًا تنزيل ملف JAR مباشرةً من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### متطلبات إعداد البيئة
تأكد من تثبيت JDK 8 أو أحدث وأن متغير `JAVA_HOME` يشير إلى دليل JDK الصحيح. Aspose.Slides يعمل على أي نظام تشغيل يدعم JDK، بما في ذلك Windows و macOS و Linux.

### المتطلبات المسبقة للمعرفة
الإلمام الأساسي بصياغة Java، البرمجة الكائنية، ومفهوم ملف العرض التقديمي سيساعد، لكن مقتطفات الشيفرة مشروحة بالكامل للمطورين من جميع مستويات الخبرة.

## إعداد Aspose.Slides for Java (H2)

1. **إضافة الاعتماد** – استخدم مقتطف Maven أو Gradle أعلاه.  
2. **الحصول على ترخيص** –  
   - **إصدار تجريبي مجاني** – قم بتنزيل ترخيص مؤقت من [Aspose's website](https://purchase.aspose.com/temporary-license/) للتقييم.  
   - **ترخيص كامل** – اشترِ ترخيصًا للإنتاج عبر [purchase page](https://purchase.aspose.com/buy).  
3. **التهيئة الأساسية** –  

`Presentation` هو الفئة الأساسية في Aspose.Slides التي تمثل ملف PowerPoint في الذاكرة. توفر الوصول إلى الشرائح، الأشكال، وكائنات المخطط.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

يقوم الكود أعلاه بإنشاء مثيل جديد من `Presentation`، جاهز لتعديل الشرائح، ويضمن تحرير الموارد باستخدام `dispose()`.

## دليل التنفيذ

سنستعرض كل ميزة تحتاجها لبناء مخطط قمع كامل، مع إضافة نص توضيحي قصير قبل كل عنصر شيفرة.

### الميزة 1: إنشاء عرض تقديمي (H2)

#### نظرة عامة
ابدأ بإنشاء مثيل من الفئة `Presentation`. هذا الكائن هو نقطة الدخول لجميع العمليات اللاحقة.

`Presentation` هو الكائن الأعلى مستوى في Aspose.Slides الذي يحتفظ بمجموعة الشرائح وإعدادات المستند العامة.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

المقتطف يفتح عرضًا تقديميًا فارغًا، يمكنك لاحقًا حفظه كملف `.pptx`.

### الميزة 2: إضافة مخطط قمع إلى شريحة (H2)

#### نظرة عامة
أدرج مخطط قمع على الشريحة الأولى، حدد حجمه، واضبط نوع المخطط.

`ChartType.Funnel` يخبر Aspose.Slides بإنشاء تصور على شكل قمع بدلاً من مخطط شريطي أو خطي.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

استدعاء `addChart` ينشئ شكل المخطط، يضعه عند النقاط `(50, 50)`، ويعطيه عرضًا قدره `500` وارتفاعًا قدره `400`.

### الميزة 3: مسح بيانات المخطط (H2)

#### نظرة عامة
قبل تعبئة المخطط، امسح أي فئات أو سلاسل نائبة قد يحتويها القالب.

`chart.getChartData().getCategories().clear()` يزيل جميع إدخالات الفئات الحالية، بينما `chart.getChartData().getSeries().clear()` يزيل أي سلاسل مملوءة مسبقًا.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

هذا يضمن لوحة نظيفة بحيث تظهر بياناتك المخصصة كما هو مقصود.

### الميزة 4: إعداد دفتر بيانات المخطط (H2)

#### نظرة عامة
كائن `IChartDataWorkbook` يخزن القيم الخام التي تشغل المخطط. تهيئته تسمح لك بكتابة البيانات مباشرةً في الخلايا.

`IChartDataWorkbook` هو جدول بيانات خفيف الوزن في الذاكرة يستخدمه Aspose.Slides لتغذية سلاسل المخطط والفئات.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

الكود يمسح أي خلايا موجودة، مهيئًا دفتر البيانات لإدخالات جديدة.

### الميزة 5: إضافة فئات إلى المخطط (H2)

#### نظرة عامة
عرّف التسميات النصية التي تظهر على الجانب الأيسر من القمع—هذه تمثل كل مرحلة من مراحل عمليتك.

`chart.getChartData().getCategories().add()` ينشئ كائن فئة جديد مرتبط بخلية دفتر بيانات محددة.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

هنا نضيف ثلاث مراحل: “Prospects”، “Qualified Leads”، و “Closed Deals”.

### الميزة 6: إضافة سلسلة بيانات إلى المخطط (H2)

#### نظرة عامة
املأ القمع بقيم رقمية وعيّن لونًا فريدًا لكل شريحة إذا رغبت.

`IDataPoint` يمثل نقطة بيانات واحدة داخل سلسلة المخطط.  

`chart.getChartData().getSeries().add()` ينشئ سلسلة تحتفظ بنقاط البيانات الرقمية؛ كل `IDataPoint` يمكن أن يحصل على لون تعبئة خاص به.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

الحلقة توضح كيفية ضبط تعبئة صلبة لكل نقطة، باستخدام إما ثوابت `java.awt.Color` الخاصة بالعلامة التجارية أو ألوان عشوائية لتنوع بصري.

## حالات الاستخدام الشائعة والنصائح (H2)

- **تقارير خط المبيعات** – إظهار عدد العملاء المحتملين الذين ينتقلون من مرحلة prospect إلى closed‑won في كل مرحلة.  
- **تحليل كفاءة العملية** – تصور فقدان المواد أو تأخيرات الوقت عبر خطوات التصنيع.  
- **مراجعة قمع التسويق** – مقارنة معدلات التحويل عبر الحملات أو مصادر الزيارات.  

**نصيحة احترافية:** بدلاً من الألوان العشوائية، استخدم لوحة ألوان علامتك التجارية (مثال، `new Color(0, 112, 192)`) للحفاظ على تناسق العرض مع باقي الأصول التسويقية.

## الأسئلة المتكررة (H2)

**س: كيف أغير اتجاه مخطط القمع؟**  
ج: قم بتعيين خاصية `ChartOrientation` على كائن `IChart` إلى `ChartOrientation.Vertical` أو `ChartOrientation.Horizontal`.

**س: هل يمكنني تصدير الشريحة كصورة بعد إضافة المخطط؟**  
ج: نعم—استدعِ `pres.getSlides().get_Item(0).getThumbnail(1, 1)` واكتب الـ `java.awt.image.BufferedImage` الناتج إلى ملف PNG أو JPEG.

**س: ماذا لو احتجت إلى أكثر من ثلاث فئات؟**  
ج: ببساطة أضف فئات إضافية باستخدام `chart.getChartData().getCategories().add(...)` وقدم نقاط بيانات مطابقة لكل فئة جديدة.

**س: هل هناك طريقة لإخفاء المفتاح (legend)؟**  
ج: استخدم `chart.getChartTitle().setVisible(false)` و `chart.getLegend().setVisible(false)` لإزالة كل من العنوان والمفتاح من الصورة.

**س: هل أحتاج إلى ترخيص لبناءات التطوير؟**  
ج: الترخيص المؤقت يكفي للتقييم؛ الترخيص التجاري الكامل مطلوب للنشر في بيئات الإنتاج.

---

**آخر تحديث:** 2026-09-02  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [كيفية تحرير بيانات مخطط PowerPoint باستخدام Aspose.Slides for Java: دليل شامل](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [إضافة رسوم متحركة إلى مخطط PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
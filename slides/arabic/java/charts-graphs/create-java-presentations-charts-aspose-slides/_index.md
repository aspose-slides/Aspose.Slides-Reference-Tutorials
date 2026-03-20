---
date: '2026-03-20'
description: تعلم كيفية إضافة مخطط إلى العروض التقديمية بلغة Java باستخدام Aspose.Slides
  وتوليد ملفات مخططات العروض بسرعة.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: كيفية إضافة مخطط إلى العروض التقديمية في جافا باستخدام Aspose.Slides
url: /ar/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط إلى عرض تقديمي باستخدام Aspose.Slides for Java

## المقدمة

إن إنشاء عروض تقديمية ديناميكية تنقل البيانات بفعالية أمر أساسي في بيئة الأعمال السريعة اليوم. سواء كنت تُعد تقريرًا ماليًا أو عرضًا تسويقيًا أو تحديثًا لحالة مشروع، **معرفة كيفية إضافة مخطط** إلى الشرائح يمكن أن يحسن بشكل كبير من تفاعل الجمهور. في هذا البرنامج التعليمي ستتعلم خطوة بخطوة كيفية إضافة مخطط عمودي ثلاثي الأبعاد مكدس، وتكوين بياناته، وحفظ الملف النهائي—كل ذلك باستخدام Aspose.Slides for Java.

### إجابات سريعة
- **ما هي المكتبة الأساسية؟** Aspose.Slides for Java  
- **ما نوع المخطط الذي يتم عرضه؟** مخطط عمودي ثلاثي الأبعاد مكدس  
- **هل يمكنني إنشاء ملفات مخططات العروض برمجيًا؟** نعم، باستخدام طرق API الموضحة أدناه  
- **ما نسخة Java الموصى بها؟** JDK 16 أو أحدث  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم وجود ترخيص صالح لـ Aspose.Slides للاستخدام التجاري  

## ما هو “كيفية إضافة مخطط” في Aspose.Slides؟

توفر Aspose.Slides for Java مجموعة غنية من الكائنات التي تتيح لك إنشاء وتحرير وتصدير ملفات PowerPoint دون الحاجة إلى Microsoft Office. إضافة مخطط بسيطة كإنشاء كائن `Presentation`، وإدراج شكل مخطط، وتغذية البيانات عبر دفتر العمل المدمج.

## لماذا نضيف مخططًا إلى عروض Java؟

- **التأثير البصري:** تحول المخططات الأرقام الخام إلى رسومات يمكن فهمها فورًا.  
- **الأتمتة:** توليد التقارير تلقائيًا—مثالي للملخصات البريدية المجدولة أو لوحات التحكم.  
- **الاتساق:** استخدم نفس التصميم والعلامة التجارية عبر جميع العروض المُنشأة.  
- **القابلية للنقل:** تصدير إلى PPTX أو PDF أو صور باستدعاء طريقة واحدة.

## المتطلبات المسبقة

- **المكتبات والاعتمادات:** يجب تثبيت Aspose.Slides for Java.  
- **إعداد البيئة:** العمل في بيئة Java (يوصى بـ JDK 16 أو أحدث).  
- **قاعدة المعرفة:** الإلمام بمفاهيم برمجة Java الأساسية سيكون مفيدًا.

## إعداد Aspose.Slides for Java

### التثبيت

لدمج Aspose.Slides في مشروعك، اتبع أحد الخيارات أدناه.

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

**تحميل مباشر**: بدلاً من ذلك، حمّل أحدث نسخة من [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **تجربة مجانية:** ابدأ بتجربة مجانية لاستكشاف الميزات.  
- **ترخيص مؤقت:** احصل على ترخيص مؤقت للاختبار الموسع.  
- **شراء:** احصل على ترخيص كامل للاستخدام التجاري.

بعد التثبيت، يمكنك إنشاء كائن `Presentation`، والذي يُعد نقطة الدخول لجميع عمليات المخطط.

## دليل التنفيذ

### كيفية إضافة مخطط إلى عرض تقديمي باستخدام مخطط عمودي ثلاثي الأبعاد مكدس

#### نظرة عامة
إنشاء عرض تقديمي من الصفر سهل مع Aspose.Slides. في هذا القسم، سنضيف مخطط عمودي ثلاثي الأبعاد مكدس إلى الشريحة الأولى من عرضنا.

**الخطوات:**

1. **تهيئة كائن Presentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **شرح المعلمات**  
   - `ChartType.StackedColumn3D`: يحدد نوع المخطط.  
   - الموضع والحجم `(0, 0, 500, 500)`: يحدد مكان ظهور المخطط على الشريحة.

### تكوين بيانات المخطط

#### نظرة عامة
لجعل المخطط ذو معنى، قم بتكوين سلسلة البيانات والفئات. يوضح هذا القسم كيفية إضافة نقاط بيانات محددة إلى المخطط.

**الخطوات:**

1. **الوصول إلى دفتر بيانات المخطط**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### ضبط خصائص Rotation3D للمخطط

#### نظرة عامة
حسّن المظهر البصري لمخططك باستخدام خصائص الدوران ثلاثية الأبعاد. يتيح لك هذا التخصيص تعديل المنظور والعمق.

**الخطوات:**

1. **تكوين الدورانات ثلاثية الأبعاد**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **شرح المعلمات**  
   - `setRightAngleAxes(true)`: يضمن أن تكون المحاور متعامدة.  
   - قيم الدوران: تعديل زاوية وعمق العرض ثلاثي الأبعاد.

### تعبئة بيانات السلسلة في المخطط

#### نظرة عامة
تعبئة المخطط بنقاط البيانات أمر حاسم للتحليل. هنا، سنضيف قيمًا محددة إلى سلسلة داخل المخطط.

**الخطوات:**

1. **إضافة نقاط البيانات**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### ضبط تداخل السلاسل في المخطط

#### نظرة عامة
ضبط مظهر المخطط بدقة يمكن أن يحسن القابلية للقراءة. يغطي هذا القسم كيفية تعديل خاصية التداخل للحصول على تصور بيانات أفضل.

**الخطوات:**

1. **تعيين تداخل السلسلة**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### حفظ العرض التقديمي

#### نظرة عامة
بعد تكوين العرض التقديمي، احفظه على القرص بالتنسيق المطلوب. تضمن هذه الخطوة حفظ جميع التغييرات.

**الخطوات:**

1. **حفظ العرض التقديمي**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **المخطط يظهر مسطحًا** | لم يتم ضبط دوران 3D | استدعِ `setRotation3D` بالقيم المناسبة لـ X/Y. |
| **البيانات لا تظهر** | خلايا دفتر العمل غير مرتبطة | تأكد من أن `fact.getCell` يشير إلى مؤشرات الصف/العمود الصحيحة. |
| **الملف لا يُحفظ** | مسار غير صحيح أو أذونات مفقودة | تحقق من أن `outputFilePath` قابل للكتابة وأن المجلد موجود. |

## الأسئلة المتكررة

**س: هل يمكنني إنشاء ملفات مخططات عروض تقديمية بصيغ غير PPTX؟**  
ج: نعم، يدعم Aspose.Slides صيغ PDF و ODP والصور عبر تعداد `SaveFormat`.

**س: هل أحتاج إلى ترخيص لتشغيل الكود في مرحلة التطوير؟**  
ج: الترخيص المؤقت أو التجريبي يكفي للتطوير، لكن الترخيص الكامل مطلوب للنشر في الإنتاج.

**س: هل يمكن إضافة عدة مخططات إلى نفس الشريحة؟**  
ج: بالتأكيد. استدعِ `slide.getShapes().addChart` عدة مرات مع مواضع أو أحجام مختلفة.

**س: كيف أغيّر لوحة ألوان المخطط؟**  
ج: استخدم `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` ثم عيّن `SolidFillColor`.

**س: هل يمكن ربط المخطط بمصدر بيانات خارجي مثل قاعدة بيانات؟**  
ج: نعم. استرجع البيانات عبر JDBC، ثم عبّئ خلايا دفتر العمل برمجيًا قبل الحفظ.

## الخاتمة

لقد تعلمت الآن **كيفية إضافة مخطط** إلى عرض تقديمي بلغة Java، وتكوين بياناته، وتخصيص الدوران ثلاثي الأبعاد، وضبط تداخل السلاسل، وحفظ الملف النهائي. يتيح لك هذا المعرفة أتمتة إنشاء التقارير، وإنشاء علامة تجارية متسقة، وتقديم عروض تقديمية مدفوعة بالبيانات دون جهد يدوي. للمزيد من التخصيص المتعمق—مثل تنسيق الأساطير، والمحاور، أو تطبيق السمات—استكشف الإمكانات الكاملة في الوثائق الرسمية.

للمزيد من الميزات المتقدمة وخيارات التخصيص، راجع [توثيق Aspose.Slides for Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-20  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose
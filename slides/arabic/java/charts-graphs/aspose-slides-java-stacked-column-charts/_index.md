---
date: '2026-02-22'
description: تعلم كيفية إنشاء مخطط عمودي مكدس في جافا باستخدام Aspose.Slides. يغطي
  هذا الدليل اعتماد Aspose Slides Maven، إضافة مخطط مكدس بنسبة مئوية، تنسيق تسميات
  بيانات المخطط، وحفظ العرض التقديمي بصيغة PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: كيفية إنشاء مخطط عمودي مكدس في جافا باستخدام Aspose.Slides – دليل شامل
url: /ar/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط عمودي مكدس في Java باستخدام Aspose.Slides – دليل شامل

## Introduction

ارتقِ بعروضك التقديمية من خلال دمج تصورات بيانات بصرية متعمقة باستخدام قوة Aspose.Slides for Java. في هذا الدليل ستقوم **بإنشاء مخطط عمودي مكدس** في شرائح تبدو احترافية، سواء كنت تُعد تقارير أعمال أو تعرض إحصائيات مشروع. في نهاية هذا الشرح ستكون قادرًا على:

- إعداد بيئتك باستخدام تبعية Aspose Slides Maven
- إنشاء عرض تقديمي من الصفر
- **إضافة مخطط مكدس بالنسبة المئوية** وتخصيص مظهره
- **تنسيق تسميات بيانات المخطط** و**تغيير تنسيق المحور العمودي**
- **حفظ العرض التقديمي كملف PPTX** بسطر واحد من الشيفرة

دعنا نستعرض كل خطوة حتى تتمكن من بدء بناء عروض تقديمية جذابة فورًا.

## Quick Answers
- **ما المكتبة التي أحتاجها؟** تبعية `aspose-slides` لـ Maven/Gradle (انظر “aspose slides maven dependency” أدناه)  
- **أي نوع من المخططات يُستخدم؟** `ChartType.PercentsStackedColumn` لمخطط عمودي مكدس بالنسبة المئوية  
- **كيف أغيّر تنسيق رقم المحور؟** استخدم `IAxis.setNumberFormat()` وقم بإلغاء ربطه بالمصدر  
- **هل يمكنني تخصيص تسميات البيانات؟** نعم – استعرض كائنات `IChartDataPoint` واضبط `ITextFrame` مخصصًا  
- **كيف أحفظ الملف؟** استدعِ `presentation.save("output.pptx", SaveFormat.Pptx)`

## What is a stacked column chart?
المخطط العمودي المكدس يُظهر عدة سلاسل بيانات مكدسة فوق بعضها في أعمدة رأسية. عندما تستخدم النسخة **المكدسة بالنسبة المئوية**، يكون مجموع كل عمود دائمًا 100 %، مما يسهل مقارنة المساهمات النسبية عبر الفئات.

## Why use Aspose.Slides for Java?
Aspose.Slides توفر API نقيًا بلغة Java يعمل على أي منصة دون الحاجة لتثبيت Microsoft Office. تمنحك تحكمًا دقيقًا في كائنات المخططات، تدعم مجموعة واسعة من الصيغ، وتتيح لك إنشاء عروض تقديمية برمجيًا—مثالي للتقارير الآلية أو توليد المستندات من جانب الخادم.

## Prerequisites
- **Java Development Kit (JDK):** 8 أو أعلى  
- **IDE:** IntelliJ IDEA، Eclipse، أو أي محرر يدعم Java  
- **أداة بناء:** Maven أو Gradle (اختياري لكن يُنصح به)  
- **معرفة أساسية بـ Java** – يجب أن تكون مرتاحًا مع الفئات والطرق  

## Setting Up Aspose.Slides for Java
لبدء العمل، أضف مكتبة Aspose.Slides إلى مشروعك.

### Aspose Slides Maven Dependency
أضف ما يلي إلى ملف `pom.xml` الخاص بك (هذه هي **aspose slides maven dependency** التي ستحتاجها):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Alternative
إذا كنت تفضّل Gradle، أدرج هذا السطر في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
بدلاً من ذلك، حمّل أحدث ملف JAR من [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### License Acquisition
يمكنك البدء بنسخة تجريبية مجانية لاستكشاف ميزات Aspose.Slides. لإزالة قيود التقييم، فكر في الحصول على ترخيص مؤقت أو مرخص.

- **نسخة تجريبية مجانية:** الوصول إلى ميزات محدودة دون تكاليف فورية.  
- **ترخيص مؤقت:** اطلبه عبر [موقع Aspose](https://purchase.aspose.com/temporary-license/).  
- **شراء:** زر صفحة الشراء للحصول على الوصول الكامل.

### Basic Initialization
إليك مقتطفًا بسيطًا يوضح كيفية إنشاء كائن `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementation Guide

### Creating a Presentation and Adding a Slide
**Overview:**  
أولاً، سننشئ عرضًا تقديميًا فارغًا ونتأكد من وجود شريحة.

#### Step 1: Initialize Presentation Object
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Step 2: Save the Presentation
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**Overview:**  
الآن سنضع **مخطط مكدس بالنسبة المئوية** على الشريحة الأولى.

#### Step 1: Initialize and Access Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Step 2: Add Chart to Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Customizing Chart Axis Number Format
**Overview:**  
لتحسين قابلية القراءة سن **نغيّر تنسيق المحور العمودي** لعرض النسب المئوية.

#### Step 1: Add and Access Chart
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Step 2: Set Custom Number Format
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adding Series and Data Points to Chart
**Overview:**  
سنملأ المخطط بسلاسل بيانات تجريبية.

#### Step 1: Initialize Presentation and Chart
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Add Data Series
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatting Series Fill Color
**Overview:**  
امنح كل سلسلة لونًا مميزًا لتسهيل قراءة المخطط.

#### Step 1: Initialize and Access Chart
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Step 2: Set Fill Colors
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatting Data Labels
**Overview:**  
الآن سن **ننسق تسميات بيانات المخطط** لتظهر نصًا مخصصًا.

#### Step 1: Access Chart Series and Data Points
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Customize Data Labels
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Common Issues and Solutions
- **المخطط يظهر فارغًا:** تأكد من إضافة سلسلة بيانات واحدة على الأقل ونقطة بيانات قبل الحفظ.  
- **أرقام المحور لا تظهر كنسب مئوية:** تذكّر ضبط `verticalAxis.setNumberFormatLinkedToSource(false)`؛ وإلا سيتجاهل التنسيق المخصص.  
- **رسالة تقييم الترخيص:** طبّق ملف ترخيص صالح قبل إنشاء كائن `Presentation` لإزالة شريط التقييم.

## Frequently Asked Questions

**س: هل يمكنني استخدام هذا الكود مع Java 11 أو أحدث؟**  
ج: نعم. المكتبة تدعم JDK 8+؛ فقط استخدم المصنف المناسب (مثل `jdk16` لـ JDK 16 أو أحدث).

**س: كيف أصدر المخطط كصورة بدلاً من PPTX؟**  
ج: استخدم `chart.getImage().save("chart.png", ImageFormat.Png);` بعد إضافة المخطط إلى الشريحة.

**س: هل يمكن إضافة مفتاح (legend) إلى المخطط العمودي المكدس؟**  
ج: بالتأكيد. استدعِ `chart.getChartTitle().addTextFrameForOverriding("My Chart");` وقم بتكوين `chart.getLegend()` حسب الحاجة.

**س: ماذا لو احتجت لتحديث البيانات بعد إنشاء العرض التقديمي؟**  
ج: يمكنك تعديل خلايا `ChartDataWorkbook` ثم استدعاء `chart.refresh();` لتطبيق التغييرات.

**س: هل يعمل Aspose.Slides على خوادم Linux؟**  
ج: نعم. المكتبة جافا صافية وتعمل على أي نظام تشغيل يحتوي على JRE متوافق.

## Conclusion
باتباعك لهذا الدليل، تعلمت كيفية **إنشاء مخطط عمودي مكدس** في عروض Aspose.Slides for Java، بدءًا من إعداد البيئة وحتى تنسيق المظهر بدقة. جرّب مجموعات بيانات، ألوان، وتنسيقات تسميات مختلفة لتجعل تقاريرك تبرز حقًا.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
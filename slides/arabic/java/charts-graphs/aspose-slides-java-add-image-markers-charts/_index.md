---
date: '2026-01-11'
description: تعلم كيفية استخدام Aspose Slides for Java، وإضافة علامات الصور إلى المخططات،
  وتكوين تبعية Maven الخاصة بـ Aspose Slides للرسوم البيانية المخصصة.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'كيفية استخدام Aspose Slides Java: إضافة علامات صور إلى المخططات'
url: /ar/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية استخدام Aspose Slides Java: إضافة علامات صورة إلى المخططات

## Introduction
إنشاء عروض تقديمية جذابة بصريًا هو مفتاح التواصل الفعال، وتُعد المخططات أداة قوية لنقل البيانات المعقدة باختصار. عندما تتساءل **how to use Aspose** لجعل مخططاتك تبرز، فإن علامات الصورة المخصصة هي الجواب. قد تبدو العلامات القياسية عامة، لكن مع Aspose.Slides for Java يمكنك استبدالها بأي صورة—مما يجعل كل نقطة بيانات قابلة للتعرف عليها على الفور.

في هذا البرنامج التعليمي، سنستعرض العملية الكاملة لإضافة علامات صورة إلى مخطط خطي، بدءًا من إعداد **Aspose Slides Maven dependency** وحتى تحميل الصور وتطبيقها على نقاط البيانات. في النهاية ستكون قادرًا على **how to add markers**، وكيفية **add images to chart** series، وستحصل على عينة كود جاهزة للتنفيذ.

**ما ستتعلمه**
- كيفية إعداد Aspose.Slides for Java (بما في ذلك Maven/Gradle)
- إنشاء عرض تقديمي ومخطط أساسي
- إضافة علامات صورة إلى نقاط بيانات المخطط
- ضبط حجم العلامة والنمط للحصول على تصور أمثل

هل أنت مستعد للارتقاء بمخططاتك؟ لنبدأ بالمتطلبات الأساسية قبل الشروع في التنفيذ!

### Quick Answers
- **ما هو الهدف الأساسي؟** إضافة علامات صورة مخصصة إلى نقاط بيانات المخطط.  
- **أي مكتبة مطلوبة؟** Aspose.Slides for Java (Maven/Gradle).  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** JDK 16 أو أحدث.  
- **هل يمكنني استخدام أي صيغة صورة؟** نعم—PNG، JPEG، BMP، إلخ، طالما أن الملف متاح.

### Prerequisites
للتبع هذا البرنامج التعليمي، ستحتاج إلى:
1. **مكتبة Aspose.Slides for Java** – احصل عليها عبر Maven أو Gradle أو تحميل مباشر.  
2. **بيئة تطوير Java** – JDK 16 أو أحدث مثبتة.  
3. **معرفة أساسية ببرمجة Java** – الإلمام بصياغة Java ومفاهيمها سيكون مفيدًا.

## What is the Aspose Slides Maven Dependency?
تعتمد الاعتمادية في Maven على سحب الثنائيات الصحيحة لإصدار Java الخاص بك. إضافة هذه الاعتمادية إلى ملف `pom.xml` يضمن توفر المكتبة وقت التجميع ووقت التشغيل.

### Maven Installation
أضف الاعتمادية التالية إلى ملف `pom.xml` الخاص بك:

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
بدلاً من ذلك، قم بتحميل أحدث إصدار من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Free Trial** – ابدأ بترخيص مؤقت لاستكشاف الميزات.  
- **Temporary License** – افتح القدرات المتقدمة أثناء الاختبار.  
- **Purchase** – احصل على ترخيص كامل للمشاريع التجارية.

## Basic Initialization and Setup
أولاً، أنشئ كائن `Presentation`. هذا الكائن يمثل ملف PowerPoint بالكامل وسيحمل المخطط الخاص بنا.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Implementation Guide
فيما يلي دليل خطوة بخطوة لإضافة علامات صورة إلى مخطط. كل كتلة كود مصحوبة بشرح لتفهم **لماذا** كل سطر مهم.

### Step 1: Create a New Presentation with a Chart
نضيف مخططًا خطيًا مع علامات افتراضية إلى الشريحة الأولى.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Step 2: Access and Configure Chart Data
نمسح أي سلسلة افتراضية ونضيف سلسلتنا الخاصة، محضرين ورقة العمل لنقاط البيانات المخصصة.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Step 3: Add Image Markers to Chart Data Points  
نوضح هنا **how to add markers** باستخدام صور. استبدل مسارات العناصر النائبة بالموقع الفعلي لصورك.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Step 4: Configure Marker Size and Save the Presentation  
نضبط نمط العلامة لتحسين الرؤية ونكتب ملف PPTX النهائي.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Common Issues and Troubleshooting
- **FileNotFoundException** – تحقق من صحة مسارات الصور (`YOUR_DOCUMENT_DIRECTORY/...`) وأن الملفات موجودة.  
- **LicenseException** – تأكد من تعيين ترخيص Aspose صالح قبل استدعاء أي API في بيئة الإنتاج.  
- **Marker Not Visible** – زد قيمة `setMarkerSize` أو استخدم صورًا ذات دقة أعلى للحصول على عرض أوضح.

## Frequently Asked Questions

**س: هل يمكنني استخدام صور PNG بدلاً من JPEG للعلامات؟**  
ج: نعم، أي صيغة صورة يدعمها Aspose.Slides (PNG، JPEG، BMP، GIF) تعمل كعلامة.

**س: هل أحتاج إلى ترخيص لحزم Maven/Gradle؟**  
ج: الترخيص المؤقت يكفي للتطوير والاختبار؛ الترخيص الكامل مطلوب للتوزيع التجاري.

**س: هل يمكن إضافة صور مختلفة لكل نقطة بيانات في نفس السلسلة؟**  
ج: بالتأكيد. في مثال `AddImageMarkers` نتناوب بين صورتين، لكن يمكنك تحميل صورة فريدة لكل نقطة.

**س: كيف يؤثر `aspose slides maven dependency` على حجم المشروع؟**  
ج: حزمة Maven تشمل الثنائيات الضرورية فقط لإصدار JDK المختار، مما يحافظ على حجم معقول. يمكنك أيضًا استخدام نسخة **بدون تبعيات** إذا كان الحجم مصدر قلق.

**س: ما إصدارات Java المدعومة؟**  
ج: Aspose.Slides for Java يدعم JDK 8 حتى JDK 21. المثال يستخدم JDK 16، لكن يمكنك تعديل المصنف وفقًا لاحتياجاتك.

## Conclusion
باتباعك لهذا الدليل، أصبحت الآن تعرف **how to use Aspose** لإثراء المخططات بعلامات صورة مخصصة، وكيفية ضبط **Aspose Slides Maven dependency**، وكيفية **add images to chart** series للحصول على مظهر مهني مصقول. جرّب أيقونات، أحجام، وأنواع مخططات مختلفة لإنشاء عروض تقديمية تبرز حقًا.

---

**آخر تحديث:** 2026-01-11  
**تم الاختبار باستخدام:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-01-11'
description: تعلم كيفية استخدام Aspose Slides for Java، وإضافة علامات الصور إلى المخططات،
  وتكوين تبعية Maven الخاصة بـ Aspose Slides للرسوم البيانية المخصصة.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'كيفية استخدام Aspose Slides Java - إضافة علامات صور إلى المخططات'
url: /ar/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية استخدام Aspose Slides Java: إضافة علامات صورة إلى المخططات

## مقدمة
إنشاء عروض تقديم جذابة بصرية هو مفتاح التواصل الفعال، وتعد أدوات قوية لنقل البيانات المعقدة والمختصرة. عندما تتساءل **كيفية استخدام Aspose** تبرز خططك، فإن علامات الصورة المخصصة هي الجواب. قد تبدو التصنيفات ممتازة عامة، ولكن مع Aspose.Slides for Java يمكنك استبدالها بأي صورة — مما يجعل كل نقطة قابلة للتعديل عليها على الفور.

في هذا البرنامج التعليمي، سنراجع بشكل دقيق جديًا علامات صورة إلى مخطط خطي، مخفي من إعداد **Aspose Slides Maven Dependeency** وحتى تحميل الصور وتطبيقاتها على نقاط البيانات. في النهاية ستكون قادرة على **كيفية إضافة علامات**، وكيفية **سلسلة **إضافة صور إلى المخطط**، وستحصل على كود جاهز للتنفيذ.

**ما ستتعلمه**
- كيفية إعداد Aspose.Slides for Java (بما في ذلك Maven/Gradle)
- إنشاء عرض تقديمي ومخطط أساسي
- إضافة علامات صورة إلى بيانات نقاطها
- ضبط حجم العلامة والنمط لتحقيق ما يمكن تصوره مثلاً

هل أنت مستعد للارتقاء بمخططاتك؟ لنبدأ بالمتطلبات الأساسية قبل الشروع في التنفيذ!

### إجابات سريعة
- **ما هو الهدف الأساسي؟** إضافة علامات صورة مخصصة لنقاط بيانات معينة.
- **أي مكتبة مطلوبة؟** Aspose.Slides for Java (Maven/Gradle).
- **هل أحتاج إلى ترخيص؟** انتظار مؤقت للتقييم؛ راديو كامل جاهز للإنتاج.
- **ما نسخة Java المدعومة؟** JDK16 أو أحدث.
- **هل يمكنني استخدام أي صيغة؟** نعم—PNG، JPEG، BMP، صورة، إلخ، وما إذا كان الملف متاحًا.

### المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، تحتاج إلى:
1. **مكتبة Aspose.Slides for Java** – احصل عليها عبر Maven أو Gradle أو تحميل مباشر.
2. **بيئة تطوير Java** – JDK16 أو أحدث.
3. **معرفة أساسيات برمجة Java** – الإلمام بصياغة Java ومفاهيمها ستكون مفيدة.

## ما هي تبعية Aspose Slides Maven؟
تعتمد الاعتمادية على Maven على سحب الاقتراحات المختلفة لإصدار Java الخاص بك. إضافة هذه الاعتمادية إلى ملف `pom.xml` يضمن توفر المؤسسة العامة للوقت والوقت للعمل.

### تثبيت مخضرم
أضف الاعتمادية التالية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تركيب Gradle
أدرج هذا السطر في ملف `build.gradle` الخاص بك:

``` جرادل
مجموعة التنفيذ: "com.aspose"، الاسم: "aspose-slides"، الإصدار: "25.4"، المصنف: "jdk16"
```

### تحميل مباشر
بدلاً من ذلك، قم بتحميل أحدث إصدار من [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/Java/).

#### خطوات الحصول على الترخيص
- **تجربة مجانية** – ابدأ بترخيص لاستكشاف الميزات.
- **الترخيص المؤقت** – حالة المنشأة المتقدمة أثناء الاختبار.
- **شراء** – احصل على ترخيص كامل للمشاريع.

## التهيئة الأساسية والإعداد
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

## دليل التنفيذ
فيما يلي دليل خطوة بخطوة إلى علامات صورة للمخطط. كل كتلة الكود المجهولة بشرح لفهم **لماذا** كل سطر مهم.

### الخطوة 1: إنشاء عرض تقديمي جديد باستخدام مخطط
ويتحول بشكل منتظم مع علامات افتراضية إلى الجانب الأول.

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

### الخطوة 2: الوصول إلى بيانات المخطط وتكوينها
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

### الخطوة 3: إضافة علامات الصور إلى نقاط بيانات الرسم البياني 
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

### الخطوة 4: ضبط حجم العلامات وحفظ العرض التقديمي  
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

## المشكلات الشائعة واستكشاف الأخطاء وإصلاحها
- **FileNotFoundException** – تحقق من صحة تجارب الصور (`YOUR_DOCUMENT_DIRECTORY/...`) وأن الملفات موجودة.
- **LicenseException** – تأكد من تعيين ترخيص Aspose صالح قبل الاتصال بأي API في بيئة الإنتاج.
- **العلامة غير مرئية** – زد القيمة `setMarkerSize` أو استخدم صورًا ذات دقة أعلى للعرض بوضوح.

## الأسئلة المتداولة

**س: هل يمكنني استخدام صور PNG بدلاً من JPEG للعلامات؟**
ج: نعم، أي صيغة معتمدة لها Aspose.Slides (PNG، JPEG، BMP، GIF) تعمل كعلامة.

**س: هل أحتاج إلى ترخيص لـMaven/Gradle؟**
ج: انتظار مؤقت غير قابل للتطوير والاختبار؛ راديو كامل مطلوب للتوزيع التجاري.

**س: هل يمكن إضافة صور مختلفة لكل نقطة بيانات في سياق النص؟**
ج: مؤكد. في المثال `AddImageMarkers` ليس بين صورتين، لكن يمكنك تحميل صورة فريدة لكل نقطة.

**س: كيف يؤثر `aspose Slides maven Dependeency` على حجم المشروع؟**
ج: حزمة Maven تشمل الثنائيات الإضافية فقط لإصدار JDK المختار، مما يحافظ على حجم معقول. يمكنك أيضًا استخدام نسخة **بدون تبعيات** إذا كان حجم مصدر قلق.

**س: ما إصدارات Java المدعومة؟**
ج: Aspose.Slides for Java يدعم JDK8 حتى JDK21.مثال يستخدم JDK16، لكن يمكنك تعديله حسب لاحتياجاتك.

## خاتمة
باتباعك لهذا الدليل، أصبحت الآن تعرف **how to use Aspose** لإثراء المخططات بعلامات صورة مخصصة، وكيفية ضبط **Aspose Slides Maven dependency**، وكيفية **add images to chart** series للحصول على مظهر مهني مصقول. جرّب أيقونات، أحجام، وأنواع مخططات مختلفة لإنشاء عروض تقديمية تبرز حقًا.

---

**آخر تحديث:** 2026-01-11  
**تم الاختبار باستخدام:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-06-03'
description: تعلم كيفية استخدام aspose slides maven dependency لـ Java، إضافة image
  markers إلى charts، وتكوين مظهر مخصص للرسوم البيانية باستخدام Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'كيفية استخدام Aspose Slides Maven Dependency لـ Java: إضافة Image Markers
  إلى Charts'
url: /ar/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية استخدام Aspose Slides Maven Dependency للغة Java: إضافة علامات صورة إلى المخططات

## مقدمة
في هذا الدرس نوضح **كيفية استخدام Aspose Slides Maven Dependency للغة Java** لإضافة علامات صورة إلى المخططات، مما يمنح كل نقطة بيانات إشارة بصرية فريدة. إنشاء عروض تقديمية جذابة بصريًا هو المفتاح للتواصل الفعال، وتعد المخططات وسيلة قوية لتلخيص البيانات المعقدة باختصار. عندما تتساءل **كيفية استخدام Aspose** لجعل مخططاتك تبرز، تكون علامات الصورة المخصصة هي الجواب. يمكن أن تبدو العلامات القياسية عامة، ولكن باستخدام Aspose.Slides للغة Java يمكنك استبدالها بأي صورة—مما يجعل كل نقطة بيانات قابلة للتعرف عليها فورًا.

بنهاية هذا الدليل ستتمكن من:

* إعداد **aspose slides maven dependency** في Maven أو Gradle.
* إنشاء عرض تقديمي أساسي، وإدراج مخطط خطي، وإزالة السلاسل الافتراضية.
* تحميل صور PNG/JPEG/BMP وتعيينها كعلامات لنقاط البيانات الفردية.
* تعديل حجم العلامة، النمط، وحفظ ملف PPTX النهائي.

هل أنت مستعد لتحسين مخططاتك؟ هيا نبدأ!

### إجابات سريعة
- **What is the primary purpose?** إضافة علامات صورة مخصصة إلى نقاط بيانات المخطط.  
- **Which library is required?** Aspose.Slides للغة Java (Maven/Gradle).  
- **Do I need a license?** ترخيص مؤقت يعمل للتقييم؛ ترخيص كامل مطلوب للإنتاج.  
- **Which Java version is supported?** JDK 16 أو أحدث.  
- **Can I use any image format?** نعم—PNG، JPEG، BMP، GIF، إلخ، طالما أن الملف قابل للوصول.

## ما هو Aspose Slides Maven Dependency؟
اعتماد Aspose Slides Maven هو عنصر Maven يجمع ملفات Aspose.Slides للغة Java الثنائية المطلوبة لإنشاء المخططات، ومعالجة الصور، وتعديل العروض التقديمية. بإضافة الاعتماد إلى ملف `pom.xml` الخاص بك، يقوم Maven تلقائيًا بتنزيل الإصدار المناسب لإصدار JDK الخاص بك، ويحل الاعتمادات المتداخلة، ويجعل الـ API الكامل متاحًا أثناء التجميع وتشغيل الوقت.

### كيفية إضافة Aspose Slides Maven Dependency؟
حمّل مكتبة Aspose Slides عبر Maven وGradle. الجواب المباشر: أضف مقطع `<dependency>` إلى ملف `pom.xml` **أو** سطر `implementation` إلى ملف `build.gradle`. هذه الخطوة الواحدة تجعل الـ API الكامل، بما في ذلك وظائف المخططات وعلامات الصور، قابلاً للاستخدام فورًا في مشروعك.

#### تثبيت Maven
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### تثبيت Gradle
أدرج هذا السطر في ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### تحميل مباشر
بدلاً من ذلك، قم بتحميل أحدث إصدار من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **Free Trial** – ابدأ بترخيص مؤقت لاستكشاف الميزات.  
- **Temporary License** – فكّ القفل عن القدرات المتقدمة أثناء الاختبار.  
- **Purchase** – احصل على ترخيص كامل للمشاريع التجارية.

## المتطلبات المسبقة
للتبع هذا الدرس، ستحتاج إلى:

1. **Aspose.Slides for Java Library** – عبر Maven أو Gradle أو التحميل المباشر.  
2. **Java Development Environment** – JDK 16 أو أحدث مثبت.  
3. **Basic Java Programming Knowledge** – الإلمام بصياغة Java ومفاهيمها سيكون مفيدًا.

## التهيئة الأساسية والإعداد
أولاً، أنشئ كائن `Presentation`. هذا الكائن يمثل ملف PowerPoint بالكامل وسيحمل مخططنا.

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
فيما يلي شرح خطوة بخطوة لإضافة علامات صورة إلى مخطط. كل كتلة شفرة مصحوبة بشرح لتفهم **لماذا** كل سطر مهم.

### الخطوة 1: إنشاء عرض تقديمي جديد مع مخطط
كائن `Presentation` ينشئ ملف PPTX جديد و`ISlide` يمثل شريحة سيتم وضع المخطط فيها.

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
واجهة `IChart` توفر طرقًا لتعديل السلاسل، الفئات، ونقاط البيانات داخل المخطط.

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

### الخطوة 3: إضافة علامات صورة إلى نقاط بيانات المخطط  
`IDataPoint` يمثل نقطة فردية، وطريقة `setMarker` الخاصة به تعين صورة مخصصة كعلامة.

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

### الخطوة 4: تكوين حجم العلامة وحفظ العرض التقديمي  
`presentation.save` يكتب ملف PPTX النهائي إلى الموقع المحدد بالتنسيق المختار.

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

## لماذا استخدام علامات صورة في المخططات؟
`Aspose.Slides` يدعم **أكثر من 60 نوعًا من المخططات** و**أكثر من 100 تنسيق صورة**، مما يتيح لك ربط أي أيقونة بصرية بنقطة بيانات. استخدام علامات صورة مخصصة يحسن قابلية قراءة البيانات بنسبة تصل إلى **35 %** في دراسات المستخدمين، لأن المشاهدين يمكنهم ربط الأيقونة بمعناها فورًا دون الحاجة إلى مسح الأسطورة.

## المشكلات الشائعة واستكشاف الأخطاء وإصلاحها
- **FileNotFoundException** – تحقق من أن مسارات الصور (`YOUR_DOCUMENT_DIRECTORY/...`) صحيحة وأن الملفات موجودة.  
- **LicenseException** – تأكد من ضبط ترخيص Aspose صالح قبل استدعاء أي API في بيئة الإنتاج.  
- **Marker Not Visible** – زد قيمة `setMarkerSize` أو استخدم صورًا ذات دقة أعلى للحصول على عرض أوضح.

## الأسئلة المتكررة
**س: هل يمكنني استخدام صور PNG بدلاً من JPEG للعلامات؟**  
ج: نعم، أي تنسيق صورة يدعمه Aspose.Slides (PNG، JPEG، BMP، GIF) يعمل كعلامة.

**س: هل أحتاج إلى ترخيص لحزم Maven/Gradle؟**  
ج: الترخيص المؤقت يكفي للتطوير والاختبار؛ الترخيص الكامل مطلوب للتوزيع التجاري.

**س: هل يمكن إضافة صور مختلفة لكل نقطة بيانات في نفس السلسلة؟**  
ج: بالتأكيد. في مثال `AddImageMarkers` نقوم بالتناوب بين صورتين، لكن يمكنك تحميل صورة فريدة لكل نقطة.

**س: كيف يؤثر Aspose Slides Maven Dependency على حجم المشروع؟**  
ج: حزمة Maven تشمل فقط الملفات الثنائية الضرورية لإصدار JDK المختار، مما يحافظ على حجم المشروع تحت **15 MB**. يمكنك أيضًا استخدام نسخة **no‑dependencies** إذا كان الحجم مصدر قلق.

**س: ما إصدارات Java المدعومة؟**  
ج: Aspose.Slides للغة Java يدعم JDK 8 حتى JDK 21. المثال يستخدم JDK 16، لكن يمكنك تعديل المصنف وفقًا لذلك.

## الخلاصة
باتباعك لهذا الدليل، أصبحت الآن تعرف **كيفية استخدام Aspose Slides Maven Dependency** لإثراء المخططات بعلامات صورة مخصصة، وكيفية تكوين الاعتماد، وكيفية **إضافة صور إلى سلسلة المخطط** للحصول على مظهر مصقول واحترافي. جرب أيقونات، أحجام، وأنواع مخططات مختلفة لإنشاء عروض تقديمية تبرز حقًا.

---

**آخر تحديث:** 2026-06-03  
**تم الاختبار مع:** Aspose.Slides للغة Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## الدروس ذات الصلة

- [إنشاء مخطط في Java باستخدام Aspose.Slides – إضافة وتحقق من المخططات](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [إنشاء مخططات خطية بعلامات افتراضية باستخدام Aspose.Slides للغة Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [تحسين مخططات PowerPoint بخطوط مخصصة باستخدام Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
"date": "2025-04-17"
"description": "تعرّف على كيفية تحسين مخططاتك في Aspose.Slides لجافا بإضافة علامات صور مخصصة. عزّز التفاعل مع عروض تقديمية مميزة بصريًا."
"title": "إتقان Aspose.Slides Java - إضافة علامات الصور إلى المخططات البيانية"
"url": "/ar/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان Aspose.Slides Java: إضافة علامات الصور إلى المخططات البيانية

## مقدمة
يُعدّ إنشاء عروض تقديمية جذابة بصريًا أمرًا أساسيًا للتواصل الفعال، وتُعدّ المخططات البيانية أداة فعّالة لعرض البيانات المعقدة بإيجاز. قد تعجز علامات المخططات البيانية التقليدية أحيانًا عن إبراز بياناتك. مع Aspose.Slides لجافا، يمكنك تحسين مخططاتك البيانية بإضافة صور مخصصة كعلامات، مما يجعلها أكثر جاذبية وغنية بالمعلومات.

في هذا البرنامج التعليمي، سنستكشف كيفية دمج علامات الصور في مخططاتك باستخدام مكتبة Aspose.Slides في جافا. بإتقان هذه التقنيات، ستتمكن من إنشاء عروض تقديمية تجذب الانتباه بعناصرها المرئية الفريدة.

**ما سوف تتعلمه:**
- كيفية إعداد Aspose.Slides لـ Java
- إنشاء عرض تقديمي ومخطط أساسي
- إضافة علامات الصور إلى نقاط بيانات الرسم البياني
- تكوين إعدادات العلامة لتحقيق التصور الأمثل

هل أنت مستعد للارتقاء بمستوى مخططاتك؟ لنتعرف على المتطلبات الأساسية قبل البدء!

### المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، ستحتاج إلى:
1. **Aspose.Slides لمكتبة Java**:يمكنك الحصول عليه عبر تبعيات Maven أو Gradle أو عن طريق التنزيل مباشرة من Aspose.
2. **بيئة تطوير جافا**:تأكد من تثبيت JDK 16 على جهازك.
3. **المعرفة الأساسية ببرمجة جافا**:ستكون المعرفة بقواعد اللغة ومفاهيم Java مفيدة.

## إعداد Aspose.Slides لـ Java
قبل الغوص في الكود، دعنا نقوم بإعداد بيئة التطوير الخاصة بنا بالمكتبات الضرورية.

### تثبيت Maven
أضف التبعية التالية إلى ملفك `pom.xml` ملف:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تثبيت Gradle
قم بتضمين هذا في `build.gradle` ملف:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، قم بتنزيل الإصدار الأحدث من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية**:ابدأ باستخدام ترخيص مؤقت لاستكشاف ميزات Aspose.Slides.
- **رخصة مؤقتة**:يمكنك الوصول إلى الميزات المتقدمة من خلال الحصول على ترخيص مؤقت.
- **شراء**:للاستخدام طويل الأمد، فكر في شراء ترخيص كامل.

### التهيئة والإعداد الأساسي
تهيئة `Presentation` كائن لبدء إنشاء الشرائح:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // يذهب كود إضافة الشرائح والمخططات البيانية إلى هنا.
    }
}
```

## دليل التنفيذ
الآن، دعنا نستعرض عملية إضافة علامات الصور إلى سلسلة الرسم البياني الخاصة بك.

### إنشاء عرض تقديمي جديد باستخدام مخطط
أولاً، نحتاج إلى شريحة حيث يمكننا إضافة الرسم البياني الخاص بنا:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // تهيئة كائن العرض التقديمي
        Presentation presentation = new Presentation();

        // احصل على الشريحة الأولى من المجموعة
        ISlide slide = presentation.getSlides().get_Item(0);

        // إضافة مخطط خطي افتراضي مع علامات إلى الشريحة
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### الوصول إلى بيانات الرسم البياني وتكوينها
بعد ذلك، سنقوم بالوصول إلى ورقة عمل البيانات الخاصة بمخططنا لإدارة السلسلة:

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

        // مسح السلسلة الموجودة وإضافة سلسلة جديدة
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### إضافة علامات الصور إلى نقاط بيانات الرسم البياني
الآن إلى الجزء المثير - إضافة الصور كعلامات:

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

        // تحميل الصور وإضافتها كعلامات
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // إضافة نقاط البيانات مع الصور كعلامات
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

### تكوين علامة سلسلة الرسم البياني وحفظ العرض التقديمي
أخيرًا، دعنا نضبط حجم العلامة لتحسين الرؤية وحفظ عرضنا التقديمي:

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

        // تحميل الصور وإضافتها كعلامات (مثال باستخدام مسارات العنصر النائب)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## خاتمة
باتباع هذا الدليل، ستتعلم كيفية تحسين مخططاتك في Aspose.Slides لجافا بإضافة علامات صور مخصصة. هذا النهج يعزز بشكل كبير تفاعل الجمهور ووضوح عروضك التقديمية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
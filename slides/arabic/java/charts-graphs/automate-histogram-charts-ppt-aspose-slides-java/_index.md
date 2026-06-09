---
date: '2026-02-27'
description: تعلم كيفية إضافة مخططات هيستوغرام في PowerPoint باستخدام Aspose.Slides
  للـ Java، وتلقائيًا إنشاء المخططات لتحميل وتعديل العروض التقديمية بسرعة.
keywords:
- automate histogram charts PowerPoint
- Aspose.Slides for Java tutorial
- add histogram chart in PowerPoint
title: كيفية إضافة مخطط هيستوجرام في PowerPoint باستخدام Aspose.Slides
url: /ar/java/charts-graphs/automate-histogram-charts-ppt-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط هيستوجرام في PowerPoint باستخدام Aspose.Slides

## المقدمة
إن إنشاء عروض تقديمية جذابة بصريًا أمر حيوي في عالم اليوم القائم على البيانات، وتعد المخططات جزءًا أساسيًا من هذه العملية. **كيفية إضافة مخطط هيستوجرام** تلقائيًا يمكن أن يوفر لك ساعات من العمل اليدوي ويقضي على الأخطاء. في هذا الدرس ستتعلم كيفية تحميل ملف PowerPoint، تعديل الشرائح، إضافة مخطط هيستوجرام، ضبط المحور الأفقي، وأخيرًا حفظ ملف PowerPoint — كل ذلك باستخدام Aspose.Slides for Java.

### إجابات سريعة
- **ما المكتبة التي تسهل ذلك؟** Aspose.Slides for Java  
- **أي نوع من المخططات؟** مخطط هيستوجرام  
- **هل يمكنني تحميل ملف PPTX موجود؟** نعم – استخدم `Presentation` لفتح أي ملف  
- **كيف أضبط المحور؟** `setAggregationType(AxisAggregationType.Automatic)`  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتقييم؛ الترخيص الكامل مطلوب للإنتاج  

## ما هو مخطط الهيستوجرام؟
الهيستوجرام يُظهر توزيع البيانات الرقمية عن طريق تجميع القيم في صناديق. إنه مثالي لعرض التردد، نطاقات الأداء، أو أي انتشار إحصائي مباشرة داخل شريحة PowerPoint.

## لماذا نُؤتمت إنشاء الهيستوجرام؟
- **السرعة:** توليد العشرات من المخططات في ثوانٍ بدلاً من دقائق.  
- **الاتساق:** كل مخطط يتبع نفس التنسيق وإعدادات المحور.  
- **القابلية للتوسع:** مثالي لمعالجة دفعات من التقارير، لوحات المعلومات، أو العروض المتكررة.  

## المتطلبات المسبقة
- **Aspose.Slides for Java** – الإصدار 25.4 أو أحدث.  
- **JDK** 16 أو أعلى.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
- Maven أو Gradle لإدارة الاعتمادات.  

### المكتبات المطلوبة والإصدارات والاعتمادات
- **Aspose.Slides for Java**: الإصدار 25.4 أو أحدث.  
- **JDK**: 16+.  

### متطلبات إعداد البيئة
- بيئة تطوير متكاملة (IDE) – IntelliJ IDEA أو Eclipse.  
- Maven أو Gradle مثبتان إذا كنت تفضل التعامل الآلي مع الاعتمادات.  

### المتطلبات المعرفية
- برمجة Java أساسية.  
- الإلمام ببنية ملفات PowerPoint ومفاهيم المخططات.  

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

لمن يفضل التحميل المباشر، زر صفحة [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
1. **نسخة تجريبية مجانية** – احصل على ترخيص مؤقت لاستكشاف جميع الميزات.  
2. **ترخيص مؤقت** – قدِّم طلبًا على موقع Aspose للحصول على مفتاح قصير الأمد.  
3. **شراء** – احصل على ترخيص دائم من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

**التهيئة الأساسية:**

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
فيما يلي شرح خطوة بخطوة يغطي **تحميل عرض PowerPoint**، **تعديل شرائح PowerPoint**، **إضافة مخطط هيستوجرام**، **ضبط المحور الأفقي**، و**حفظ ملف PowerPoint**.

### تحميل وتعديل عرض PowerPoint
**كيفية تحميل ملف PowerPoint والوصول إلى شريحته الأولى:**

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
**كيفية إضافة مخطط هيستوجرام إلى الشريحة التي تم تحميلها:**

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

*شرح:* `addChart` ينشئ مخططًا جديدًا من النوع `ChartType.Histogram`. الأرقام تحدد موضع X‑Y وعرض‑ارتفاع المخطط على الشريحة.

### تكوين دفتر بيانات المخطط وإضافة سلسلة
**كيفية تعبئة الهيستوجرام بنقاط البيانات:**

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

*شرح:* `IChartDataWorkbook` يعمل كجدول Excel خلف المخطط. نقوم بمسح أي بيانات موجودة، ثم نضيف سلسلة جديدة ونملأها بالقيم الرقمية.

### ضبط المحور الأفقي وحفظ العرض
**كيفية ضبط نوع التجميع للمحور الأفقي وحفظ الملف:**

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

*شرح:* ضبط `AggregationType.Automatic` يسمح لـ Aspose بتجميع البيانات تلقائيًا في صناديق مناسبة، مما يجعل الهيستوجرام أسهل للقراءة. استدعاء `save` النهائي يكتب ملف PPTX إلى القرص.

## التطبيقات العملية
إليك بعض السيناريوهات الواقعية حيث يبرز **أتمتة إنشاء المخططات**:

1. **تقارير الأعمال** – توليد هيستوجرامات توزيع المبيعات للعرض ربع السنوي.  
2. **البحوث الأكاديمية** – تصور مجموعات البيانات التجريبية مباشرة في شرائح المحاضرات.  
3. **اجتماعات تحليل البيانات** – تحويل بيانات CSV الخام بسرعة إلى هيستوجرامات مصقولة لمراجعات أصحاب المصلحة.  

## المشكلات الشائعة والحلول
- **خطأ الترخيص المفقود:** تأكد من صحة مسار ملف `.lic` وأن نسخة الترخيص تتطابق مع مكتبة Aspose.Slides لديك.  
- **المخطط غير ظاهر:** تحقق من أن أبعاد الشريحة كافية؛ عدّل معلمات حجم `addChart` إذا لزم الأمر.  
- **البيانات تُستبدل:** دائمًا استدعِ `wb.clear(0)` قبل تعبئة بيانات جديدة لتجنب القيم المتبقية.

## الأسئلة المتكررة

**س: هل يمكنني إضافة عدة مخططات هيستوجرام إلى نفس العرض؟**  
ج: نعم. استدعِ `addChart` على أي شريحة بقدر ما تحتاج، كل واحدة بسلسلة بياناتها الخاصة.

**س: هل يدعم Aspose.Slides أنواع مخططات أخرى غير الهيستوجرام؟**  
ج: بالتأكيد. يدعم الخط، العمود، الدائرة، التبعثر، والعديد من الأنواع الأخرى.

**س: هل يمكن تنسيق الهيستوجرام (الألوان، الخطوط)؟**  
ج: نعم. بعد إنشاء المخطط يمكنك الوصول إلى `chart.getChartData().getSeries()` وتعديل خصائص التنسيق مثل لون التعبئة والخط.

**س: ماذا إذا احتجت إلى تحميل PPTX محمي بكلمة مرور؟**  
ج: استخدم المُنشئ `Presentation(String fileName, LoadOptions options)` وحدد كلمة المرور في `LoadOptions`.

**س: هل يعمل هذا مع ملفات .ppt القديمة؟**  
ج: Aspose.Slides يمكنه قراءة وكتابة كل من `.ppt` و`.pptx`. فقط غيّر امتداد الملف في طريقة `save`.

---

**آخر تحديث:** 2026-02-27  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
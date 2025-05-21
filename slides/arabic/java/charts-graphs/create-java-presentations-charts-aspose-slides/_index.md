---
"date": "2025-04-17"
"description": "تعلّم كيفية إنشاء وتكوين عروض تقديمية ديناميكية باستخدام الرسوم البيانية في جافا باستخدام Aspose.Slides. أتقن إضافة العروض التقديمية وتخصيصها وحفظها بفعالية."
"title": "إنشاء عروض تقديمية بلغة Java مع الرسوم البيانية باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء عرض تقديمي وتكوينه باستخدام مخطط باستخدام Aspose.Slides لـ Java

## مقدمة

يُعد إنشاء عروض تقديمية ديناميكية تعرض البيانات بفعالية أمرًا بالغ الأهمية في بيئة الأعمال سريعة التطور اليوم. سواء كنت تُعدّ تقريرًا ماليًا أو تستعرض مقاييس مشروع، فإن إضافة المخططات البيانية تُعزز تأثير عرضك التقديمي بشكل كبير. يُرشدك هذا البرنامج التعليمي خلال إنشاء وتكوين عرض تقديمي باستخدام مخطط عمودي ثلاثي الأبعاد باستخدام Aspose.Slides for Java، وهي مكتبة فعّالة مُصممة للتعامل مع العروض التقديمية برمجيًا.

**ما سوف تتعلمه:**
- كيفية إنشاء عرض تقديمي جديد
- إضافة المخططات وتكوينها في الشرائح
- تخصيص بيانات الرسم البياني ومظهره
- احفظ عرضك التقديمي بفعالية

هل أنت مستعد لإتقان إنشاء عروض تقديمية جذابة بصريًا باستخدام جافا؟ هيا بنا!

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أنك قمت بتغطية المتطلبات الأساسية التالية:

- **المكتبات والتبعيات**:يجب تثبيت Aspose.Slides لـ Java.
- **إعداد البيئة**:العمل في بيئة Java (يوصى باستخدام JDK 16 أو إصدار أحدث).
- **قاعدة المعرفة**:ستكون المعرفة بمفاهيم برمجة Java الأساسية مفيدة.

## إعداد Aspose.Slides لـ Java

### تثبيت

لدمج Aspose.Slides في مشروعك، اتبع الخطوات التالية:

**مافن**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**جرادل**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**التحميل المباشر**:بدلاً من ذلك، قم بتنزيل الإصدار الأحدث من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **نسخة تجريبية مجانية**:ابدأ بإصدار تجريبي مجاني لاستكشاف الميزات.
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت للاختبار الموسع.
- **شراء**:احصل على ترخيص كامل للاستخدام التجاري.

بمجرد التثبيت، قم بتهيئة المكتبة في بيئة Java الخاصة بك عن طريق إنشاء مثيل لها `Presentation` يُمهّد هذا الطريق لإضافة المخططات والعناصر الأخرى إلى العرض التقديمي الخاص بك.

## دليل التنفيذ

### إنشاء عرض تقديمي وتكوينه باستخدام مخطط

#### ملخص
إنشاء عرض تقديمي من الصفر سهل للغاية مع Aspose.Slides. في هذا القسم، سنضيف مخططًا عموديًا ثلاثي الأبعاد إلى الشريحة الأولى من عرضنا التقديمي.

**خطوات:**

1. **تهيئة كائن العرض التقديمي**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // تهيئة كائن عرض تقديمي جديد
           Presentation presentation = new Presentation();
           
           // الوصول إلى الشريحة الأولى في العرض التقديمي
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // أضف مخططًا عموديًا مكدسًا ثلاثي الأبعاد إلى الشريحة في الموضع (0،0)
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

2. **شرح المعلمات**:
   - `ChartType.StackedColumn3D`:يحدد نوع الرسم البياني.
   - الموقع والحجم `(0, 0, 500, 500)`:يحدد مكان ظهور الرسم البياني على الشريحة.

### تكوين بيانات الرسم البياني

#### ملخص
لجعل مخططك ذا معنى، قم بتكوين سلاسل البيانات وفئاتها. يوضح هذا القسم كيفية إضافة نقاط بيانات محددة إلى مخططك.

**خطوات:**

1. **مصنف بيانات مخطط الوصول**

   ```java
   public static void configureChartData(IChart chart) {
       // تعيين فهرس ورقة العمل التي تحتوي على بيانات الرسم البياني
       int defaultWorksheetIndex = 0;
       
       // الوصول إلى مصنف بيانات الرسم البياني
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // أضف سلسلتين مع الأسماء
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // أضف ثلاث فئات
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### تعيين خصائص Rotation3D للرسم البياني

#### ملخص
حسّن مظهر مخططك البصري باستخدام خصائص التدوير ثلاثي الأبعاد. يتيح لك هذا التخصيص تعديل المنظور والعمق.

**خطوات:**

1. **تكوين التدويرات ثلاثية الأبعاد**

   ```java
   public static void setRotation3D(IChart chart) {
       // تمكين محاور الزاوية القائمة وتكوين الدورات في اتجاهي X وY ونسبة العمق
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **شرح المعلمات**:
   - `setRightAngleAxes(true)`:يضمن أن المحاور عمودية.
   - قيم الدوران: ضبط زاوية وعمق العرض ثلاثي الأبعاد.

### ملء بيانات السلسلة في الرسم البياني

#### ملخص
يُعدّ ملء مخططك بنقاط البيانات أمرًا بالغ الأهمية للتحليل. هنا، سنضيف قيمًا محددة إلى سلسلة داخل مخططنا.

**خطوات:**

1. **إضافة نقاط البيانات**

   ```java
   public static void populateSeriesData(IChart chart) {
       // الوصول إلى سلسلة المخططات الثانية
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // إضافة نقاط بيانات لسلسلة الأشرطة ذات القيم المحددة
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

### ضبط تداخل السلسلة في الرسم البياني

#### ملخص
يُمكن أن يُحسّن ضبط مظهر مخططك البياني سهولة قراءته. يتناول هذا القسم كيفية ضبط خاصية التداخل لتحسين عرض البيانات.

**خطوات:**

1. **مجموعة تداخل السلسلة**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // احصل على السلسلة الثانية من الرسم البياني واضبط تداخلها على 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### حفظ العرض التقديمي

#### ملخص
بعد إعداد عرضك التقديمي، احفظه على القرص بالتنسيق المطلوب. تضمن هذه الخطوة حفظ جميع التغييرات.

**خطوات:**

1. **حفظ العرض التقديمي**

   ```java
   public static void savePresentation(Presentation presentation) {
       // حفظ العرض التقديمي المعدل في ملف
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## خاتمة

لقد تعلمتَ الآن كيفية إنشاء وتكوين عروض تقديمية مع مخططات بيانية باستخدام Aspose.Slides لجافا. غطّى هذا الدليل تهيئة عرض تقديمي، وإضافة مخطط عمودي ثلاثي الأبعاد، وتكوين سلاسل البيانات وفئاتها، وضبط خصائص التدوير، وملء بيانات السلاسل، وضبط تداخل السلاسل، وحفظ العرض التقديمي النهائي.

للحصول على ميزات أكثر تقدمًا وخيارات التخصيص، راجع [توثيق Aspose.Slides لـ Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
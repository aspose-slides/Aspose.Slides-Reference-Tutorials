---
"date": "2025-04-17"
"description": "تعرّف على كيفية إنشاء وتخصيص مخططات الأسهم الديناميكية في PowerPoint باستخدام Aspose.Slides لـ Java. يغطي هذا الدليل تهيئة العروض التقديمية، وإضافة سلاسل البيانات، وتنسيق المخططات، وحفظ الملفات."
"title": "إنشاء مخططات أسهم ديناميكية في PowerPoint باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات أسهم ديناميكية في PowerPoint باستخدام Aspose.Slides لـ Java

## مقدمة

حسّن عروض PowerPoint التقديمية بإضافة مخططات أسهم ديناميكية. سواءً كنت محللًا ماليًا، أو خبيرًا في مجال الأعمال، أو مُعلّمًا وترغب في تصوّر اتجاهات البيانات بفعالية، يُرشدك هذا الدليل التعليمي خلال إنشاء مخططات الأسهم وتخصيصها باستخدام Aspose.Slides لجافا. بنهاية هذا الدليل، ستتمكن من تحميل ملفات PowerPoint الحالية، وإضافة مخططات أسهم مُفصّلة مع سلاسل وفئات مُخصصة، وتنسيقها بشكل جميل، وحفظ عرضك التقديمي المُحسّن.

**ما سوف تتعلمه:**
- تهيئة عرض تقديمي في Java باستخدام Aspose.Slides
- إضافة وتخصيص مخططات الأسهم
- مسح سلسلة البيانات والفئات
- إدراج نقاط بيانات جديدة للتحليل الشامل
- تنسيق خطوط وأشرطة الرسم البياني بشكل فعال
- حفظ العرض التقديمي المحدث

هل أنت مستعد لإنشاء عروض تقديمية جذابة بصريًا؟ هيا بنا!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- **مجموعة تطوير جافا (JDK)**:تأكد من تثبيت JDK على نظامك.
- **بيئة تطوير متكاملة**:استخدم أي IDE مثل IntelliJ IDEA أو Eclipse لكتابة وتشغيل كود Java.
- **Aspose.Slides لمكتبة Java**يتطلب هذا البرنامج التعليمي الإصدار 25.4 من Aspose.Slides لـ Java.

### إعداد Aspose.Slides لـ Java

#### مافن
لدمج Aspose.Slides في مشروعك باستخدام Maven، أضف التبعية التالية إلى مشروعك `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### جرادل
بالنسبة لمستخدمي Gradle، قم بتضمين هذا في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### التحميل المباشر
بدلاً من ذلك، قم بتنزيل أحدث ملف JAR من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

**الحصول على الترخيص**يمكنك البدء بفترة تجريبية مجانية أو طلب ترخيص مؤقت. للاستخدام الممتد، يُنصح بشراء ترخيص كامل.

## دليل التنفيذ

دعونا نقوم بتقسيم كل ميزة خطوة بخطوة.

### تهيئة العرض التقديمي
#### ملخص
ابدأ بتحميل ملف PowerPoint الحالي لتحضيره للتعديلات.

#### دليل خطوة بخطوة
1. **استيراد المكتبة**:
   
   ```java
   import com.aspose.slides.Presentation;
   ```

2. **تحميل ملف العرض التقديمي**:
   
   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // جاهز لإجراء العمليات على 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة مخطط الأسهم إلى الشريحة
#### ملخص
تتضمن هذه الخطوة إضافة مخطط الأسهم إلى الشريحة الأولى من العرض التقديمي الخاص بك.

3. **أضف الرسم البياني**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### مسح سلسلة البيانات والفئات الموجودة في الرسم البياني
#### ملخص
قم بإزالة أي سلسلة بيانات أو فئات موجودة مسبقًا من الرسم البياني للبدء من جديد.

4. **مسح البيانات**:
   
   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة فئات إلى بيانات الرسم البياني
#### ملخص
أضف فئات مخصصة لتقسيم البيانات وفهمها بشكل أفضل.

5. **إدراج الفئات**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // إضافة الفئات
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة سلسلة بيانات إلى الرسم البياني
#### ملخص
دمج سلاسل البيانات المختلفة مثل الافتتاح، والارتفاع، والانخفاض، والإغلاق للحصول على تحليل شامل.

6. **إضافة سلسلة بيانات**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // أضف سلسلة لـ "الافتتاح"، و"الارتفاع"، و"الانخفاض"، و"الإغلاق"
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة نقاط البيانات إلى السلسلة
#### ملخص
قم بملء كل سلسلة بنقاط بيانات محددة للحصول على تمثيل دقيق.

7. **إدراج نقاط البيانات**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // إضافة نقاط البيانات إلى سلسلة "مفتوحة"
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // إضافة نقاط البيانات إلى السلسلة "العالية"
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // إضافة نقاط البيانات إلى السلسلة "المنخفضة"
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // إضافة نقاط البيانات إلى سلسلة "إغلاق"
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### تنسيق الخطوط العالية والمنخفضة والأشرطة العلوية/السفلية
#### ملخص
قم بتخصيص مظهر الخطوط العالية والمنخفضة وأشرطة الأعلى/الأسفل لتحسين التصور.

8. **تنسيق الخطوط العالية والمنخفضة**:
   
   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // تنسيق الخطوط المرتفعة والمنخفضة لسلسلة "إغلاق"
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

9. **عرض أشرطة لأعلى/لأسفل**:
   
   ```java
   // عرض أشرطة الصعود/الهبوط لمجموعة سلسلة مخطط الأسهم
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### تخصيص تسميات البيانات على الخطوط العالية والمنخفضة
#### ملخص
قم بإضافة وتنسيق تسميات البيانات لعرض القيم على الخطوط العليا والمنخفضة.

10. **إظهار القيم على أشرطة الصعود/الهبوط**:
    
    ```java
    // إظهار القيم على أشرطة الصعود/الهبوط لكل سلسلة في مجموعة الرسم البياني
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### إعداد لون تعبئة الأشرطة السفلية
#### ملخص
قم بتعيين لون تعبئة مخصص لأشرطة الأعلى/الأسفل لتعزيز التمييز البصري.

11. **تغيير ألوان الشريط العلوي/السفلي**:
    
    ```java
    // تغيير ألوان الشريط العلوي/السفلي لكل سلسلة في مجموعة الرسم البياني
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // سلسلة "مفتوحة"
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // أشرطة علوية باللون السماوي
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // سلسلة "هاي"
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // قضبان سفلية باللون الأخضر البحري الداكن
        }
    }
    ```

### حفظ ملف PowerPoint
#### ملخص
احفظ التغييرات في ملف PowerPoint جديد.

12. **حفظ العرض التقديمي**:
    
    ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## خاتمة

تهانينا! لقد نجحت في إنشاء وتخصيص مخططات أسهم ديناميكية في PowerPoint باستخدام Aspose.Slides لجافا. تُحسّن هذه العملية عروضك التقديمية بتصورات بيانات جذابة بصريًا، مما يتيح لك توصيل رؤى مالية فعّالة. إذا كنت مهتمًا بتخصيص أو استكشاف أنواع أخرى من المخططات، ففكّر في التعمق في الدليل الشامل. [توثيق Aspose.Slides](https://docs.aspose.com/slides/java/).

## قراءات ومراجع إضافية
- توثيق Aspose.Slides لـ Java: استكشف الأدلة التفصيلية حول استخدام الميزات المختلفة لـ Aspose.Slides.
- نظرة عامة على أدوات التخطيط البياني في PowerPoint: تعرف على أدوات التخطيط البياني المختلفة المتوفرة في Microsoft PowerPoint.
- أفضل ممارسات تصور البيانات: تعلم كيفية عرض البيانات بشكل فعال من خلال الوسائل المرئية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
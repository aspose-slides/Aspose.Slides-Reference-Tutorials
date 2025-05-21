---
"date": "2025-04-17"
"description": "تعلم كيفية إنشاء عروض تقديمية احترافية باستخدام Aspose.Slides لجافا. يغطي هذا الدليل إعداد بيئتك، وإضافة مخططات أعمدة مكدسة، وتخصيصها لزيادة الوضوح."
"title": "إتقان مخططات الأعمدة المكدسة في جافا باستخدام Aspose.Slides - دليل شامل"
"url": "/ar/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان مخططات الأعمدة المكدسة في Java باستخدام Aspose.Slides: دليل شامل

## مقدمة

ارتقِ بعروضك التقديمية بدمج تصورات بيانات ثاقبة مع قوة Aspose.Slides لجافا. إنشاء شرائح احترافية بمخططات أعمدة مكدسة أمر سهل، سواء كنت تُعدّ تقارير أعمال أو تُعرض إحصاءات مشاريع.

في هذا البرنامج التعليمي، سنستكشف كيفية استخدام Aspose.Slides لجافا لإنشاء عروض تقديمية ديناميكية وإضافة مخططات عمودية مكدسة جذابة بصريًا. بنهاية هذا الدليل، ستكون قد اكتسبت المهارات اللازمة لما يلي:
- قم بإعداد بيئتك لاستخدام Aspose.Slides
- إنشاء عرض تقديمي من الصفر
- إضافة وتخصيص مخططات الأعمدة المكدسة بالنسب المئوية
- تنسيق محاور الرسم البياني وعلامات البيانات لتحقيق الوضوح

دعنا نتعمق في إنشاء العروض التقديمية التي تجذب جمهورك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- **مجموعة تطوير Java (JDK):** الإصدار 8 أو أعلى.
- **بيئة التطوير المتكاملة:** أي بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.
- **Maven/Gradle:** لإدارة التبعيات (اختياري ولكن موصى به).
- **المعرفة الأساسية بلغة جافا:** المعرفة بمفاهيم برمجة جافا.

## إعداد Aspose.Slides لـ Java
للبدء، عليك تضمين مكتبة Aspose.Slides في مشروعك. إليك الطريقة:

**مافن:**
أضف هذه التبعية إلى `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**جرادل:**
قم بتضمين هذا في `build.gradle` ملف:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**التحميل المباشر:**
بدلاً من ذلك، قم بتنزيل أحدث ملف JAR من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
يمكنك البدء بفترة تجريبية مجانية لاستكشاف ميزات Aspose.Slides. لإزالة قيود التقييم، يمكنك الحصول على ترخيص مؤقت أو شراء ترخيص.
- **نسخة تجريبية مجانية:** يمكنك الوصول إلى ميزات محدودة دون تكاليف فورية.
- **رخصة مؤقتة:** طلب عبر [موقع Aspose](https://purchase.aspose.com/temporary-license/).
- **شراء:** قم بزيارة صفحة الشراء للحصول على إمكانية الوصول الكامل.

### التهيئة الأساسية
فيما يلي كيفية تهيئة Aspose.Slides في تطبيق Java الخاص بك:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // إنشاء مثيل لفئة العرض التقديمي
        Presentation presentation = new Presentation();
        
        // تنفيذ العمليات على كائن العرض التقديمي
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## دليل التنفيذ

### إنشاء عرض تقديمي وإضافة شريحة
**ملخص:**
ابدأ بإنشاء عرض تقديمي بسيط بشريحة أولية. هذا هو أساسك لمزيد من التحسينات.

#### الخطوة 1: تهيئة كائن العرض التقديمي
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // إنشاء مثيل عرض تقديمي جديد
        Presentation presentation = new Presentation();
        
        // مرجع للشريحة الأولى (تم إنشاؤها تلقائيًا)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### الخطوة 2: حفظ العرض التقديمي
```java
// حفظ العرض التقديمي في ملف
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### إضافة مخطط عمودي مكدس بالنسب المئوية إلى شريحة
**ملخص:**
قم بتعزيز الشريحة الخاصة بك عن طريق إضافة مخطط عمودي متراكم بالنسب المئوية، مما يسمح بمقارنة البيانات بسهولة.

#### الخطوة 1: تهيئة الشريحة والوصول إليها
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // انتقل إلى إضافة الرسم البياني في الخطوة التالية
    }
}
```

#### الخطوة 2: إضافة الرسم البياني إلى الشريحة
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### تخصيص تنسيق أرقام محور الرسم البياني
**ملخص:**
قم بتخصيص تنسيق الأرقام للمحور الرأسي للرسم البياني الخاص بك لتحسين إمكانية القراءة.

#### الخطوة 1: إضافة الرسم البياني والوصول إليه
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

#### الخطوة 2: تعيين تنسيق رقم مخصص
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### إضافة سلسلة ونقاط بيانات إلى الرسم البياني
**ملخص:**
قم بملء الرسم البياني الخاص بك بسلسلة من البيانات، مما يجعله مفيدًا وجذابًا بصريًا.

#### الخطوة 1: تهيئة العرض التقديمي والمخطط
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

#### الخطوة 2: إضافة سلسلة البيانات
```java
// مسح السلسلة الموجودة وإضافة سلسلة جديدة
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// أضف المزيد من نقاط البيانات حسب الحاجة
```

### تنسيق لون تعبئة السلسلة
**ملخص:**
قم بتعزيز جماليات الرسم البياني الخاص بك عن طريق تنسيق لون التعبئة لكل سلسلة.

#### الخطوة 1: تهيئة المخطط والوصول إليه
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

#### الخطوة 2: تعيين ألوان التعبئة
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// كرر ذلك لسلسلة أخرى بألوان مختلفة
```

### تنسيق تسميات البيانات
**ملخص:**
اجعل تسميات البيانات الخاصة بك أكثر قابلية للقراءة عن طريق تخصيص تنسيقها.

#### الخطوة 1: الوصول إلى سلسلة المخططات ونقاط البيانات
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

#### الخطوة 2: تخصيص تسميات البيانات
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

## خاتمة
باتباع هذا الدليل، ستتعلم كيفية إعداد Aspose.Slides لجافا وإنشاء عروض تقديمية ديناميكية باستخدام مخططات عمودية متراكمة النسب المئوية. يمكنك تخصيص مخططاتك بشكل أكبر عن طريق ضبط الألوان والتسميات لتناسب احتياجاتك.

برمجة سعيدة!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
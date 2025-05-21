---
"date": "2025-04-17"
"description": "تعرّف على كيفية استخدام Aspose.Slides لجافا لإنشاء مخططات دائرية ديناميكية في PowerPoint. حسّن عروضك التقديمية بخطوات سهلة وأمثلة برمجية."
"title": "إنشاء مخططات دائرية ديناميكية في PowerPoint باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات دائرية ديناميكية في PowerPoint باستخدام Aspose.Slides لـ Java

## مقدمة
غالبًا ما يتطلب إنشاء عروض تقديمية جذابة أكثر من مجرد نصوص وصور؛ إذ تُحسّن المخططات البيانية سرد القصص بشكل ملحوظ من خلال عرض البيانات بشكل فعّال. ومع ذلك، يواجه العديد من المطورين صعوبة في دمج ميزات المخططات الديناميكية في ملفات PowerPoint برمجيًا. يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.Slides لـ Java لإنشاء مخطط دائري في PowerPoint، وهي أداة فعّالة تجمع بين المرونة وسهولة الاستخدام.

**ما سوف تتعلمه:**
- كيفية تهيئة عرض تقديمي باستخدام Aspose.Slides لـ Java
- دليل خطوة بخطوة لإضافة مخطط دائري إلى شرائحك
- تكوين نقاط البيانات وتخصيص خصائص الملصق
- حفظ العرض التقديمي المعدّل بدقة عالية

دعونا نستكشف كيفية الاستفادة من هذه الميزات لتحسين عروضك التقديمية. قبل البدء، تأكد من إلمامك بمفاهيم برمجة جافا الأساسية.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي بشكل فعال، تأكد من أن لديك:
- المعرفة الأساسية ببرمجة جافا.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
- تم تثبيت Maven أو Gradle لإدارة التبعيات.
- ترخيص Aspose.Slides صالح لجافا. يمكنك الحصول على نسخة تجريبية مجانية لاختبار ميزاته.

## إعداد Aspose.Slides لـ Java
ابدأ بدمج Aspose.Slides في مشروعك. اختر بين Maven وGradle، حسب تفضيلك:

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

إذا كنت تفضل التنزيل مباشرة، قم بزيارة [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/) صفحة.

### الحصول على الترخيص
يمكنك البدء بفترة تجريبية مجانية لاستكشاف ميزات Aspose.Slides. للاستخدام الممتد، اشترِ ترخيصًا أو اطلب ترخيصًا مؤقتًا من [موقع Aspose](https://purchase.aspose.com/temporary-license/). اتبع الإرشادات المقدمة لإعداد بيئتك وتهيئة Aspose.Slides في تطبيقك.

## دليل التنفيذ
دعونا نشرح الخطوات اللازمة لإنشاء مخطط دائري في PowerPoint باستخدام Aspose.Slides لجافا. كل قسم مخصص لخاصية محددة، مما يضمن الوضوح والتركيز.

### تهيئة العرض التقديمي
ابدأ بتحميل أو إنشاء ملف باوربوينت جديد. هذه الخطوة تُهيئ بيئة العرض التقديمي.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// التحقق من نجاح التحميل عن طريق حفظ العرض التقديمي الأولي
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### إضافة مخطط دائري
أضف مخططًا دائريًا إلى الشريحة الخاصة بك، وقم بتخصيص أبعاده ومظهره.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// تكوين خصائص السلسلة
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### تكوين نقاط البيانات والعلامات
قم بتخصيص مظهر كل نقطة بيانات وتكوين العلامات لتحسين قابلية القراءة.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // تنسيق نقطة البيانات
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // تخصيص خصائص العلامة للسلسلة الأخيرة في كل فئة
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### حفظ العرض التقديمي
بعد تكوين الرسم البياني الخاص بك، احفظ العرض التقديمي للاحتفاظ بالتغييرات التي أجريتها.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## التطبيقات العملية
يمكن استخدام مخططات الكعكة الدائرية في سيناريوهات مختلفة:
- **التقارير المالية:** تصور تخصيصات الميزانية أو المقاييس المالية.
- **تحليل السوق:** إظهار توزيع حصة السوق بين المنافسين.
- **نتائج الاستطلاع:** عرض البيانات التصنيفية من استجابات الاستطلاع بشكل فعال.

يتيح التكامل مع الأنظمة الأخرى، مثل قواعد البيانات وتطبيقات الويب، إنشاء مخططات ديناميكية استنادًا إلى البيانات في الوقت الفعلي.

## اعتبارات الأداء
للحصول على الأداء الأمثل:
- إدارة استخدام الذاكرة عن طريق التخلص من الموارد على الفور.
- قم بتحديد عدد المخططات أو الشرائح إذا لم يكن ذلك ضروريًا للحفاظ على قوة المعالجة.
- استخدم هياكل بيانات فعالة للتعامل مع مجموعات البيانات الكبيرة.

إن الالتزام بأفضل الممارسات يضمن تشغيل تطبيقك بسلاسة، خاصة عند التعامل مع العروض التقديمية المعقدة.

## خاتمة
إنشاء مخططات دائرية ديناميكية في PowerPoint باستخدام Aspose.Slides لجافا عملية سهلة بمجرد فهم الخطوات الأساسية. مع هذا الدليل، أنت الآن جاهز لتحسين عروضك التقديمية من خلال دمج مخططات جذابة بصريًا تُعبّر بفعالية عن رؤى البيانات.

لاستكشاف وظائف Aspose.Slides بشكل أكبر والتعرف على إمكانياتها بشكل أعمق، فكر في تجربة أنواع مختلفة من المخططات أو الميزات المتقدمة مثل الرسوم المتحركة والانتقالات.

## قسم الأسئلة الشائعة
**س: هل يمكنني استخدام Aspose.Slides لـ Java في التطبيقات التجارية؟**
ج: نعم، ولكن ستحتاج إلى الحصول على ترخيص. يمكنك البدء بفترة تجريبية مجانية لتقييم ميزاته.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
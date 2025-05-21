---
"date": "2025-04-17"
"description": "تعلّم كيفية إنشاء وتخصيص وحفظ المخططات البيانية مع تسميات النسب المئوية في عروض جافا التقديمية باستخدام Aspose.Slides. طوّر مهاراتك في العروض التقديمية اليوم!"
"title": "إنشاء المخططات وتخصيصها في العروض التقديمية بلغة Java باستخدام Aspose.Slides"
"url": "/ar/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء المخططات وتخصيصها في العروض التقديمية بلغة Java باستخدام Aspose.Slides

## مقدمة
غالبًا ما يتطلب إنشاء عروض تقديمية جذابة أكثر من مجرد نص؛ بل يتطلب مخططات ديناميكية تعرض المعلومات بفعالية. إذا كنت ترغب في تحسين عروضك التقديمية المستندة إلى جافا بميزات مخططات متطورة باستخدام Aspose.Slides، فهذا البرنامج التعليمي مناسب لك. سنرشدك خلال إنشاء عرض تقديمي، وإضافة المخططات وتكوينها، وحساب الإجماليات، وعرض تسميات النسب المئوية، وحفظ عملك - كل ذلك في بضع خطوات سهلة.

**ما سوف تتعلمه:**
- كيفية إنشاء العروض التقديمية وتخصيصها باستخدام الرسوم البيانية باستخدام Aspose.Slides لـ Java
- حساب إجمالي الفئات في المخططات البيانية
- عرض البيانات كعلامات نسبية على الرسوم البيانية
- حفظ العروض التقديمية باستخدام ميزات الرسم البياني المحسّنة

دعونا نلقي نظرة على المتطلبات الأساسية التي تحتاجها قبل البدء.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:

- **مجموعة تطوير جافا (JDK)**:الإصدار 8 أو أعلى.
- **بيئة تطوير متكاملة**:مثل IntelliJ IDEA، أو Eclipse، أو أي IDE يدعم Java.
- **Aspose.Slides لمكتبة Java**:يعد هذا أمرًا بالغ الأهمية للتعامل مع ميزات العرض التقديمي.

### المكتبات والإصدارات المطلوبة
ستحتاج إلى Aspose.Slides لجافا. إليك كيفية تضمينه في مشروعك:

**مافن:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**جرادل:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، يمكنك تنزيل الإصدار الأحدث مباشرةً من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### إعداد البيئة
تأكد من تكوين بيئة التطوير لديك لاستخدام JDK 8 أو إصدار أحدث ومن إعداد IDE الخاص بك لإدارة التبعيات باستخدام Maven أو Gradle.

**الحصول على الترخيص:**
- **نسخة تجريبية مجانية**:الوصول إلى الميزات الأساسية لأغراض الاختبار.
- **رخصة مؤقتة**:اختبار الميزات المتقدمة دون قيود التقييم.
- **شراء**:للاستخدام التجاري طويل الأمد، فكر في شراء ترخيص.

## إعداد Aspose.Slides لـ Java
ابدأ بإعداد مكتبة Aspose.Slides في مشروع جافا الخاص بك. إليك كيفية تهيئة المكتبة وتكوينها:

1. أضف التبعية عبر Maven أو Gradle كما هو موضح أعلاه.
2. استيراد حزم Aspose.Slides الضرورية:
   ```java
   import com.aspose.slides.*;
   ```

3. تهيئة ملف جديد `Presentation` مثال:
   ```java
   Presentation presentation = new Presentation();
   ```

سيسمح لك هذا الإعداد ببدء إنشاء العروض التقديمية برمجيًا.

## دليل التنفيذ

### إنشاء المخططات وتخصيصها في العرض التقديمي الخاص بك

#### ملخص
يتضمن إنشاء مخطط تهيئة العرض التقديمي الخاص بك، والوصول إلى الشرائح، وإضافة مخطط بسمات محددة مثل النوع والموضع والحجم.

**خطوات:**
1. **إنشاء مثيل للعرض التقديمي**:ابدأ بإنشاء مثيل لـ `Presentation` فصل.
2. **شريحة الوصول**:استرجاع الشريحة الأولى باستخدام `get_Item(0)`.
3. **إضافة الرسم البياني**: يستخدم `addChart()` لإضافة مخطط عمودي مكدس عند إحداثيات محددة بأبعاد محددة.

```java
// الميزة: إنشاء عرض تقديمي باستخدام الرسم البياني
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### حساب الإجماليات للفئات

#### ملخص
تتضمن عملية حساب إجماليات الفئات تكرار كل سلسلة في الرسم البياني لتلخيص القيم لكل فئة.

**خطوات:**
1. **تهيئة المصفوفة**:إنشاء مصفوفة لتخزين القيم الإجمالية.
2. **التكرار عبر الفئات والسلاسل**:استخدم الحلقات المتداخلة لتجميع الإجماليات لكل فئة من جميع السلاسل.

```java
// الميزة: حساب إجمالي الفئات في الرسم البياني
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### عرض البيانات كنسب مئوية على الرسم البياني

#### ملخص
ترتكز هذه الميزة على تكوين تسميات البيانات لعرض القيم كنسب مئوية، مما يوفر الوضوح في التصور.

**خطوات:**
1. **تكوين تسميات السلسلة**:إعداد خصائص التسمية مثل حجم الخط ورؤية مفاتيح الأسطورة.
2. **حساب النسب المئوية**:احسب النسبة المئوية لكل نقطة بيانات بناءً على قيمة الفئة الإجمالية.
3. **تعيين نص التسمية**:تنسيق العلامات لإظهار النسب المئوية بنقطتين عشريتين.

```java
// الميزة: عرض البيانات كعلامات نسبية على الرسم البياني
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### حفظ العرض التقديمي مع الرسم البياني

#### ملخص
وأخيرًا، احفظ العرض التقديمي الخاص بك في المسار المحدد بتنسيق PPTX.

**خطوات:**
1. **طريقة الحفظ**:استخدم `save()` الطريقة على `Presentation` مثال.
2. **التخلص من الموارد**:تأكد من تحرير الموارد بعد الحفظ.

```java
// الميزة: حفظ العرض التقديمي مع الرسم البياني
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## التطبيقات العملية

1. **التقارير المالية**:استخدم المخططات البيانية لعرض نسب نمو الإيرادات عبر الأقسام.
2. **تحليل بيانات المبيعات**:يمكنك تصور بيانات المبيعات حسب المنطقة باستخدام تسميات النسب المئوية للحصول على رؤى أكثر وضوحًا.
3. **العروض التعليمية**:تعزيز العروض التقديمية الأكاديمية باستخدام الإحصائيات المرئية.
4. **الحملات التسويقية**:عرض مقاييس أداء الحملة على هيئة صور مرئية جذابة.
5. **اجتماعات استراتيجية الأعمال**:استخدم المخططات البيانية لنقل البيانات المعقدة في مناقشات التخطيط الاستراتيجي.

## اعتبارات الأداء
- **إدارة الذاكرة**:التخلص من `Presentation` الأشياء على الفور لتحرير الموارد.
- **تحسين تحميل الرسم البياني**:قم بتحميل عناصر الرسم البياني الأساسية فقط إلى الذاكرة إذا كان ذلك ممكنًا.
- **معالجة الدفعات**:عند معالجة عروض تقديمية متعددة، فكر في التعامل معها على دفعات لإدارة استهلاك الموارد بشكل فعال.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-17"
"description": "تعرّف على كيفية إنشاء وتخصيص المخططات الخطية بلغة جافا باستخدام Aspose.Slides. يغطي هذا الدليل عناصر المخططات، والعلامات، والتسميات، والأنماط للعروض التقديمية الاحترافية."
"title": "تخصيص مخطط الخط الرئيسي في Java باستخدام Aspose.Slides"
"url": "/ar/java/charts-graphs/master-line-chart-customization-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان تخصيص مخططات الخطوط في Java باستخدام Aspose.Slides

## مقدمة

قد يكون إنشاء عروض تقديمية احترافية تجمع بين وضوح البيانات والجاذبية البصرية أمرًا صعبًا، خاصةً عند تخصيص المخططات الخطية في تطبيقات جافا. سيساعدك هذا الدليل على إتقان استخدام "Aspose.Slides for Java" لإنشاء المخططات الخطية وتخصيصها بسهولة. ستتعلم كيفية تحسين عناصر المخططات، مثل العناوين، والرموز التوضيحية، والفؤوس، والعلامات، والتسميات، والألوان، والأنماط، وغيرها.

**ما سوف تتعلمه:**
- إنشاء مخطط خطي باستخدام Aspose.Slides لـ Java
- تخصيص عناصر الرسم البياني مثل العنوان والأسطورة والمحاور
- ضبط علامات السلسلة، والعلامات، وألوان الخطوط، والأنماط
- احفظ عرضك التقديمي مع جميع التعديلات

قبل الغوص في الأمر، دعنا نتأكد من أن كل شيء جاهز للبدء.

## المتطلبات الأساسية

للمتابعة، تأكد من أن لديك:

- **المكتبات المطلوبة:** تحتاج إلى Aspose.Slides لجافا. نوصي باستخدام الإصدار 25.4.
- **إعداد البيئة:** يجب تكوين بيئة Java الخاصة بك بشكل صحيح باستخدام JDK16 أو إصدار أحدث.
- **المتطلبات المعرفية:** ستكون المعرفة ببرمجة Java ومفاهيم التخطيط الأساسية مفيدة.

## إعداد Aspose.Slides لـ Java

ابدأ بدمج Aspose.Slides في مشروعك. إليك كيفية القيام بذلك باستخدام أدوات بناء مختلفة:

### مافن
أضف هذه التبعية إلى `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### جرادل
قم بتضمينه في `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، قم بتنزيل الإصدار الأحدث من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- **نسخة تجريبية مجانية:** ابدأ بالتجربة المجانية لاستكشاف الميزات.
- **رخصة مؤقتة:** احصل على ترخيص مؤقت للوصول الكامل دون قيود.
- **شراء:** فكر في شراء ترخيص للاستخدام المستمر.

قم بتهيئة بيئتك عن طريق إعداد Aspose.Slides، مع التأكد من تكوين المكتبة بشكل صحيح في مشروعك.

## دليل التنفيذ

دعنا نقسم عملية إنشاء المخططات الخطية وتخصيصها باستخدام Aspose.Slides لـ Java إلى ميزات مميزة.

### إنشاء مخطط خطي وتكوينه

#### ملخص
ابدأ بإضافة شريحة جديدة إلى العرض التقديمي الخاص بك وإدراج مخطط خطي مع علامات.

```java
import com.aspose.slides.*;

// تهيئة فئة العرض التقديمي
class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            // الوصول إلى الشريحة الأولى
            ISlide slide = pres.getSlides().get_Item(0);
            
            // إضافة مخطط خطي مع علامات
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يُشغّل هذا الكود عرضًا تقديميًا ويضيف مخططًا خطيًا إلى الشريحة الأولى. تُحدد المعلمات نوع المخطط وموقعه على الشريحة.

### إخفاء عنوان الرسم البياني

#### ملخص
في بعض الأحيان، قد يؤدي إزالة عنوان الرسم البياني إلى الحصول على مظهر أكثر نظافة.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // إخفاء عنوان الرسم البياني
            chart.getTitleFormat().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يخفي هذا المقطع عنوان الرسم البياني عن طريق تعيين رؤيته إلى "خطأ".

### إخفاء محاور القيمة والفئة

#### ملخص
للحصول على تصميم بسيط، قد ترغب في إخفاء كلا المحورين.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // إخفاء المحاور الرأسية والأفقية
            chart.getAxes().getVerticalAxis().setVisible(false);
            chart.getAxes().getHorizontalAxis().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يقوم هذا الكود بتعيين رؤية كلا المحورين إلى false.

### إخفاء أسطورة الرسم البياني

#### ملخص
قم بإزالة الأسطورة للتركيز على البيانات نفسها.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // إخفاء الأسطورة
            chart.setHasLegend(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يخفي هذا المقطع أسطورة الرسم البياني.

### إخفاء خطوط الشبكة الرئيسية على المحور الأفقي

#### ملخص
قم بإزالة خطوط الشبكة الرئيسية للحصول على مظهر أنظف.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // تعيين خطوط الشبكة الرئيسية إلى "NoFill"
            chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat()
                .getLine().getFillFormat().setFillType(FillType.NoFill);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يقوم هذا الكود بإخفاء خطوط الشبكة الرئيسية عن طريق تعيين نوع التعبئة الخاص بها إلى `NoFill`.

### إزالة جميع السلاسل من الرسم البياني

#### ملخص
مسح كافة سلاسل البيانات لبداية جديدة.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // إزالة جميع السلاسل من الرسم البياني
            for (int i = chart.getChartData().getSeries().size() - 1; i >= 0; i--) {
                chart.getChartData().getSeries().removeAt(i);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يؤدي هذا المقطع إلى إزالة جميع السلاسل الموجودة من الرسم البياني.

### تكوين علامات السلسلة والعلامات

#### ملخص
قم بتخصيص العلامات وعلامات البيانات للحصول على تمثيل أفضل للبيانات.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // تكوين العلامات والعلامات للسلسلة الأولى
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "A1", "Sample Series"), chart.getType());
            series.getMarkerStyleType() = MarkerStyleType.Circle;
            for (int i = 0; i < series.getDataPoints().size(); i++) {
                IDataLabel lbl = series.getDataPoints().get_Item(i).getDataPointLevels().get(0).getLabel();
                lbl.getDataLabelFormat().setShowValue(true);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يقوم هذا الكود بتكوين العلامات والعلامات لسلسلة في الرسم البياني.

### احفظ عرضك التقديمي

بعد إجراء كافة التخصيصات، احفظ العرض التقديمي الخاص بك للحفاظ على التغييرات.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // تخصيص الرسم البياني...

            // حفظ العرض التقديمي
            pres.save("CustomizedLineChart.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

يحفظ هذا الكود العرض التقديمي المخصص الخاص بك كملف PPTX.

## خاتمة

باتباع هذا الدليل، يمكنك استخدام Aspose.Slides لجافا بفعالية لإنشاء وتخصيص مخططات خطية في عروضك التقديمية. جرّب عناصر وأنماطًا مختلفة للمخططات لتحسين المظهر المرئي لبياناتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
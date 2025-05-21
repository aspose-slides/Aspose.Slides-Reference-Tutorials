---
"date": "2025-04-17"
"description": "تعلّم كيفية إنشاء مخططات دائرية رائعة بلغة جافا باستخدام Aspose.Slides. يغطي هذا الدليل الشامل التهيئة، وتكوين البيانات، وحفظ العروض التقديمية."
"title": "إنشاء مخططات دائرية في جافا باستخدام Aspose.Slides - دليل شامل"
"url": "/ar/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات دائرية في جافا باستخدام Aspose.Slides: دليل خطوة بخطوة

## مقدمة

في بيئة اليوم المعتمدة على البيانات، يُعدّ تصوّر المعلومات بفعالية أمرًا أساسيًا لتعزيز الفهم والمشاركة. مع أن إنشاء مخططات بيانية احترافية برمجيًا قد يبدو صعبًا، خاصةً باستخدام جافا، إلا أن هذا الدليل سيرشدك خلال استخدام Aspose.Slides لجافا لإنشاء مخططات بيانية دائرية بسهولة.

من خلال اتباع هذه الخطوات، سيكتسب المطورون خبرة عملية في التعامل مع شرائح العرض التقديمي ودمج تصور البيانات بسلاسة.

**النقاط الرئيسية:**
- قم بتهيئة كائن العرض التقديمي باستخدام Aspose.Slides Java.
- تكوين بيانات الرسم البياني وإدارة السلاسل أو الفئات الموجودة.
- أضف سلاسل وفئات مخصصة لمخططاتك.
- تنسيق وعرض نقاط البيانات بشكل فعال.
- احفظ عرضك التقديمي بتنسيقات مختلفة بكل سهولة.

قبل البدء في التنفيذ، تأكد من أن لديك كل ما تحتاجه للبدء.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:

- **المكتبات المطلوبة:**
  - Aspose.Slides لإصدار Java 25.4 أو أحدث.
  
- **إعداد البيئة:**
  - تم تثبيت JDK 16 أو أعلى على نظامك.
  - IDE مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.

- **المتطلبات المعرفية:**
  - فهم أساسي لمفاهيم برمجة جافا.
  - - المعرفة بإدارة التبعيات في مشاريع Maven أو Gradle.

## إعداد Aspose.Slides لـ Java

لدمج Aspose.Slides في مشروعك، اتبع الخطوات التالية استنادًا إلى أداة البناء الخاصة بك:

**إعداد Maven:**
أضف التبعية التالية إلى ملفك `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**إعداد Gradle:**
قم بتضمين ما يلي في `build.gradle` ملف:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**التحميل المباشر:**
بدلاً من ذلك، قم بتنزيل الإصدار الأحدث مباشرةً من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### الحصول على ترخيص

لاستخدام Aspose.Slides دون قيود التقييم:
- **نسخة تجريبية مجانية:** ابدأ باستخدام ترخيص مؤقت لاستكشاف الميزات الكاملة.
- **رخصة مؤقتة:** احصل على واحدة عبر [موقع Aspose](https://purchase.aspose.com/temporary-license/).
- **شراء:** فكر في الشراء للاستخدام المستمر.

قم بتطبيق الترخيص الخاص بك في تطبيق Java الخاص بك باستخدام:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## دليل التنفيذ

### تهيئة العرض التقديمي والمخطط

#### ملخص
ابدأ بتهيئة كائن العرض التقديمي وإضافة مخطط دائري إلى الشريحة الأولى.

**الخطوة 1: تهيئة العرض التقديمي**
قم بتحميل ملف PPTX الحالي أو قم بإنشاء ملف جديد:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**الخطوة 2: إضافة مخطط دائري**
إنشاء مخطط على الشريحة الأولى عند الإحداثيات المحددة:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### تكوين مصنف بيانات الرسم البياني ومسح السلاسل/الفئات الموجودة

#### ملخص
قم بتكوين مصنف بيانات الرسم البياني وإزالة أي سلسلة أو فئات موجودة مسبقًا.

**الخطوة 1: الوصول إلى مصنف بيانات الرسم البياني**
استرداد المصنف المرتبط بالرسم البياني الخاص بك:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**الخطوة 2: مسح السلاسل والفئات الموجودة**
تأكد من عدم وجود نقاط بيانات متبقية:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### إضافة سلسلة إلى الرسم البياني

#### ملخص
قم بملء الرسم البياني الخاص بك بسلاسل متعددة، كل منها مخصصة للمظهر والسلوك.

**الخطوة 1: إضافة السلسلة بشكل متكرر**
قم بالمرور عبر المؤشرات لإضافة سلسلة:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // تخصيص السلسلة
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### إضافة الفئات ونقاط البيانات إلى الرسم البياني

#### ملخص
قم بتكوين الفئات وإضافة نقاط البيانات باستخدام تنسيق محدد للعلامات.

**الخطوة 1: إضافة الفئات**
التنقل عبر المؤشرات لكل فئة:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**الخطوة 2: إضافة نقاط البيانات إلى كل سلسلة**
قم بالتكرار خلال كل سلسلة للفئة الحالية:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // إعدادات تنسيق نقطة البيانات
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // تنسيق التسمية للسلسلة الأخيرة
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // ضبط خيارات العرض
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // ضبط موضع الملصق
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### حفظ العرض التقديمي

#### ملخص
بمجرد تكوين الرسم البياني الخاص بك، احفظ العرض التقديمي في الدليل المحدد.

**الخطوة 1: حفظ العرض التقديمي**
استخدم `save` طريقة كتابة التغييرات:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## خاتمة

لقد تعلمتَ الآن كيفية إنشاء وتخصيص مخططات الدونات في جافا باستخدام Aspose.Slides. تُشكّل هذه الخطوات أساسًا لدمج تصورات البيانات المتطورة في عروضك التقديمية.

**الخطوات التالية:**
- قم بتجربة أنواع المخططات المختلفة المتوفرة في Aspose.Slides.
- استكشف خيارات التخصيص الإضافية مثل الألوان والخطوط والأنماط لتتناسب مع احتياجات علامتك التجارية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
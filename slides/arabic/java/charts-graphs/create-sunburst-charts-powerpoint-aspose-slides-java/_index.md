---
"date": "2025-04-17"
"description": "تعرّف على كيفية إنشاء وتخصيص مخططات أشعة الشمس في PowerPoint باستخدام Aspose.Slides لجافا. يغطي هذا الدليل خطوة بخطوة الإعداد والتخصيص والتطبيقات العملية."
"title": "إنشاء وتخصيص مخططات Sunburst في PowerPoint باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء وتخصيص مخططات Sunburst في PowerPoint باستخدام Aspose.Slides لـ Java

## مقدمة

غالبًا ما يتطلب إنشاء عروض تقديمية جذابة دمج مخططات جذابة بصريًا لعرض البيانات بفعالية. ومن هذه المخططات مخطط "أشعة الشمس"، الذي يوفر طريقة فريدة لعرض البيانات الهرمية بتصميمه الشعاعي. ومع ذلك، قد تكون إضافة هذه المخططات وتخصيصها مهمة شاقة بدون الأدوات المناسبة. سيرشدك هذا الدليل خلال عملية إنشاء مخططات "أشعة الشمس" وتعديلها في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java.

**ما سوف تتعلمه:**
- إعداد البيئة الخاصة بك لـ Aspose.Slides
- إنشاء عرض تقديمي جديد باستخدام مخطط أشعة الشمس
- تخصيص نقاط البيانات داخل الرسم البياني
- التطبيقات الواقعية لهذه المهارات

دعونا نتعرف على كيفية تبسيط هذه العملية باستخدام Aspose.Slides لـ Java.

## المتطلبات الأساسية

قبل البدء، تأكد من جاهزية بيئة التطوير لديك. ستحتاج إلى:
- **مجموعة تطوير جافا (JDK)** الإصدار 16 أو أعلى
- أن **بيئة التطوير المتكاملة (IDE)** مثل IntelliJ IDEA أو Eclipse
- المعرفة الأساسية بـ **جافا** وعروض PowerPoint

## إعداد Aspose.Slides لـ Java

### تبعية Maven

لتضمين Aspose.Slides في مشروعك، أضف التبعية التالية إلى مشروعك `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### اعتماد Gradle

إذا كنت تستخدم Gradle، قم بتضمين ما يلي في ملفك `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر

بدلاً من ذلك، قم بتنزيل أحدث ملف JAR من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص

لاستخدام Aspose.Slides دون قيود التقييم:
- **نسخة تجريبية مجانية:** ابدأ باستخدام ترخيص مؤقت لاستكشاف الميزات الكاملة.
- **رخصة مؤقتة:** طلب ترخيص مؤقت على [موقع Aspose](https://purchase.aspose.com/temporary-license).
- **شراء:** بالنسبة للمشاريع الجارية، فكر في شراء اشتراك.

### التهيئة الأساسية

إليك كيفية تهيئة Aspose.Slides في تطبيق Java الخاص بك:
```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // قم بتهيئة Aspose.Slides باستخدام ترخيص إذا كان متاحًا
        Presentation pres = new Presentation();
        try {
            // الكود الخاص بك هنا...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## دليل التنفيذ

### إنشاء عرض تقديمي وإضافة مخطط Sunburst

#### ملخص

توضح هذه الميزة كيفية إنشاء عرض تقديمي في PowerPoint من البداية وإضافة مخطط أشعة الشمس.

#### خطوات:
##### الخطوة 1: تهيئة العرض التقديمي
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // استبدل بمسارك
```

##### الخطوة 2: إضافة مخطط Sunburst
أضف مخطط انفجار الشمس إلى الشريحة الأولى في الموضع (100، 100) بحجم (450 × 400).
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

##### الخطوة 3: حفظ العرض التقديمي
احفظ العرض التقديمي الخاص بك للتأكد من تخزين كافة التغييرات.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### تعديل نقاط البيانات في الرسم البياني

#### ملخص
تعرف على كيفية تعديل نقاط البيانات، بما في ذلك التسميات والألوان، داخل مخطط أشعة الشمس.

#### خطوات:
##### الخطوة 1: جمع نقاط بيانات الوصول
قم بالوصول إلى مجموعة نقاط بيانات السلسلة الأولى من الرسم البياني.
```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

##### الخطوة 2: إظهار القيمة لنقطة بيانات محددة
تعديل التسمية لإظهار القيم على مستوى معين.
```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

##### الخطوة 3: تعديل تنسيقات الملصقات
قم بضبط إعدادات العلامة مثل رؤية اسم الفئة ولون النص.
```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

##### الخطوة 4: تعيين لون التعبئة لنقاط البيانات
تخصيص لون التعبئة لنقاط البيانات المحددة.
```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

##### الخطوة 5: حفظ العرض التقديمي المعدّل
احفظ دائمًا تغييراتك لإنهائها.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## التطبيقات العملية

1. **تحليلات الأعمال:** استخدم مخططات Sunburst لتوضيح التسلسلات الهرمية المعقدة للبيانات، مثل بيانات المبيعات حسب المنطقة والفئة.
2. **إدارة المشاريع:** عرض مهام المشروع مقسمة إلى مهام فرعية باستخدام مخطط شعاعي لسهولة التصور.
3. **تعليم:** تمثيل وحدات الدورة والمحاضرات الخاصة بها في العروض التعليمية.

## اعتبارات الأداء

- **تحسين استخدام الموارد:** تأكد من أن تطبيقك يدير الذاكرة بكفاءة، وخاصة عند التعامل مع مجموعات بيانات كبيرة أو مخططات متعددة.
- **إدارة ذاكرة جافا:** استخدم أفضل الممارسات مثل التخلص من الكائنات على الفور لمنع تسرب الذاكرة.

## خاتمة

يُعد إنشاء وتخصيص مخططات Sunburst باستخدام Aspose.Slides لجافا طريقة فعّالة لتحسين عروضك التقديمية. باتباع هذا الدليل، ستتعلم أساسيات إعداد بيئتك، وتطبيق ميزات المخططات، وتعديل نقاط البيانات بفعالية.

**الخطوات التالية:**
- استكشف المزيد من أنواع المخططات المتوفرة في Aspose.Slides.
- جرّب خيارات التخصيص المختلفة لمخططاتك.

**الدعوة إلى العمل:** حاول تنفيذ هذه الحلول في مشروع العرض التقديمي التالي الخاص بك لترى كيف يمكنها تعزيز جهودك في تصور البيانات!

## قسم الأسئلة الشائعة

1. **ما هو مخطط انفجار الشمس؟**
   - يعرض مخطط انفجار الشمس البيانات الهرمية بشكل شعاعي، وهو مثالي لعرض العلاقات المتداخلة.
2. **كيف أقوم بتثبيت Aspose.Slides لـ Java باستخدام Maven؟**
   - أضف التبعية إلى `pom.xml` الملف كما هو موضح في قسم الإعداد أعلاه.
3. **هل يمكنني تعديل أنواع أخرى من الرسوم البيانية باستخدام Aspose.Slides؟**
   - نعم، يدعم Aspose.Slides أنواعًا مختلفة من المخططات مثل المخططات العمودية والخطية والدائرية.
4. **ماذا يجب أن أفعل إذا لم يتم حفظ العرض التقديمي الخاص بي بشكل صحيح؟**
   - تأكد من أن مسار الملف الخاص بك صحيح وأن لديك أذونات الكتابة للدليل.
5. **كيف يمكنني الحصول على مزيد من المساعدة مع Aspose.Slides؟**
   - قم بزيارة [منتدى Aspose](https://forum.aspose.com/c/slides/11) أو تحقق من الوثائق في [مرجع Aspose.Slides](https://reference.aspose.com/slides/java/).

## موارد
- **التوثيق:** [مرجع Aspose.Slides](https://reference.aspose.com/slides/java)
- **المنتدى:** [منتدى أسبوزي](https://forum.aspose.com/c/slides)
- **التنزيلات:** [تنزيلات Aspose.Slides](https://releases.aspose.com/slides/java)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
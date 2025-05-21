---
"date": "2025-04-17"
"description": "تعرّف على كيفية إنشاء وتخصيص مخطط دائري باستخدام Aspose.Slides لجافا. يغطي هذا الدليل الإعداد والتنفيذ والتطبيقات العملية."
"title": "إنشاء مخطط دائري في جافا باستخدام Aspose.Slides - دليل شامل"
"url": "/ar/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخطط دائري في Java باستخدام Aspose.Slides: دليل شامل

## المخططات والرسوم البيانية

### مقدمة

في مجال تصور البيانات، تُعدّ المخططات الدائرية طريقة بديهية لتمثيل النسب داخل مجموعة البيانات. ومع ذلك، عند التعامل مع مجموعات بيانات معقدة حيث تكون بعض الأجزاء أصغر بكثير من غيرها، قد تصبح المخططات الدائرية التقليدية مُزدحمة ويصعب تفسيرها. تُعالج المخططات الدائرية هذه المشكلة بتقسيم أجزاء صغيرة إلى مخطط ثانوي، مما يُحسّن سهولة القراءة.

في هذا البرنامج التعليمي، ستتعلم كيفية إنشاء مخطط دائري ومعالجته باستخدام Aspose.Slides لجافا. ستغطي إعداد بيئتك، وإنشاء المخطط، وتخصيص خصائص مثل تسميات البيانات ومواضع التقسيم، وحفظ عرضك التقديمي بتنسيق PPTX. في النهاية، ستكون قد أتقنت هذه الميزات من خلال تطبيقات عملية ونصائح لتحسين الأداء.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides لـ Java
- إنشاء مخطط دائري
- تخصيص خصائص الرسم البياني مثل تسميات البيانات وتكوينات التقسيم
- حفظ العرض التقديمي الخاص بك على القرص

هل أنت مستعد للبدء؟ لنلقِ نظرة على المتطلبات الأساسية أولًا!

## المتطلبات الأساسية

قبل إنشاء مخطط الفطيرة الخاص بنا، تأكد من أن لديك:

### المكتبات والإصدارات والتبعيات المطلوبة:
- **Aspose.Slides لـ Java**:ضروري لإدارة عروض PowerPoint برمجيًا.

### متطلبات إعداد البيئة:
- مجموعة تطوير جافا (JDK) مُثبّتة على جهازك. نوصي باستخدام JDK 16 أو أحدث.
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.

### المتطلبات المعرفية:
- فهم أساسي لبرمجة جافا
- المعرفة بـ Maven أو Gradle لإدارة التبعيات

## إعداد Aspose.Slides لـ Java

### معلومات التثبيت:

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

**التحميل المباشر**:يمكنك تنزيل الإصدار الأحدث من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص:
- **نسخة تجريبية مجانية**:ابدأ بفترة تجريبية مدتها 30 يومًا لاستكشاف كافة الميزات.
- **رخصة مؤقتة**:اطلب ترخيصًا مؤقتًا للتقييم الموسع.
- **شراء**:فكر في شراء ترخيص إذا كان Aspose.Slides يلبي احتياجاتك.

### التهيئة والإعداد الأساسي

بمجرد إعداد المكتبة في مشروعك، قم بتهيئتها عن طريق إنشاء مثيل لها `Presentation` فصل:

```java
Presentation presentation = new Presentation();
```

هذا يُمهّد الطريق لإضافة مخططات بيانية متنوعة إلى شرائحك. بعد ذلك، لننتقل إلى تطبيق مخططنا الدائري.

## دليل التنفيذ

### إنشاء مخطط "فطيرة الفطيرة"

#### ملخص
سنبدأ بإنشاء مثيل لـ `Presentation` وأضف مخططًا دائريًا على الشريحة الأولى. سيُظهر هذا المخطط البيانات بوضوح من خلال فصل الأجزاء الصغيرة إلى مخطط دائري ثانوي، مما يُحسّن سهولة القراءة.

#### الخطوة 1: إنشاء مثيل لفئة العرض التقديمي
```java
// إنشاء عرض تقديمي جديد
ePresentation presentation = new Presentation();
```
يقوم هذا الكود بتهيئة العرض التقديمي الخاص بك حيث سنضيف مخططاتنا البيانية.

#### الخطوة 2: أضف مخطط "فطيرة الفطيرة" على الشريحة الأولى
```java
// أضف دائرة أو مخطط دائري إلى الشريحة الأولى في الموضع (50، 50) بحجم (500 × 400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
هنا نحدد نوع الرسم البياني (`PieOfPie`) وموقعها وأبعادها على الشريحة.

#### الخطوة 3: تعيين تسميات البيانات لإظهار القيم الخاصة بالسلسلة
```java
// تكوين تسميات البيانات لعرض القيم
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
تضمن هذه الخطوة أن يعرض كل جزء من مخططنا الدائري القيمة المقابلة له، مما يساعد في تفسير البيانات بسرعة.

#### الخطوة 4: تكوين حجم الفطيرة الثانية وتقسيمها حسب النسبة المئوية
```java
// ضبط حجم الفطيرة الثانوية
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// تقسيم الفطيرة حسب النسبة المئوية
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// تعيين موضع الانقسام
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
تتيح لك هذه التكوينات تخصيص كيفية تقسيم الرسم البياني وعرض أجزاء أصغر، مما يؤدي إلى تحسين الوضوح للمشاهدين.

#### الخطوة 5: حفظ العرض التقديمي على القرص بتنسيق PPTX
```java
// تحديد دليل الإخراج
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// احفظ العرض التقديمي\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
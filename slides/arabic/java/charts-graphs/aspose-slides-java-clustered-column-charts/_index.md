---
date: '2026-01-17'
description: تعلم كيفية إنشاء مخطط عمودي مجمع في Java باستخدام Aspose.Slides. يوضح
  هذا الدليل خطوة بخطوة كيفية إضافة المخطط، ضبط الألوان، وحفظ العرض التقديمي.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: كيفية إنشاء مخطط عمودي مجمع في جافا باستخدام Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط عمودي مجمع في Java باستخدام Aspose.Slides

## المقدمة
إنشاء تمثيلات بصرية جذابة للبيانات أمر أساسي لتقديم عروض أعمال مؤثرة، وتعلم **كيفية إنشاء مخطط عمودي مجمع** برمجياً يمكن أن يوفر لك ساعات من العمل اليدوي. يبسّط هذا الدليل خطوة بخطوة عملية استخدام **Aspose.Slides for Java** لإنشاء وتنسيق مخططات عمودية مجمعة بسرعة، مما يعزز عروضك بصور احترافية بسهولة.

سنستعرض كل ما تحتاجه — من إعداد المكتبة إلى إضافة المخطط، تخصيص ألوان السلاسل، وحفظ الملف النهائي.

### ما ستحققه
- تثبيت وتكوين Aspose.Slides for Java  
- **إنشاء مخطط عمودي مجمع** في عرض تقديمي جديد تمامًا  
- تطبيق ألوان تعبئة السلاسل تلقائيًا  
- حفظ العرض التقديمي على القرص  

لنبدأ بالمتطلبات المسبقة قبل بناء المخطط!

## إجابات سريعة
- **ما هو الصنف الأساسي؟** `Presentation` من `com.aspose.slides`  
- **كيف أضيف مخططًا؟** استخدم `addChart(ChartType.ClusteredColumn, ...)` على مجموعة أشكال الشريحة  
- **هل يمكنني ضبط الألوان تلقائيًا؟** نعم، استدعِ `setAutomaticSeriesColor(true)` على كل سلسلة  
- **ما الصيغة المستخدمة للحفظ؟** `SaveFormat.Pptx` (PowerPoint)  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج  

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من توفر الأدوات والمعرفة اللازمة:

### المكتبات والاعتمادات المطلوبة
ستحتاج إلى مكتبة Aspose.Slides for Java. تأكد من أنك تستخدم الإصدار 25.4 مع دعم JDK16.

### متطلبات إعداد البيئة
يجب أن تدعم بيئة التطوير الخاصة بك Java (يفضل JDK16) وأن تكون قادرة على بناء المشاريع باستخدام Maven أو Gradle.

### المتطلبات المعرفية
الإلمام بأساسيات برمجة Java، والعمل مع المكتبات عبر Maven/Gradle، وفهم عروض PowerPoint سيكون مفيدًا.

## إعداد Aspose.Slides for Java
لدمج Aspose.Slides في مشروعك، اتبع تعليمات الإعداد أدناه:

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**تحميل مباشر**  
لمن يفضّلون التحميل المباشر، زر [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية**: ابدأ بنسخة تجريبية مجانية لاستكشاف الميزات.  
- **ترخيص مؤقت**: احصل على ترخيص مؤقت للاختبار بدون قيود.  
- **شراء**: للاستخدام المستمر، اشترِ ترخيصًا كاملاً.

**التهيئة الأساسية والإعداد**  
قم بتهيئة Aspose.Slides كما يلي:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## دليل التنفيذ

### الميزة 1: إنشاء مخطط عمودي مجمع
لننشئ مخططًا عموديًا مجمعًا باستخدام Aspose.Slides for Java. تتيح لك هذه الميزة إضافة مخططات بصرية جذابة إلى شرائحك بسهولة.

#### نظرة عامة
في هذا القسم، سنقوم بتهيئة عرض تقديمي جديد وإدراج مخطط عمودي مجمع في الشريحة الأولى.

**الخطوة 1: تهيئة العرض التقديمي**  
أنشئ كائن `Presentation` لبدء العمل مع ملفات PowerPoint:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**الخطوة 2: إضافة مخطط عمودي مجمع**  
أضف المخطط عند الإحداثيات المحددة (100, 50) والأبعاد (600 × 400):
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**الخطوة 3: تنظيف الموارد**  
دائمًا قم بتحرير الموارد لتجنب تسرب الذاكرة:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

### الميزة 2: ضبط لون تعبئة السلسلة تلقائيًا
عزز الجاذبية البصرية بضبط ألوان تعبئة السلاسل تلقائيًا.

#### نظرة عامة
قم بتعيين لون كل سلسلة في المخطط تلقائيًا للحصول على مظهر متناسق.

**الخطوة 1: الوصول إلى المخطط وتكرار السلاسل**  
بعد إنشاء المخطط، احصل عليه وكرر عبر سلاسله:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**الخطوة 2: إدارة الموارد**  
حرّر كائن العرض التقديمي بمجرد الانتهاء:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

### الميزة 3: حفظ العرض التقديمي على القرص
أخيرًا، احفظ عملك بسهولة باستخدام Aspose.Slides.

#### نظرة عامة
احفظ العروض التقديمية المعدلة بالصيغ والمواقع المطلوبة.

**الخطوة 1: تحديد مسار الإخراج**  
حدد المكان الذي تريد حفظ الملف فيه:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**الخطوة 2: حفظ العرض التقديمي**  
استخدم طريقة `save` لكائن `Presentation`:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## التطبيقات العملية
- **التقارير المالية**: تصور الأرباح الفصلية بوضوح.  
- **تحليل بيانات التسويق**: عرض نتائج الحملات باستخدام مرئيات جذابة.  
- **إدارة المشاريع**: تتبع المعالم والتقدم بصريًا في اجتماعات الفريق.

## اعتبارات الأداء
عند العمل مع Aspose.Slides، ضع في اعتبارك أفضل الممارسات التالية:

- إدارة الذاكرة بفعالية عبر تحرير كائنات `Presentation` فور الانتهاء.  
- تحسين حجم الملفات عند حفظ العروض لتقليل استهلاك مساحة القرص.  
- استخدام هياكل بيانات فعّالة لسلاسل المخطط لتعزيز الأداء.

## الخاتمة
تهانينا! لقد تعلمت كيفية **إنشاء مخطط عمودي مجمع** وتنسيقه باستخدام Aspose.Slides for Java. هذه المهارة لا تُحسّن عروضك فحسب، بل تُبسّط أيضًا عملية تمثيل البيانات بصريًا.

**الخطوات التالية:**  
استكشف ميزات إضافية مثل تخصيص عناصر المخطط، إضافة تسميات البيانات، أو التكامل مع مصادر البيانات لتوسيع قدرات مشروعك.

## قسم الأسئلة المتكررة
1. **كيف أقوم بتثبيت Aspose.Slides لإصدار JDK معين؟**  
   - استخدم تبعيات Maven/Gradle مع تحديد `classifier` كما هو موضح في قسم الإعداد.  
2. **ماذا أفعل إذا لم يتم حفظ العرض التقديمي بشكل صحيح؟**  
   - تأكد من وجود أذونات كتابة في دليل الإخراج وأن مسار الملف صحيح.  
3. **هل يمكنني إنشاء أنواع أخرى من المخططات باستخدام Aspose.Slides for Java؟**  
   - بالتأكيد! استكشف خيارات `ChartType` مثل المخططات الدائرية، الشريطية، أو الخطية.  
4. **كيف أتعامل مع مجموعات بيانات كبيرة في مخططي؟**  
   - حسّن هياكل البيانات وفكّر في معالجة البيانات مسبقًا قبل تصورها.  
5. **أين يمكنني العثور على المزيد من الأمثلة لاستخدام Aspose.Slides for Java؟**  
   - زر [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) للحصول على أدلة شاملة وعينات كود.

## الموارد
- **التوثيق**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **التحميل**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **الشراء**: [Buy a License](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **ترخيص مؤقت**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **الدعم**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-01-17  
**تم الاختبار مع:** Aspose.Slides 25.4 (JDK16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-05-29'
description: تعلم كيفية إنشاء pie chart Aspose باستخدام Aspose.Slides Maven، إضافة
  pie chart Java إلى شريحة، وتخصيص chart data. step‑by‑step guide مع إعداد Maven وreal‑world
  examples.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: إنشاء pie chart Aspose – إضافة مخطط إلى عرض تقديمي باستخدام Maven
url: /ar/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط دائري إلى عرض تقديمي باستخدام Aspose.Slides Java

## المقدمة
في هذا الدليل ستقوم **create pie chart aspose** باستخدام Aspose.Slides Maven وسترى كيفية تضمينه في شريحة PowerPoint. إنشاء عروض تقديمية جذابة بصريًا أمر حاسم لنقل المعلومات بفعالية، خاصة عندما يلعب تصور البيانات دورًا رئيسيًا. إذا كنت تتطلع إلى أتمتة هذه العملية باستخدام **aspose slides maven**، فأنت في المكان الصحيح. سنستعرض إضافة مخطط إلى شريحة — تحديدًا مخططًا دائريًا — وتخصيصه لسيناريوهات العالم الحقيقي.

### ما ستتعلمه
- كيفية تهيئة كائن عرض تقديمي في Java.  
- خطوات **add a pie chart java** على الشريحة الأولى من العرض التقديمي.  
- الوصول إلى دفاتر عمل بيانات المخطط وإدراج أوراق العمل داخلها.  

لنغص في كيفية الاستفادة من Aspose.Slides Java لتعزيز عروضك التقديمية بالمخططات الديناميكية!

## إجابات سريعة
- **ما المكتبة التي تضيف المخططات عبر Maven؟** aspose slides maven  
- **ما نوع المخطط الذي تم توضيحه؟** Pie chart (add chart to slide)  
- **ما هو الحد الأدنى لإصدار Java المطلوب؟** JDK 16 or later  
- **هل أحتاج إلى ترخيص للاختبار؟** A free trial works; production needs a license  
- **أين يمكنني العثور على تبعية Maven؟** In the setup section below  

## ما هو Aspose Slides Maven؟
Aspose.Slides for Java هي واجهة برمجة تطبيقات قوية تتيح للمطورين إنشاء وتعديل وعرض ملفات PowerPoint برمجيًا. حزمة Maven (`aspose-slides`) تبسط إدارة التبعيات، مما يسمح لك بالتركيز على بناء وتخصيص الشرائح—مثل إضافة مخطط دائري—دون التعامل مع معالجة الملفات على مستوى منخفض.

## لماذا تستخدم Aspose.Slides Maven لإضافة مخطط إلى شريحة؟
استخدام Aspose.Slides Maven يتيح لك إنشاء المخططات مباشرةً من كود Java دون تعديل يدوي في PowerPoint. يوفر تحكمًا برمجيًا كاملاً في أنواع المخططات ومصادر البيانات والتنسيق، مما يضمن اتساق العلامة التجارية والدقة. كما يتولى عنصر Maven جميع التبعيات المطلوبة، مما يبسط عمليات البناء ويسمح بالتكامل السلس في خطوط CI/CD.

## المتطلبات المسبقة
- **Aspose.Slides for Java** الإصدار 25.4 أو أحدث (Maven/Gradle).  
- JDK 16+ مثبت.  
- بيئة تطوير متكاملة (IntelliJ IDEA, Eclipse, إلخ).  
- معرفة أساسية بـ Java وإلمام بـ Maven أو Gradle.

## إعداد Aspose.Slides لـ Java
أولاً، أدرج Aspose.Slides في مشروعك عبر Maven أو Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، يمكنك [download the latest release](https://releases.aspose.com/slides/java/) مباشرةً من موقع Aspose.

### الحصول على الترخيص
Aspose.Slides for Java يقدم نسخة تجريبية مجانية مع ترخيص مؤقت للاختبار. للاستخدام غير المحدود في الإنتاج، اشترِ ترخيصًا عبر [purchase page](https://purchase.aspose.com/buy).

## دليل التنفيذ
فيما يلي نقسم الحل إلى ميزتين: إضافة مخطط دائري والوصول إلى دفتر بياناته.

### الميزة 1: إنشاء عرض تقديمي وإضافة مخطط
#### نظرة عامة
هذا الجزء يوضح كيفية إنشاء عرض تقديمي جديد و**add a pie chart** إلى الشريحة الأولى.

#### كيف تنشئ مخطط دائري باستخدام aspose؟
حمّل فئة `Presentation`، أضف مخططًا من النوع `ChartType.Pie`، واحفظ الملف. العملية بأكملها تتطلب ثلاث نداءات API فقط وتستغرق أقل من ثانية لعرض تقديمي مكوّن من 10 شرائح تقريبًا، مما يجعلها مثالية لتوليد التقارير تلقائيًا.

#### خطوة بخطوة

**الخطوة 1: تهيئة كائن عرض تقديمي جديد**  
فئة `Presentation` هي الكائن الأعلى مستوى في Aspose.Slides الذي يمثل ملف PowerPoint في الذاكرة.  
```java
Presentation pres = new Presentation();
```
*ينشئ كائن `Presentation` الذي سيحتوي على جميع الشرائح.*

**الخطوة 2: إضافة مخطط دائري**  
`ChartType.Pie` يخبر Aspose بإنشاء مخطط دائري.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*يضع مخططًا دائريًا عند الإحداثيات (50, 50) بعرض 400 وارتفاع 500.*

**الخطوة 3: تحرير الموارد**  
استدعاء `dispose()` يحرر الموارد الأصلية ويمنع تسرب الذاكرة.  
```java
if (pres != null) pres.dispose();
```
*يحرر الموارد الأصلية؛ يجب دائمًا استدعاء `dispose()` عند الانتهاء.*

### الميزة 2: الوصول إلى دفتر بيانات المخطط وأوراق العمل
#### نظرة عامة
تعلم كيفية الوصول إلى دفتر العمل الداخلي الذي يخزن بيانات المخطط والتجول عبر أوراقه.

#### كيف تصل إلى دفتر بيانات المخطط؟
احصل على `IChartDataWorkbook` من المخطط، ثم تكرار مجموعة `Worksheets`. هذا الدفتر يشبه ملف Excel، مما يتيح لك قراءة أو تعديل أو إضافة سلاسل بيانات برمجيًا، وسيعكس المخطط التغييرات فورًا عند التحديث أثناء التشغيل دون الحاجة لإعادة تشغيل.

#### خطوة بخطوة

**الخطوة 1: (إعادة استخدام) تهيئة كائن عرض تقديمي جديد**  
*نفس الخطوة 1 في الميزة 1.*

**الخطوة 2: (إعادة استخدام) إضافة مخطط دائري**  
*نفس الخطوة 2 في الميزة 1.*

**الخطوة 3: الحصول على دفتر بيانات المخطط**  
`IChartDataWorkbook` هو الواجهة التي توفر وصولًا للقراءة والكتابة إلى دفتر العمل الداخلي للمخطط.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*يسترجع `IChartDataWorkbook` المرتبط بالمخطط.*

**الخطوة 4: التجول عبر أوراق العمل**  
كائنات `Worksheet` تمثل أوراقًا فردية داخل دفتر العمل.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*يطبع اسم كل ورقة عمل، مما يتيح لك التحقق من بنية البيانات.*

**الخطوة 5: تحرير الموارد**  
*نفس الخطوة 3 في الميزة 1.*

## تطبيقات عملية
- **تقارير البيانات:** إنشاء عروض شرائح تلقائيًا مع مؤشرات محدثة لاستخبارات الأعمال.  
- **العروض الأكاديمية:** تصور نتائج البحث دون إنشاء مخطط يدوي.  
- **المواد التسويقية:** عرض أداء المنتج أو نتائج الاستطلاعات فورًا.

## اعتبارات الأداء
- Aspose.Slides يمكنه التعامل مع **50+ input and output formats** ومعالجة عروض مئات الصفحات دون تحميل الملف بالكامل في الذاكرة.  
- حافظ على عدد الشرائح والمخططات معقولًا؛ كل مخطط يستهلك ذاكرة أصلية.  
- دائمًا استدعِ `dispose()` لتحرير الموارد بسرعة.  
- حسّن معالجة بيانات دفتر العمل—تجنب تحميل مجموعات بيانات ضخمة في مخطط واحد.

## الخلاصة
غطينا كيف يتيح لك **aspose slides maven** **add chart to slide** برمجيًا وكيفية العمل مع دفتر بيانات المخطط. باستخدام هذه اللبنات الأساسية يمكنك أتمتة أي سير عمل تقارير يتطلب مخرجات PowerPoint مصقولة.

### الخطوات التالية
- استكشف خيارات تنسيق المخطط (الألوان، الأساطير، تسميات البيانات).  
- الاتصال بمصادر بيانات خارجية (CSV، قواعد البيانات) لملء المخططات ديناميكيًا.  
- دمج أنواع متعددة من المخططات في عرض تقديمي واحد لسرد قصصي أغنى.

## الأسئلة المتكررة

**س: كيف أقوم بتثبيت Aspose.Slides لـ Java؟**  
ج: استخدم تبعية Maven أو Gradle الموضحة أعلاه، أو قم بتنزيل المكتبة من صفحة الإصدارات.

**س: ما هي متطلبات النظام لـ Aspose.Slides؟**  
ج: JDK 16 أو أحدث؛ المكتبة تعمل على أي منصة تدعم Java.

**س: هل يمكنني إضافة أنواع مخططات أخرى غير المخططات الدائرية؟**  
ج: نعم، يدعم Aspose.Slides المخططات الشريطية، الخطية، المتناثرة، الرادارية، وأكثر من 20 نوعًا من المخططات.

**س: كيف يمكنني التعامل مع العروض الكبيرة بكفاءة؟**  
ج: حرّر الكائنات بسرعة، قلل من حجم الصور عالية الدقة، وأعد استخدام قوالب المخططات لتقليل استهلاك الذاكرة.

**س: أين يمكنني العثور على مزيد من التفاصيل حول ميزات Aspose.Slides؟**  
ج: زر [Aspose documentation](https://reference.aspose.com/slides/java/) للحصول على مرجع API كامل.

**س: هل يلزم ترخيص للاستخدام التجاري؟**  
ج: الترخيص الساري مطلوب للإنتاج؛ النسخة التجريبية مجانية للتقييم.

**س: هل تتضمن حزمة Maven جميع قدرات المخططات؟**  
ج: نعم، حزمة `aspose-slides` Maven تحتوي على محرك المخططات الكامل.

## الموارد
- التوثيق: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- التنزيل: [Latest Releases](https://releases.aspose.com/slides/java/)
- الشراء والتجربة: [Purchase Page](https://purchase.aspose.com/buy)
- الإصدار التجريبي المجاني: [Trial Downloads](https://releases.aspose.com/slides/java/)
- الترخيص المؤقت: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- منتدى الدعم: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**آخر تحديث:** 2026-05-29  
**تم الاختبار مع:** Aspose.Slides 25.4 for Java (jdk16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Create a Pie of Pie Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
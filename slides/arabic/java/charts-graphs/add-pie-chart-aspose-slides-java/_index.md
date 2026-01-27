---
date: '2026-01-09'
description: اكتشف كيفية استخدام Aspose Slides Maven لإضافة مخطط إلى شريحة وتخصيص
  مخطط دائري في عروض Java التقديمية. إعداد خطوة بخطوة، الكود، وأمثلة من الواقع.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - إضافة مخطط دائري إلى عرض تقديمي'
url: /ar/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط دائري إلى عرض تقديمي باستخدام Aspose.Slides Java

## مقدمة
إن إنشاء عروض تقديمية جذابة بصريًا أمر حيوي لنقل المعلومات بفعالية، خاصة عندما يلعب تصور البيانات دورًا أساسيًا. إذا كنت ترغب في أتمتة هذه العملية باستخدام **aspose slides maven**، فأنت في المكان الصحيح. في هذا الدليل ستتعلم كيفية **add chart to slide** — وبالتحديد مخطط دائري — باستخدام Aspose.Slides for Java، وسترى كيف يمكنك تخصيصه لسيناريوهات العالم الحقيقي.

### ما ستتعلمه
- كيفية تهيئة كائن عرض تقديمي في Java.  
- خطوات **add a pie chart java** على الشريحة الأولى من العرض.  
- الوصول إلى دفاتر بيانات المخطط وقائمة الأوراق داخلها.  

هيا نغوص في كيفية الاستفادة من Aspose.Slides Java لتعزيز عروضك التقديمية بالمخططات الديناميكية!

## إجابات سريعة
- **ما المكتبة التي تضيف المخططات عبر Maven؟** aspose slides maven  
- **ما نوع المخطط المعروض؟** مخطط دائري (add chart to slide)  
- **ما هو الحد الأدنى لإصدار Java المطلوب؟** JDK 16 أو أحدث  
- **هل أحتاج إلى ترخيص للاختبار؟** الإصدار التجريبي المجاني يعمل؛ الإنتاج يتطلب ترخيصًا  
- **أين يمكنني العثور على تبعية Maven؟** في قسم الإعداد أدناه  

## ما هو Aspose Slides Maven؟
Aspose.Slides for Java هو API قوي يتيح للمطورين إنشاء ملفات PowerPoint وتعديلها وعرضها برمجيًا. حزمة Maven (`aspose-slides`) تبسط إدارة التبعيات، مما يسمح لك بالتركيز على بناء وتخصيص الشرائح—مثل إضافة مخطط دائري—دون الحاجة للتعامل مع معالجة الملفات منخفضة المستوى.

## لماذا نستخدم Aspose.Slides Maven لإضافة مخطط إلى شريحة؟
- **الأتمتة:** توليد التقارير ولوحات التحكم تلقائيًا.  
- **الدقة:** تحكم كامل في أنواع المخططات والبيانات والتنسيق.  
- **متعددة المنصات:** يعمل على أي بيئة متوافقة مع Java.  

## المتطلبات المسبقة
- **Aspose.Slides for Java** الإصدار 25.4 أو أحدث (Maven/Gradle).  
- JDK 16+ مثبت.  
- بيئة تطوير متكاملة (IntelliJ IDEA، Eclipse، إلخ).  
- معرفة أساسية بـ Java وإلمام بـ Maven أو Gradle.

## إعداد Aspose.Slides for Java
أولاً، أدرج Aspose.Slides في مشروعك عبر Maven أو Gradle.

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، يمكنك [download the latest release](https://releases.aspose.com/slides/java/) مباشرةً من موقع Aspose.

### الحصول على الترخيص
Aspose.Slides for Java يقدم نسخة تجريبية مجانية مع ترخيص مؤقت للاختبار. للاستخدام الإنتاجي غير المحدود، اشترِ ترخيصًا عبر [purchase page](https://purchase.aspose.com/buy).

## دليل التنفيذ
سنقسم الحل إلى ميزتين: إضافة مخطط دائري والوصول إلى دفتر بياناته.

### الميزة 1: إنشاء عرض تقديمي وإضافة مخطط
#### نظرة عامة
هذا الجزء يوضح كيفية إنشاء عرض تقديمي جديد و**add a pie chart** إلى الشريحة الأولى.

#### خطوة بخطوة

**الخطوة 1: تهيئة كائن Presentation جديد**  
```java
Presentation pres = new Presentation();
```
*ينشئ كائن `Presentation` الذي سيحمل جميع الشرائح.*

**الخطوة 2: إضافة مخطط دائري**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*يضع مخططًا دائريًا عند الإحداثيات (50, 50) بعرض 400 وارتفاع 500. يحدد تعداد `ChartType.Pie` لـ Aspose أن يتم رسم مخطط دائري.*

**الخطوة 3: تحرير الموارد**  
```java
if (pres != null) pres.dispose();
```
*يفرغ الموارد الأصلية؛ يجب دائمًا استدعاء `dispose()` عند الانتهاء.*

### الميزة 2: الوصول إلى دفتر بيانات المخطط والأوراق
#### نظرة عامة
تعلم كيفية الوصول إلى دفتر العمل الأساسي الذي يخزن بيانات المخطط وتكرار أوراقه.

#### خطوة بخطوة

**الخطوة 1: (إعادة استخدام) تهيئة كائن Presentation جديد**  
*نفس خطوة 1 في الميزة 1.*

**الخطوة 2: (إعادة استخدام) إضافة مخطط دائري**  
*نفس خطوة 2 في الميزة 1.*

**الخطوة 3: الحصول على دفتر بيانات المخطط**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*يسترجع `IChartDataWorkbook` المرتبط بالمخطط.*

**الخطوة 4: تكرار الأوراق**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*يطبع اسم كل ورقة عمل، مما يتيح لك التحقق من بنية البيانات.*

**الخطوة 5: تحرير الموارد**  
*نفس خطوة 3 في الميزة 1.*

## تطبيقات عملية
- **تقارير البيانات:** توليد عروض شرائح تلقائيًا ببيانات محدثة لأغراض ذكاء الأعمال.  
- **العروض الأكاديمية:** تصور نتائج الأبحاث دون الحاجة لإنشاء مخططات يدويًا.  
- **المواد التسويقية:** عرض أداء المنتج أو نتائج الاستطلاعات فورًا.

## اعتبارات الأداء
- حافظ على عدد الشرائح والمخططات معقولًا؛ كل منها يستهلك ذاكرة.  
- استدعِ دائمًا `dispose()` لتحرير الموارد الأصلية.  
- حسّن معالجة بيانات دفتر العمل—تجنب تحميل مجموعات بيانات ضخمة في مخطط واحد.

## الخلاصة
لقد استعرضنا كيف يتيح لك **aspose slides maven** **add chart to slide** برمجيًا وكيفية التعامل مع دفتر بيانات المخطط. باستخدام هذه اللبنات الأساسية يمكنك أتمتة أي سير عمل تقارير يتطلب مخرجات PowerPoint مصقولة.

### الخطوات التالية
- استكشف خيارات تنسيق المخطط (الألوان، الأساطير، تسميات البيانات).  
- اربط مصادر بيانات خارجية (CSV، قواعد بيانات) لتعبئة المخططات ديناميكيًا.  
- اجمع أنواع مخططات متعددة في عرض تقديمي واحد لسرد قصص أكثر غنى.

## الأسئلة المتكررة

**س: كيف أُثبّت Aspose.Slides for Java؟**  
ج: استخدم تبعية Maven أو Gradle الموضحة أعلاه، أو حمّل المكتبة من صفحة الإصدارات.

**س: ما هي متطلبات النظام لـ Aspose.Slides؟**  
ج: JDK 16 أو أحدث؛ المكتبة مستقلة عن النظام الأساسي.

**س: هل يمكنني إضافة أنواع مخططات أخرى غير المخطط الدائري؟**  
ج: نعم، يدعم Aspose.Slides المخططات الشريطية، الخطية، المبعثرة، والعديد غيرها.

**س: كيف أتعامل مع عروض تقديمية كبيرة بكفاءة؟**  
ج: حرّر الكائنات فورًا، قلل عدد الصور عالية الدقة، وأعد استخدام قوالب المخططات عند الإمكان.

**س: أين يمكنني العثور على مزيد من التفاصيل حول ميزات Aspose.Slides؟**  
ج: زر [Aspose documentation](https://reference.aspose.com/slides/java/) للحصول على مرجع API كامل.

**س: هل يلزم ترخيص للاستخدام التجاري؟**  
ج: نعم، يتطلب الإنتاج ترخيصًا صالحًا؛ تتوفر نسخة تجريبية مجانية للتقييم.

**س: هل حزمة Maven تشمل جميع قدرات المخططات؟**  
ج: نعم، حزمة `aspose-slides` Maven تحتوي على محرك المخططات الكامل.

## الموارد
- الوثائق: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- التحميل: [Latest Releases](https://releases.aspose.com/slides/java/)
- الشراء والتجربة: [Purchase Page](https://purchase.aspose.com/buy)
- نسخة تجريبية مجانية: [Trial Downloads](https://releases.aspose.com/slides/java/)
- ترخيص مؤقت: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- منتدى الدعم: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**آخر تحديث:** 2026-01-09  
**تم الاختبار مع:** Aspose.Slides 25.4 for Java (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

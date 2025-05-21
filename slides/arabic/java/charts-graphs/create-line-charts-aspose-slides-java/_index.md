---
"date": "2025-04-17"
"description": "تعلّم كيفية إنشاء مخططات خطية بعلامات في جافا باستخدام Aspose.Slides. يغطي هذا البرنامج التعليمي إنشاء المخططات، وجمع السلاسل، وحفظ العروض التقديمية بفعالية."
"title": "إنشاء مخططات خطية باستخدام علامات افتراضية باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات خطية باستخدام علامات افتراضية باستخدام Aspose.Slides لـ Java
## مقدمة
يُعد إنشاء مخططات بيانية جذابة بصريًا وغنية بالمعلومات أمرًا أساسيًا للعروض التقديمية والتقارير ولوحات المعلومات. أتمتة هذه العملية في تطوير البرمجيات توفر الوقت وتضمن الاتساق بين المستندات. يوضح هذا البرنامج التعليمي كيفية إنشاء مخططات بيانية خطية مع علامات باستخدام Aspose.Slides لجافا.
**Aspose.Slides لـ Java** مكتبة قوية تُمكّن المطورين من التعامل مع عروض PowerPoint التقديمية برمجيًا دون الحاجة إلى تثبيت Microsoft Office. تُبسّط هذه المكتبة مهامًا مثل إنشاء الشرائح وتحريرها وتصديرها، مما يجعلها أداة أساسية لإنشاء المستندات تلقائيًا.
**ما سوف تتعلمه:**
- كيفية تهيئة Aspose.Slides لـ Java
- خطوات إنشاء مخطط خطي باستخدام العلامات
- إضافة السلاسل والفئات إلى المخططات البيانية
- تكوين أساطير الرسم البياني
- حفظ العرض التقديمي
هل أنت مستعد للبدء؟ تأكد من تجهيز كل شيء أولًا!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن بيئة التطوير الخاصة بك جاهزة:
1. **المكتبات والتبعيات:**
   - مكتبة Aspose.Slides لـ Java (الإصدار 25.4 الموصى به)
   - مجموعة تطوير Java (JDK) الإصدار 16 أو أعلى
2. **إعداد البيئة:**
   - يجب أن يدعم IDE الخاص بك أدوات بناء Maven أو Gradle.
   - تأكد من أن لديك ملف ترخيص صالح إذا لزم الأمر.
3. **المتطلبات المعرفية:**
   - فهم أساسي لبرمجة جافا
   - المعرفة ببناء المشاريع باستخدام Maven أو Gradle
بعد وضع هذه العناصر في مكانها، فلنبدأ في إعداد Aspose.Slides لمشروعك!
## إعداد Aspose.Slides لـ Java
لاستخدام Aspose.Slides في Java، عليك تضمينه كاعتمادية في مشروعك. سيختلف الإعداد قليلاً حسب استخدامك لـ Maven أو Gradle.
### مافن
أضف التبعية التالية إلى ملفك `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### جرادل
قم بتضمين هذا في `build.gradle` ملف:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### التحميل المباشر
بدلاً من ذلك، يمكنك تنزيل الإصدار الأحدث من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).
**خطوات الحصول على الترخيص:**
- للحصول على نسخة تجريبية مجانية، قم بزيارة [صفحة التجربة المجانية](https://releases.aspose.com/slides/java/).
- للحصول على ترخيص مؤقت، انتقل إلى [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).
- شراء ترخيص كامل من خلالهم [بوابة الشراء](https://purchase.aspose.com/buy).
**التهيئة الأساسية:**
إليك كيفية تهيئة Aspose.Slides في تطبيق Java الخاص بك:
```java
import com.aspose.slides.Presentation;
// تهيئة كائن عرض تقديمي جديد
Presentation pres = new Presentation();
```
الآن، دعونا ننتقل إلى إنشاء المخططات البيانية!
## دليل التنفيذ
### الميزة 1: إنشاء مخطط باستخدام العلامات الافتراضية
يوضح هذا القسم كيفية إنشاء مخطط خطي مزود بعلامات. تُعد هذه الميزة أساسية لعرض اتجاهات البيانات بفعالية.
#### إضافة مخطط خطي
لإضافة مخطط خطي مع علامات:
```java
import com.aspose.slides.*;
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
// أضف مخططًا خطيًا مع علامات إلى الشريحة في الموضع (10، 10) بحجم (400، 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### سلسلة وفئات التصفية
للبدء من جديد:
```java
// مسح السلاسل والفئات الموجودة لضمان سجل نظيف
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// احصل على مصنف بيانات الرسم البياني لمزيد من التلاعب
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### الميزة 2: إضافة السلاسل والفئات
يعد إضافة السلاسل والفئات أمرًا بالغ الأهمية لملء مخططاتك ببيانات ذات معنى.
#### إنشاء سلسلة جديدة
لإضافة سلسلة جديدة باسم "السلسلة 1":
```java
// إضافة سلسلة جديدة إلى الرسم البياني
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// الوصول إلى السلسلة الأولى لتعبئة البيانات
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### ملء الفئات ونقاط البيانات
لإضافة الفئات ونقاط البيانات المقابلة:
```java
// أضف أسماء الفئات ونقاط البيانات الخاصة بها
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// التعامل مع نقاط البيانات الفارغة بسلاسة
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### الميزة 3: إضافة السلسلة الثانية وملء نقاط البيانات
تؤدي إضافة سلسلة إضافية إلى توفير مزيد من العمق لمخططاتك.
#### إنشاء سلسلة ثانية وتعبئتها
لإضافة "السلسلة 2":
```java
// أضف سلسلة أخرى باسم "السلسلة 2"
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// الوصول إلى السلسلة الثانية لتعبئة البيانات
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// إضافة نقاط البيانات لـ "السلسلة 2"
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### الميزة 4: تكوين أسطورة الرسم البياني
يؤدي تكوين الأسطورة إلى تحسين إمكانية قراءة الرسم البياني.
#### ضبط إعدادات الأسطورة
لتكوين:
```java
// تمكين الأسطورة وتعيينها بحيث لا تتداخل مع نقاط البيانات
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### الميزة 5: حفظ العرض التقديمي
بمجرد أن يصبح الرسم البياني جاهزًا، احفظ العرض التقديمي في ملف.
```java
try {
    // حفظ العرض التقديمي المعدل في الدليل المحدد
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## التطبيقات العملية
1. **تقارير الأعمال:**
   - استخدم المخططات البيانية في التقارير المالية لتصوير الاتجاهات بمرور الوقت.
2. **تحليل البيانات:**
   - تصور أنماط البيانات وارتباطاتها أثناء مراحل التحليل.
3. **المواد التعليمية:**
   - إنشاء شرائح إعلامية للمحاضرات أو العروض التقديمية الأكاديمية.
4. **إدارة المشاريع:**
   - قم بتعزيز الجداول الزمنية للمشروع باستخدام عناصر المخطط المرئي.
5. **العروض التقديمية التسويقية:**
   - عرض اتجاهات المبيعات ونتائج الحملة بشكل فعال باستخدام المخططات البيانية.
## خاتمة
لقد تعلمتَ كيفية إنشاء مخططات خطية مع علامات في جافا باستخدام Aspose.Slides، وإضافة سلاسل وفئات، وتكوين الأساطير، وحفظ العروض التقديمية. هذه المهارات قيّمة لإنشاء محتوى مرئي ديناميكي في مختلف التطبيقات المهنية.
لاستكشاف المزيد حول ميزات Aspose.Slides أو طلب دعم المجتمع، تفضل بزيارة [الوثائق الرسمية](https://docs.aspose.com/slides/java/) أو انضم إلى المنتديات مثل Stack Overflow.
برمجة سعيدة!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
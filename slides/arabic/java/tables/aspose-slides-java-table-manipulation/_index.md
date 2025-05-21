---
"date": "2025-04-18"
"description": "تعلم كيفية إنشاء الجداول ومعالجتها في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. حسّن عروضك التقديمية بجداول ديناميكية غنية بالبيانات بكل سهولة."
"title": "إدارة الجداول الرئيسية في عروض Java التقديمية باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/tables/aspose-slides-java-table-manipulation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إدارة الجداول الرئيسية في عروض Java التقديمية باستخدام Aspose.Slides لـ Java
## كيفية إنشاء الجداول ومعالجتها في العروض التقديمية باستخدام Aspose.Slides لـ Java
في عالمنا الرقمي المتسارع، أصبح إنشاء عروض تقديمية ديناميكية أكثر أهمية من أي وقت مضى. مع Aspose.Slides لجافا، يمكنك إنشاء الجداول وتعديلها بسلاسة داخل شرائح PowerPoint باستخدام بضعة أسطر من التعليمات البرمجية. سيرشدك هذا البرنامج التعليمي خلال عملية إعداد Aspose.Slides لجافا وتطبيق ميزات متنوعة لتحسين عروضك التقديمية.

### مقدمة
هل واجهتَ يومًا صعوبة في إنشاء جداول في عروض PowerPoint التقديمية، بحيث تكون جذابة بصريًا وغنية بالبيانات؟ مع Aspose.Slides لجافا، ستنتهي هذه التحديات. تتيح لك هذه المكتبة القوية إنشاء نماذج للعروض التقديمية، والوصول إلى الشرائح، وتحديد أبعاد الجداول، وإضافة الجداول وتخصيصها، وضبط النصوص داخل الخلايا، وتعديل إطارات النص، ومحاذاة النص عموديًا، وحفظ عملك بكفاءة.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides لـ Java
- إنشاء مثيل عرض تقديمي جديد
- الوصول إلى الشرائح في العرض التقديمي
- تحديد أبعاد الجدول وإضافتها إلى الشرائح
- تخصيص الجداول عن طريق تعيين نص الخلية وتعديل إطارات النص
- محاذاة النص عموديًا داخل خلايا الجدول
- حفظ العروض التقديمية المعدلة
دعونا نبدأ باستكشاف المتطلبات الأساسية المطلوبة لهذا البرنامج التعليمي.

### المتطلبات الأساسية
قبل البدء في التنفيذ، تأكد من أن لديك ما يلي:
- **المكتبات والتبعيات:** Aspose.Slides لإصدار Java 25.4 أو أحدث.
- **إعداد البيئة:** JDK متوافق (يفضل JDK16 وفقًا لأمثلة لدينا).
- **المتطلبات المعرفية:** فهم أساسي لبرمجة Java والمعرفة باستخدام أدوات بناء Maven أو Gradle.

### إعداد Aspose.Slides لـ Java
للبدء، ستحتاج إلى إضافة التبعيات اللازمة لمشروعك. إليك كيفية القيام بذلك:

#### مافن
أضف التبعية التالية في ملفك `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### جرادل
بالنسبة لمستخدمي Gradle، قم بتضمين هذا في `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
بدلاً من ذلك، يمكنك تنزيل أحدث ملف JAR من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

**الحصول على الترخيص:** يقدم Aspose ترخيصًا تجريبيًا مجانيًا لاستكشاف ميزاته. يمكنك التقدم بطلب للحصول على ترخيص مؤقت أو شراء ترخيص عند الحاجة.

### التهيئة الأساسية
بعد إعداد مشروعك، قم بتهيئة `Presentation` الصف كما هو موضح أدناه:
```java
import com.aspose.slides.Presentation;
// إنشاء مثيل للعرض التقديمي
Presentation presentation = new Presentation();
try {
    // الكود الخاص بك هنا
} finally {
    if (presentation != null) presentation.dispose();
}
```

## دليل التنفيذ
الآن وقد أصبحت بيئتك جاهزة، لنبدأ في التنفيذ. سنُفصّلها حسب الميزات للتوضيح.

### إنشاء مثيل للعرض التقديمي
توضح هذه الميزة تهيئة `Presentation` مثال:
```java
import com.aspose.slides.Presentation;
// تهيئة عرض تقديمي جديد
global slide;
presentation = new Presentation();
try {
    // كود للتعامل مع الشرائح والأشكال
} finally {
    if (presentation != null) presentation.dispose();
}
```
**غاية:** ضمان إدارة الموارد بشكل صحيح مع `dispose()` الطريقة في `finally` حاجز.

### احصل على شريحة من العرض التقديمي
الوصول إلى الشريحة الأولى سهل:
```java
import com.aspose.slides.Presentation;
global slide;
presentation = new Presentation();
try {
    // الوصول إلى الشريحة الأولى
    ISlide slide = presentation.getSlides().get_Item(0);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**توضيح:** `get_Item(0)` يقوم باسترجاع الشريحة الأولى، والتي تم فهرستها عند 0.

### تحديد أبعاد الجدول وإضافة جدول إلى الشريحة
قم بتحديد عرض الأعمدة وارتفاع الصفوف قبل إضافة جدول:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120}; // عرض الأعمدة
double[] dblRows = {100, 100, 100, 100}; // ارتفاعات الصفوف

    // أضف جدولاً إلى الشريحة في الموضع (x: 100، y: 50)
    ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**تكوين المفتاح:** حدد الأبعاد باستخدام المصفوفات للأعمدة والصفوف.

### تعيين النص في خلايا الجدول
قم بتخصيص الجدول الخاص بك عن طريق تعيين النص داخل الخلايا:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // تعيين النص لخلايا محددة
    tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
} finally {
    if (presentation != null) presentation.dispose();
}
```
**ملحوظة:** يستخدم `getTextFrame().setText()` لتعيين محتوى الخلية.

### الوصول إلى إطار النص وتعديله في خلية
يتيح الوصول إلى إطارات النص إمكانية التخصيص بشكل أكبر:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // الوصول إلى إطار النص وتعديل المحتوى
    ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);

portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**توضيح:** تعديل النص وخصائصه، مثل اللون، باستخدام `Portion` أشياء.

### محاذاة النص عموديًا في خلية
يؤدي محاذاة النص عموديًا إلى تحسين إمكانية القراءة:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // محاذاة النص عموديا
    ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center); // محاذاة المركز
cell.setTextVerticalType(TextVerticalType.Vertical270);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**ملحوظة:** يستخدم `setTextVerticalType()` لمحاذاة النص عموديا.

### حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    // كود للتعامل مع الجداول
    
    // حفظ العرض التقديمي كملف PPTX
    presentation.save("ModifiedPresentation.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**توضيح:** ال `save()` تكتب الطريقة تغييراتك على القرص بالتنسيق المحدد.

### خاتمة
لقد تعلمتَ الآن كيفية إعداد Aspose.Slides لجافا، وإنشاء الجداول ومعالجتها ضمن شريحة PowerPoint، وتخصيص نص الخلية، ومحاذاة النص عموديًا، وحفظ عرضك التقديمي. بإتقان هذه المهارات، يمكنك تحسين عروضك التقديمية بجداول ديناميكية غنية بالبيانات بسهولة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
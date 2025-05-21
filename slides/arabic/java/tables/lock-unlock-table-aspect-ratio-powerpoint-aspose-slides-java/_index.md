---
"date": "2025-04-18"
"description": "تعرّف على كيفية تثبيت أو إلغاء تثبيت نسب أبعاد الجداول في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. يغطي هذا الدليل الإعداد، وتنفيذ التعليمات البرمجية، والتطبيقات العملية."
"title": "كيفية قفل وإلغاء قفل نسب أبعاد الجدول في PowerPoint باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/tables/lock-unlock-table-aspect-ratio-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية قفل وإلغاء قفل نسب أبعاد الجدول في PowerPoint باستخدام Aspose.Slides لـ Java

## مقدمة

هل تواجه صعوبة في الحفاظ على تناسق تخطيطات الجداول في عروض PowerPoint التقديمية؟ بفضل إمكانية تثبيت أو إلغاء تثبيت نسب العرض إلى الارتفاع، أصبح التحكم في حجم الجداول أثناء التحرير سهلاً للغاية. يرشدك هذا البرنامج التعليمي إلى كيفية استخدام "Aspose.Slides for Java" للتحكم في أبعاد الجداول بكفاءة. ستتعلم كيفية التحكم في نسب العرض إلى الارتفاع، بالإضافة إلى كيفية دمج هذه الميزة في سير عمل العروض التقديمية الأوسع.

**ما سوف تتعلمه:**
- كيفية قفل وفتح نسبة العرض إلى الارتفاع للجداول في عروض PowerPoint.
- عملية إعداد Aspose.Slides لـ Java باستخدام Maven أو Gradle أو التنزيلات المباشرة.
- تنفيذ الكود خطوة بخطوة مع تفسيرات واضحة.
- التطبيقات العملية واعتبارات الأداء عند العمل مع عروض الشرائح الكبيرة.

دعونا نلقي نظرة على المتطلبات الأساسية قبل أن نبدأ.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:
- **مجموعة تطوير Java (JDK):** تم تثبيت الإصدار 16 أو الإصدار الأحدث على جهازك.
- **بيئة التطوير المتكاملة:** أي Java IDE مثل IntelliJ IDEA أو Eclipse.
- **Maven/Gradle:** إذا اخترت استخدام مديري الحزم للتبعيات.
- فهم أساسي لبرمجة Java والمعرفة بوظائف الجدول في PowerPoint.

## إعداد Aspose.Slides لـ Java

### إعداد Maven
لتضمين Aspose.Slides في مشروعك باستخدام Maven، أضف التبعية التالية:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### إعداد Gradle
بالنسبة لأولئك الذين يستخدمون Gradle، قم بتضمين هذا في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، قم بتنزيل الإصدار الأحدث من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية:** ابدأ بإصدار تجريبي مجاني لاستكشاف الوظائف الأساسية.
- **رخصة مؤقتة:** احصل على ترخيص مؤقت للوصول إلى الميزات الكاملة أثناء التقييم.
- **رخصة الشراء:** فكر في شراء ترخيص للاستخدام طويل الأمد دون انقطاع.

بعد إعداد بيئتك والحصول على التراخيص اللازمة، قم بتهيئة Aspose.Slides في تطبيق Java الخاص بك على النحو التالي:

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        // الكود الخاص بك هنا...
    }
}
```

## دليل التنفيذ

### قفل/فتح نسبة عرض الجدول

تتيح لك هذه الميزة الحفاظ على نسبة العرض إلى الارتفاع للجداول في عروضك التقديمية أو تعديلها، مما يضمن التصميم المتسق وقابلية القراءة.

#### الوصول إلى جدول
ابدأ بتحميل العرض التقديمي الخاص بك والوصول إلى الجدول المطلوب:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ITable;

// تحميل ملف العرض التقديمي.
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/pres.pptx");
ITable table = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

#### التحقق من نسبة العرض إلى الارتفاع وتعديلها

تحقق مما إذا كانت نسبة العرض إلى الارتفاع مقفلة، ثم قم بتبديل حالتها:

```java
// التحقق من حالة قفل نسبة العرض إلى الارتفاع الحالية.
boolean isLocked = table.getGraphicalObjectLock().getAspectRatioLocked();

// عكس حالة قفل نسبة العرض إلى الارتفاع.
table.getGraphicalObjectLock().setAspectRatioLocked(!isLocked);
```

تتيح لك ميزة التبديل هذه إجراء تعديلات مرنة أثناء عملية التصميم.

#### حفظ التغييرات
بعد إجراء التغييرات، احفظ العرض التقديمي المحدث:

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/pres-out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
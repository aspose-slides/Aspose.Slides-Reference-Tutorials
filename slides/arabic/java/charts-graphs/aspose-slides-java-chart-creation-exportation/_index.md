---
"date": "2025-04-17"
"description": "تعلم كيفية إنشاء وتصدير المخططات البيانية باستخدام Aspose.Slides في جافا. أتقن تقنيات تصور البيانات من خلال أدلة خطوة بخطوة وأمثلة برمجية."
"title": "Aspose.Slides Java - إنشاء وتصدير المخططات البيانية لتصور البيانات"
"url": "/ar/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء وتصدير المخططات البيانية باستخدام Aspose.Slides Java

**تقنيات تصور البيانات الرئيسية باستخدام Aspose.Slides لـ Java**

في عالم اليوم الذي يعتمد على البيانات، يُعدّ التصور الفعّال للبيانات أمرًا أساسيًا لاتخاذ قرارات مدروسة. يُمكن لدمج وظائف المخططات البيانية في تطبيقات جافا تحويل البيانات الخام إلى قصص بصرية جذابة. سيرشدك هذا البرنامج التعليمي إلى كيفية إنشاء المخططات البيانية وتصديرها باستخدام Aspose.Slides لجافا، مما يضمن أن تكون عروضك التقديمية غنية بالمعلومات وجذابة بصريًا.

**ما سوف تتعلمه:**
- تحميل ملفات العرض التقديمي ومعالجتها بسهولة
- أضف أنواعًا مختلفة من المخططات إلى شرائحك
- تصدير بيانات الرسم البياني إلى مصنفات خارجية بسلاسة
- تعيين مسار مصنف خارجي لإدارة البيانات بكفاءة

دعونا نبدأ!

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك الإعداد التالي جاهزًا:

### المكتبات والإصدارات المطلوبة
- **Aspose.Slides لـ Java** الإصدار 25.4 أو أحدث

### متطلبات إعداد البيئة
- مجموعة تطوير Java (JDK) 16 أو أعلى
- محرر أكواد أو بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse

### متطلبات المعرفة
- فهم أساسي لبرمجة جافا
- المعرفة بأنظمة بناء Maven أو Gradle

## إعداد Aspose.Slides لـ Java
لبدء استخدام Aspose.Slides، عليك تضمينه في مشروعك. إليك الطريقة:

**مافن**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**جرادل**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلا من ذلك، يمكنك [تنزيل أحدث إصدار مباشرة](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
يقدم Aspose.Slides نسخة تجريبية مجانية لاستكشاف كامل إمكانياته. يمكنك أيضًا التقدم بطلب للحصول على ترخيص مؤقت أو شراء ترخيص للاستخدام الممتد. اتبع الخطوات التالية:
1. قم بزيارة [صفحة شراء Aspose](https://purchase.aspose.com/buy) للحصول على رخصتك.
2. للحصول على نسخة تجريبية مجانية، قم بالتنزيل من [الإصدارات](https://releases.aspose.com/slides/java/).
3. التقدم بطلب للحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

بمجرد حصولك على ملف الترخيص، قم بتهيئته في تطبيق Java الخاص بك:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## دليل التنفيذ
### الميزة 1: تحميل العرض التقديمي
يعد تحميل العرض التقديمي هو الخطوة الأولى لأي مهمة معالجة.

#### ملخص
توضح هذه الميزة كيفية تحميل ملف PowerPoint موجود باستخدام Aspose.Slides لـ Java.

#### التنفيذ خطوة بخطوة
**إضافة مخطط إلى الشريحة**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // تعيين المسار إلى دليل المستند الخاص بك
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // تحميل عرض تقديمي موجود
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // تنظيف الموارد
        if (pres != null) pres.dispose();
    }
}
```
**توضيح:**
- `Presentation` يتم تهيئة المسار الخاص بك باستخدام `.pptx` ملف.
- تخلص دائما من `Presentation` الاعتراض على الموارد المجانية.

### الميزة 2: إضافة مخطط إلى الشريحة
إن إضافة مخطط قد يؤدي إلى تحسين عرض البيانات بشكل كبير.

#### ملخص
تُظهر هذه الميزة كيفية إضافة مخطط دائري إلى الشريحة الأولى من العرض التقديمي.

#### التنفيذ خطوة بخطوة
**إضافة مخطط إلى الشريحة**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // تعيين المسار إلى دليل المستند الخاص بك
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // أضف مخططًا دائريًا في الموضع (50، 50) بعرض 400 وارتفاع 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**توضيح:**
- `addChart` يتم استخدام الطريقة لإدراج مخطط دائري.
- تتضمن المعلمات نوع الرسم البياني وموضعه/حجمه على الشريحة.

### الميزة 3: تصدير بيانات الرسم البياني إلى مصنف خارجي
يسمح تصدير البيانات بإجراء تحليلات إضافية خارج PowerPoint.

#### ملخص
تُظهر هذه الميزة كيفية تصدير بيانات الرسم البياني من عرض تقديمي إلى مصنف Excel خارجي.

#### التنفيذ خطوة بخطوة
**تصدير البيانات**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // تعيين المسار إلى دليل المستند ودليل الإخراج
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // الوصول إلى مخطط الشريحة الأولى
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // تحديد المسار للمصنف الخارجي
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // تصدير بيانات الرسم البياني إلى تدفق Excel
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**توضيح:**
- `readWorkbookStream` يستخرج بيانات الرسم البياني.
- تتم كتابة البيانات إلى ملف Excel باستخدام `FileOutputStream`.

### الميزة 4: تعيين مصنف خارجي لبيانات الرسم البياني
قد يؤدي ربط المخططات بدفتر عمل خارجي إلى تبسيط إدارة البيانات.

#### ملخص
توضح هذه الميزة إعداد مسار مصنف خارجي لتخزين بيانات الرسم البياني.

#### التنفيذ خطوة بخطوة
**تعيين مسار المصنف الخارجي**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // تعيين المسار إلى دليل المستند الخاص بك
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // الوصول إلى مخطط الشريحة الأولى
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // تحديد وتعيين المسار للمصنف الخارجي
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**توضيح:**
- `setExternalWorkbook` يربط الرسم البياني بملف Excel، مما يسمح بتحديثات البيانات الديناميكية.

## التطبيقات العملية
يوفر Aspose.Slides حلولاً متعددة الاستخدامات لمختلف السيناريوهات:

1. **التقارير التجارية:** إنشاء تقارير مفصلة باستخدام الرسوم البيانية مباشرة من تطبيقات Java.
2. **العروض الأكاديمية:** قم بتعزيز المحتوى التعليمي باستخدام المخططات التفاعلية.
3. **التحليل المالي:** تصدير البيانات المالية إلى Excel لإجراء تحليل متعمق.
4. **تحليلات التسويق:** تصور أداء الحملة باستخدام المخططات الديناميكية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
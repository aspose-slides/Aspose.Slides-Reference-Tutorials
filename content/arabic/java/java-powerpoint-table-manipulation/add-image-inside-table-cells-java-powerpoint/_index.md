---
title: إضافة صورة داخل خلايا الجدول في Java PowerPoint
linktitle: إضافة صورة داخل خلايا الجدول في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة صور داخل خلايا الجدول في عروض Java PowerPoint التقديمية باستخدام هذا الدليل المفصل خطوة بخطوة باستخدام Aspose.Slides for Java.
type: docs
weight: 10
url: /ar/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---
## مقدمة
إذا كنت تتطلع إلى تحسين عروض Java PowerPoint التقديمية الخاصة بك عن طريق تضمين الصور داخل خلايا الجدول، فقد وصلت إلى المكان الصحيح! اليوم، سنتعمق في دليل تفصيلي خطوة بخطوة باستخدام Aspose.Slides لـ Java. سيرشدك هذا البرنامج التعليمي خلال العملية بأكملها، مما يضمن أنه حتى المبتدئ يمكنه المتابعة وتحقيق نتائج مذهلة.
## المتطلبات الأساسية
قبل أن نبدأ، دعونا نتأكد من أن لديك كل ما تحتاجه:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides لـ Java: قم بتنزيل مكتبة Aspose.Slides من[موقع إلكتروني](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): نوصي باستخدام IntelliJ IDEA أو Eclipse لتطوير Java.
4. ملف الصورة: قم بإعداد ملف صورة ترغب في تضمينه في خلايا جدول PowerPoint.
الآن بعد أن حصلت على كافة المتطلبات الأساسية، دعنا ننتقل إلى استيراد الحزم الضرورية وكتابة الكود.
## حزم الاستيراد
أولاً، قم باستيراد الحزم المطلوبة إلى مشروع Java الخاص بك. ستسمح لك هذه الحزم بالاستفادة من الوظائف التي يوفرها Aspose.Slides ومعالجة الصور في Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
دعونا نقسم المثال إلى خطوات متعددة لتسهيل متابعته.
## الخطوة 1: إعداد العرض التقديمي
ابدأ بإعداد كائن العرض التقديمي والوصول إلى الشريحة الأولى.
```java
// حدد المسار إلى دليل المستندات الخاص بك
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن فئة العرض التقديمي
Presentation presentation = new Presentation();
```
يقوم مقتطف التعليمات البرمجية هذا بتهيئة عرض تقديمي جديد لـ PowerPoint وإعداده لإجراء المزيد من التعديلات.
## الخطوة 2: الوصول إلى الشريحة الأولى
بعد ذلك، قم بالوصول إلى الشريحة الأولى من العرض التقديمي. ستكون هذه الشريحة هي اللوحة القماشية التي سنضيف فيها الجدول.
```java
try {
    // الوصول إلى الشريحة الأولى
    ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: تحديد أبعاد الجدول
تحديد عرض الأعمدة وارتفاع الصفوف للجدول. هذه الخطوة ضرورية للتأكد من أن خلايا الجدول الخاص بك لها الأبعاد الصحيحة.
```java
    // حدد الأعمدة بالعرض والصفوف بالارتفاع
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## الخطوة 4: إضافة جدول إلى الشريحة
أضف شكل الجدول إلى الشريحة باستخدام الأبعاد المحددة.
```java
    // إضافة شكل الجدول إلى الشريحة
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## الخطوة 5: تحميل الصورة
قم بتحميل الصورة التي تريد تضمينها في خلية الجدول. تأكد من توفر ملف الصورة في الدليل المحدد.
```java
    // قم بإنشاء كائن BufferedImage للاحتفاظ بملف الصورة
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // قم بإنشاء كائن IPPImage باستخدام كائن الصورة النقطية
    IPPImage imgx = presentation.getImages().addImage(image);
```
## الخطوة 6: إضافة صورة إلى خلية الجدول
حان الوقت الآن لإضافة الصورة إلى الخلية الأولى في الجدول. تكوين تنسيق التعبئة وتعيين خصائص الصورة.
```java
    // إضافة صورة إلى خلية الجدول الأول
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## الخطوة 7: ضبط اقتصاص الصورة
اضبط اقتصاص الصورة لتتناسب تمامًا مع الخلية إذا لزم الأمر. تضمن هذه الخطوة أن تبدو صورتك صحيحة تمامًا.
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## الخطوة 8: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في الدليل الذي تريده.
```java
    // احفظ PPTX على القرص
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
ها هو ذا! باتباع هذه الخطوات، يمكنك بنجاح إضافة الصور داخل خلايا الجدول في عرض تقديمي لـ Java PowerPoint باستخدام Aspose.Slides. يغطي هذا الدليل كل شيء بدءًا من إعداد بيئتك وحتى حفظ العرض التقديمي النهائي. آمل أن يساعدك هذا البرنامج التعليمي في إنشاء عروض تقديمية أكثر جاذبية من الناحية المرئية.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها في تطبيقات Java.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
 نعم يمكنك الحصول على[تجربة مجانية](https://releases.aspose.com/) لتجربة Aspose.Slides قبل الشراء.
### هل يمكنني استخدام أي تنسيق صورة مع Aspose.Slides؟
يدعم Aspose.Slides تنسيقات الصور المختلفة بما في ذلك JPEG وPNG وBMP والمزيد.
### أين يمكنني العثور على وثائق أكثر تفصيلا؟
 يمكنك الرجوع إلى[توثيق](https://reference.aspose.com/slides/java/) للحصول على معلومات وأمثلة أكثر تفصيلا.
### كيف يمكنني شراء Aspose.Slides لجافا؟
 يمكنك شرائه من[موقع أسبوز](https://purchase.aspose.com/buy).
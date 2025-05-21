---
"description": "تعرف على كيفية إضافة الصور داخل خلايا الجدول في عروض PowerPoint التقديمية بلغة Java باستخدام هذا الدليل التفصيلي خطوة بخطوة باستخدام Aspose.Slides لـ Java."
"linktitle": "إضافة صورة داخل خلايا الجدول في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة صورة داخل خلايا الجدول في Java PowerPoint"
"url": "/ar/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة صورة داخل خلايا الجدول في Java PowerPoint

## مقدمة
إذا كنت ترغب في تحسين عروض PowerPoint التقديمية بلغة جافا من خلال تضمين الصور في خلايا الجدول، فأنت في المكان المناسب! سنتناول اليوم دليلًا مفصلاً خطوة بخطوة لاستخدام Aspose.Slides في جافا. سيشرح هذا البرنامج التعليمي العملية كاملةً، مما يضمن متابعة حتى المبتدئين وتحقيق نتائج مبهرة.
## المتطلبات الأساسية
قبل أن نبدأ، دعونا نتأكد من أن لديك كل ما تحتاجه:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل مكتبة Aspose.Slides من [موقع إلكتروني](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): نوصي باستخدام IntelliJ IDEA أو Eclipse لتطوير Java.
4. ملف الصورة: قم بإعداد ملف صورة ترغب في تضمينه داخل خلايا جدول PowerPoint.
الآن بعد أن أصبحت لديك كل المتطلبات الأساسية، دعنا ننتقل إلى استيراد الحزم الضرورية وكتابة الكود.
## استيراد الحزم
أولاً، استورد الحزم المطلوبة إلى مشروع جافا. ستتيح لك هذه الحزم الاستفادة من وظائف Aspose.Slides ومعالجة الصور في جافا.
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
// إنشاء كائن فئة العرض التقديمي
Presentation presentation = new Presentation();
```
يقوم مقتطف التعليمات البرمجية هذا بتهيئة عرض تقديمي جديد في PowerPoint وإعداده لمزيد من التعديلات.
## الخطوة 2: الوصول إلى الشريحة الأولى
بعد ذلك، انتقل إلى الشريحة الأولى من العرض التقديمي. ستكون هذه الشريحة بمثابة اللوحة التي سنضيف إليها الجدول.
```java
try {
    // الوصول إلى الشريحة الأولى
    ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: تحديد أبعاد الجدول
حدّد عرض أعمدة الجدول وارتفاع صفوفه. هذه الخطوة أساسية لضمان الأبعاد الصحيحة لخلايا الجدول.
```java
    // تحديد الأعمدة بالعرض والصفوف بالارتفاع
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
حمّل الصورة التي تريد تضمينها في خلية الجدول. تأكد من توفر ملف الصورة في الدليل المحدد.
```java
    // إنشاء كائن BufferedImage لحمل ملف الصورة
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // إنشاء كائن IPPImage باستخدام كائن الخريطة النقطية
    IPPImage imgx = presentation.getImages().addImage(image);
```
## الخطوة 6: إضافة صورة إلى خلية الجدول
الآن، حان وقت إضافة الصورة إلى الخلية الأولى من الجدول. جهّز تنسيق التعبئة وخصائص الصورة.
```java
    // إضافة صورة إلى الخلية الأولى في الجدول
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## الخطوة 7: ضبط اقتصاص الصورة
اضبط اقتصاص الصورة لتتناسب تمامًا مع الخلية إذا لزم الأمر. تضمن هذه الخطوة أن تبدو صورتك مثالية.
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## الخطوة 8: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل في الدليل المطلوب.
```java
    // حفظ PPTX على القرص
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
هذا كل ما في الأمر! باتباع هذه الخطوات، يمكنك بنجاح إضافة صور داخل خلايا الجدول في عرض تقديمي جافا باوربوينت باستخدام Aspose.Slides. غطى هذا الدليل كل شيء، من إعداد بيئة العرض التقديمي إلى حفظه. آمل أن يساعدك هذا البرنامج التعليمي في إنشاء عروض تقديمية أكثر جاذبية بصريًا.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء وتعديل وإدارة عروض PowerPoint في تطبيقات Java.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
نعم يمكنك الحصول على [نسخة تجريبية مجانية](https://releases.aspose.com/) لتجربة Aspose.Slides قبل الشراء.
### هل يمكنني استخدام أي تنسيق للصورة مع Aspose.Slides؟
يدعم Aspose.Slides تنسيقات الصور المختلفة بما في ذلك JPEG وPNG وBMP والمزيد.
### أين يمكنني العثور على المزيد من الوثائق التفصيلية؟
يمكنك الرجوع إلى [التوثيق](https://reference.aspose.com/slides/java/) لمزيد من المعلومات والأمثلة التفصيلية.
### كيف يمكنني شراء Aspose.Slides لـ Java؟
يمكنك شرائه من [موقع Aspose](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
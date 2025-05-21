---
"description": "تعلّم كيفية تقسيم ودمج وتنسيق خلايا جدول PowerPoint برمجيًا باستخدام Aspose.Slides لجافا. أتقن تصميم العرض التقديمي."
"linktitle": "تقسيم الخلايا في جدول PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تقسيم الخلايا في جدول PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تقسيم الخلايا في جدول PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية التعامل مع جداول PowerPoint بلغة Java باستخدام Aspose.Slides. تُعد الجداول عنصرًا أساسيًا في العروض التقديمية، وغالبًا ما تُستخدم لتنظيم البيانات وعرضها بفعالية. يوفر Aspose.Slides إمكانيات قوية لإنشاء الجداول وتعديلها وتحسينها برمجيًا، مما يوفر مرونة في التصميم والتخطيط.
## المتطلبات الأساسية
قبل أن تبدأ هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على جهازك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA أو أي بيئة أخرى من اختيارك.

## استيراد الحزم
لبدء العمل مع Aspose.Slides لـ Java، تحتاج إلى استيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إعداد العرض التقديمي
أولاً، قم بإنشاء مثيل `Presentation` فئة لإنشاء عرض تقديمي جديد في PowerPoint.
```java
// المسار إلى الدليل الذي تريد حفظ العرض التقديمي الناتج فيه
String dataDir = "Your_Document_Directory/";
// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation presentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة وإضافة جدول
انتقل إلى الشريحة الأولى وأضف إليها شكل جدول. حدّد عرض الأعمدة وارتفاع الصفوف.
```java
try {
    // الوصول إلى الشريحة الأولى
    ISlide slide = presentation.getSlides().get_Item(0);
    // تحديد الأعمدة بالعرض والصفوف بالارتفاع
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // إضافة شكل الجدول إلى الشريحة
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## الخطوة 3: تعيين تنسيق الحدود لكل خلية
قم بالتكرار خلال كل خلية في الجدول وتعيين تنسيق الحدود (اللون والعرض وما إلى ذلك).
```java
    // تعيين تنسيق الحدود لكل خلية
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // تعيين تنسيق مماثل للحدود الأخرى (أسفل، يسار، يمين)
            // ...
        }
    }
```
## الخطوة 4: دمج الخلايا
ادمج خلايا الجدول حسب الحاجة. على سبيل المثال، ادمج الخلايا (1،1) مع (2،1) والخلايا (1،2) مع (2،2).
```java
    // دمج الخلايا (1، 1) × (2، 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // دمج الخلايا (1، 2) × (2، 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## الخطوة 5: تقسيم الخلايا
تقسيم خلية محددة إلى خلايا متعددة استنادًا إلى العرض.
```java
    // خلية منقسمة (1، 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل على القرص.
```java
    // كتابة PPTX على القرص
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // التخلص من كائن العرض التقديمي
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
يُتيح لك التعامل مع جداول PowerPoint برمجيًا باستخدام Aspose.Slides for Java طريقة فعّالة لتخصيص العروض التقديمية بكفاءة. باتباع هذا البرنامج التعليمي، ستتعلم كيفية تقسيم الخلايا ودمجها وتعيين حدودها ديناميكيًا، مما يُحسّن قدرتك على إنشاء عروض تقديمية جذابة بصريًا برمجيًا.

## الأسئلة الشائعة
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني تنزيل Aspose.Slides لـ Java؟
يمكنك تنزيله من [هذا الرابط](https://releases.aspose.com/slides/java/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم من منتدى Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
نعم يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
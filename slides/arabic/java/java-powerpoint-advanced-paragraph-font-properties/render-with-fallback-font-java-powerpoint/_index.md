---
"description": "تعرّف على كيفية عرض النصوص باستخدام الخطوط البديلة في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides. اتبع هذا الدليل خطوة بخطوة لتنفيذ سلس."
"linktitle": "العرض باستخدام الخط البديل في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "العرض باستخدام الخط البديل في Java PowerPoint"
"url": "/ar/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# العرض باستخدام الخط البديل في Java PowerPoint

## مقدمة
قد يكون إنشاء عروض PowerPoint التقديمية ومعالجتها باستخدام Java أمرًا صعبًا، ولكن مع Aspose.Slides، يمكنك القيام بذلك بكفاءة. من أهم ميزاته إمكانية عرض النص باستخدام الخطوط البديلة. تقدم هذه المقالة دليلًا مفصلاً خطوة بخطوة حول كيفية استخدام الخطوط البديلة في شرائح PowerPoint باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل الخوض في التنفيذ، دعنا نتأكد من أن لديك كل ما تحتاجه:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
2. Aspose.Slides لـ Java: يمكنك تنزيله من [صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): ستعمل بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse على جعل عملية التطوير الخاصة بك أكثر سلاسة.
4. التبعيات: قم بتضمين Aspose.Slides في تبعيات مشروعك.
## استيراد الحزم
أولاً، نحتاج إلى استيراد الحزم اللازمة في برنامج Java الخاص بنا.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
دعونا نقسم العملية إلى خطوات قابلة للإدارة.
## الخطوة 1: إعداد مشروعك
قبل كتابة أي شيفرة برمجية، تأكد من إعداد مشروعك بشكل صحيح. يتضمن ذلك إضافة مكتبة Aspose.Slides إلى مشروعك. يمكنك القيام بذلك بتنزيل المكتبة من [Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/) وإضافته إلى مسار البناء الخاص بك.
## الخطوة 2: تهيئة قواعد الرجوع إلى الخط
يجب عليك إنشاء مثيل لـ `IFontFallBackRulesCollection` أضف قواعد إلى الفئة. تُحدد هذه القواعد خيارات الخطوط البديلة لنطاقات Unicode محددة.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل جديد لمجموعة القواعد
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// إنشاء عدد من القواعد
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## الخطوة 3: تعديل قواعد الرجوع
في هذه الخطوة، سنقوم بتعديل قواعد الرجوع إلى الوضع السابق عن طريق إزالة الخطوط الرجوع إلى الوضع السابق الموجودة وتحديث القواعد الخاصة بنطاقات Unicode المحددة.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // محاولة إزالة الخط FallBack "Tahoma" من القواعد المحملة
    fallBackRule.remove("Tahoma");
    // تحديث القواعد للنطاق المحدد
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// إزالة أي قواعد موجودة من القائمة
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## الخطوة 4: تحميل العرض التقديمي
قم بتحميل عرض PowerPoint الذي تريد تعديله.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## الخطوة 5: تعيين قواعد احتياطية للعرض التقديمي
تعيين قواعد احتياطية مُجهزة لمدير الخطوط الخاص بالعرض التقديمي.
```java
try {
    // تعيين قائمة القواعد المعدة للاستخدام
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // عرض صورة مصغرة باستخدام مجموعة القواعد المبدئية وحفظها بتنسيق PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## الخطوة 6: الحفظ والاختبار
أخيرًا، احفظ عملك واختبر التنفيذ للتأكد من أن كل شيء يعمل كما هو متوقع. إذا واجهت أي مشاكل، فتحقق جيدًا من إعداداتك وتأكد من إضافة جميع التبعيات بشكل صحيح.
## خاتمة
باتباع هذا الدليل، يمكنك عرض النصوص بكفاءة باستخدام الخطوط البديلة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تضمن هذه العملية تناسق تنسيق عروضك التقديمية، حتى في حال عدم توفر الخطوط الأساسية. برمجة ممتعة!
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة تسمح للمطورين بإنشاء وتعديل وعرض عروض PowerPoint في تطبيقات Java.
### كيف أضيف Aspose.Slides إلى مشروعي؟
يمكنك تنزيل المكتبة من [صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/) وأضفه إلى مسار بناء مشروعك.
### ما هي الخطوط البديلة؟
الخطوط الاحتياطية هي خطوط بديلة يتم استخدامها عندما لا يتوفر الخط المحدد أو لا يدعم أحرفًا معينة.
### هل يمكنني استخدام قواعد احتياطية متعددة؟
نعم، يمكنك إضافة قواعد احتياطية متعددة للتعامل مع نطاقات وخطوط Unicode المختلفة.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
يمكنك الحصول على الدعم من [منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
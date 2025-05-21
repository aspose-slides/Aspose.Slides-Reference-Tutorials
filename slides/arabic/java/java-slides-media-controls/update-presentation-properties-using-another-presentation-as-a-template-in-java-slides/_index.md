---
"description": "حسّن عروض PowerPoint التقديمية ببيانات تعريفية مُحدّثة باستخدام Aspose.Slides لجافا. تعلّم كيفية تحديث خصائص مثل المؤلف والعنوان والكلمات المفتاحية باستخدام القوالب في شرائح جافا."
"linktitle": "تحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java"
"url": "/ar/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java


## مقدمة لتحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java

في هذا البرنامج التعليمي، سنشرح لك عملية تحديث خصائص العرض التقديمي (البيانات الوصفية) لعروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. يمكنك استخدام عرض تقديمي آخر كقالب لتحديث خصائص مثل المؤلف والعنوان والكلمات المفتاحية وغيرها. سنزودك بإرشادات خطوة بخطوة وأمثلة على الكود المصدري.

## المتطلبات الأساسية

قبل البدء، تأكد من دمج مكتبة Aspose.Slides لجافا في مشروع جافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد مشروعك

تأكد من أنك قمت بإنشاء مشروع Java وأضفت مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.

## الخطوة 2: استيراد الحزم المطلوبة

ستحتاج إلى استيراد حزم Aspose.Slides اللازمة للعمل مع خصائص العرض التقديمي. أدرج عبارات الاستيراد التالية في بداية فئة جافا:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## الخطوة 3: تحديث خصائص العرض التقديمي

الآن، لنُحدِّث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب. في هذا المثال، سنُحدِّث خصائص عروض تقديمية متعددة، ولكن يُمكنك تعديل هذا الكود ليناسب حالة استخدامك الخاصة.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// قم بتحميل قالب العرض التقديمي الذي تريد نسخ خصائصه
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// قم بتعيين الخصائص التي تريد تحديثها
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// تحديث عروض تقديمية متعددة باستخدام نفس القالب
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

## الخطوة 4: تحديد `updateByTemplate` طريقة

لنُعرّف طريقةً لتحديث خصائص العروض التقديمية الفردية باستخدام القالب. ستأخذ هذه الطريقة مسار العرض التقديمي المراد تحديثه وخصائص القالب كمعلمات.

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // تحميل العرض التقديمي المراد تحديثه
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // تحديث خصائص المستند باستخدام القالب
    toUpdate.updateDocumentProperties(template);
    
    // حفظ العرض التقديمي المحدث
    toUpdate.writeBindedPresentation(path);
}
```

## كود المصدر الكامل لتحديث خصائص العرض التقديمي باستخدام عرض تقديمي آخر كقالب في شرائح Java

```java
	// المسار إلى دليل المستندات.
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## خاتمة

في هذا البرنامج التعليمي الشامل، استكشفنا كيفية تحديث خصائص العرض التقديمي في عروض PowerPoint باستخدام Aspose.Slides لجافا. ركزنا تحديدًا على استخدام عرض تقديمي آخر كقالب لتحديث البيانات الوصفية بكفاءة، مثل أسماء المؤلفين والعناوين والكلمات المفتاحية وغيرها.

## الأسئلة الشائعة

### كيف يمكنني تحديث الخصائص لمزيد من العروض التقديمية؟

يمكنك تحديث خصائص العروض التقديمية المتعددة عن طريق استدعاء `updateByTemplate` طريقة لكل عرض مع المسار المطلوب.

### هل يمكنني تخصيص هذا الكود لخصائص مختلفة؟

نعم، يمكنك تخصيص الكود لتحديث خصائص محددة بناءً على متطلباتك. ما عليك سوى تعديل `template` الكائن مع قيم الخصائص المطلوبة.

### هل هناك أي قيود على نوع العروض التقديمية التي يمكن تحديثها؟

لا، يمكنك تحديث خصائص العروض التقديمية بتنسيقات مختلفة، بما في ذلك PPTX وODP وPPT.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
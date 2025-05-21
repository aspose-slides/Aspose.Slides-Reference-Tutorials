---
"date": "2025-04-23"
"description": "تعرف على كيفية إنشاء رسومات SmartArt وتخصيصها في PowerPoint باستخدام Aspose.Slides for Python، مما يعزز عروضك التقديمية باستخدام مخططات تنظيمية ديناميكية."
"title": "كيفية إنشاء وتخصيص SmartArt في PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء وتخصيص SmartArt في PowerPoint باستخدام Aspose.Slides لـ Python

## مقدمة

العروض التقديمية أداة أساسية لعرض الهياكل التنظيمية بصريًا أو لجلسات العصف الذهني. باستخدام Aspose.Slides لـ Python، يمكنك إنشاء رسومات SmartArt وتخصيصها بسهولة. سيرشدك هذا البرنامج التعليمي إلى كيفية إضافة رسم SmartArt لمخطط تنظيمي إلى شرائح PowerPoint.

**ما سوف تتعلمه:**
- إضافة رسم SmartArt في PowerPoint باستخدام Aspose.Slides لـ Python.
- تخصيص تخطيط عقدة SmartArt الخاصة بك.
- حفظ العروض التقديمية وتصديرها بكفاءة.

لنبدأ بإعداد بيئتك!

## المتطلبات الأساسية

قبل البدء في إنشاء رسومات SmartArt، تأكد من توفر المتطلبات الأساسية التالية لديك:

### المكتبات المطلوبة
- **Aspose.Slides لـ Python**:قم بتثبيت هذه المكتبة باستخدام pip إذا لم تقم بذلك بالفعل.

### متطلبات إعداد البيئة
- تثبيت عمل لـ Python (يوصى بـ 3.x).
- فهم أساسي لبرمجة بايثون.
- إن المعرفة ببرنامج Microsoft PowerPoint مفيدة ولكنها ليست ضرورية.

## إعداد Aspose.Slides لـ Python

للبدء، قم بإعداد مكتبة Aspose.Slides في بيئة Python الخاصة بك:

**تركيب Pip:**
```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص
توفر Aspose خيارات ترخيص مختلفة:
- **نسخة تجريبية مجانية**:قم بتنزيل ترخيص مؤقت لتقييم الميزات الكاملة.
- **رخصة مؤقتة**:احصل على ترخيص مؤقت مجاني للاستخدام قصير المدى.
- **شراء**:فكر في شراء اشتراك للمشاريع طويلة الأمد.

### التهيئة والإعداد الأساسي

بمجرد التثبيت، قم بتهيئة البرنامج النصي Python الخاص بك باستخدام Aspose.Slides مثل هذا:

```python
import aspose.slides as slides

# قم بتهيئة فئة العرض التقديمي باستخدام slides.Presentation() كعرض تقديمي:
    # سيتم وضع الكود الخاص بك لإضافة SmartArt هنا
```

## دليل التنفيذ

الآن دعنا نستعرض عملية إضافة SmartArt وتخصيصه في PowerPoint باستخدام Aspose.Slides لـ Python.

### إضافة رسم SmartArt

#### ملخص
قم بإنشاء شريحة جديدة وأضف إليها رسمًا بيانيًا من نوع SmartArt للمخطط التنظيمي:

```python
import aspose.slides as slides

# إنشاء مثيل عرض تقديمي مع slides.Presentation() كعرض تقديمي:
    # أضف SmartArt بأبعاد محددة في الموضع (10، 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### المعلمات والغرض من الطريقة
- **س، ص**:موضع رسم SmartArt على الشريحة.
- **العرض، الارتفاع**:الأبعاد اللازمة للرؤية الصحيحة.
- **نوع التخطيط**:يحدد نوع تخطيط SmartArt، في هذه الحالة، مخطط تنظيمي.

### تخصيص تخطيط المخطط التنظيمي

#### ملخص
قم بتخصيص العقدة الأولى في رسم SmartArt الخاص بنا عن طريق تعيين تخطيطها إلى LEFT_HANGING:

```python
# تعيين العقدة الأولى إلى تخطيط معلق على اليسار
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### شرح خيارات تكوين المفاتيح
- **نوع تخطيط مخطط المؤسسة**:يحدد كيفية عرض العقد، مما يعزز قابلية القراءة والجاذبية الجمالية.

### حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي الخاص بك في الدليل المحدد:

```python
# احفظ العرض التقديمي باستخدام SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
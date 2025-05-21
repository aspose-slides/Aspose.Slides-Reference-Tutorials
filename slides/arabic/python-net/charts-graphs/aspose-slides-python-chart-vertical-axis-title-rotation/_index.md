---
"date": "2025-04-23"
"description": "تعرف على كيفية ضبط زاوية دوران عناوين المخططات في العروض التقديمية باستخدام Aspose.Slides لـ Python، مما يعزز قابلية القراءة والجماليات."
"title": "كيفية تعيين دوران عنوان المحور الرأسي للرسم البياني في Aspose.Slides لـ Python"
"url": "/ar/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تعيين دوران عنوان المحور الرأسي للرسم البياني في Aspose.Slides لـ Python

## مقدمة

في عروض البيانات، يُعد تحسين قابلية قراءة المخططات أمرًا بالغ الأهمية. يُمكنك ضبط زاوية دوران عنوان المحور الرأسي للمخطط باستخدام Aspose.Slides لـ Python لجعل العناوين تتناسب بشكل أنيق مع شرائحك أو تبرزها. يُرشدك هذا البرنامج التعليمي إلى كيفية ضبط زاوية الدوران هذه لتحسين الأداء والجاذبية البصرية.

**ما سوف تتعلمه:**
- كيفية تثبيت وتكوين Aspose.Slides لـ Python.
- خطوات لإضافة المخططات وتخصيصها داخل الشرائح الخاصة بك.
- تقنيات لضبط زاوية دوران عناوين المخططات البيانية.
- التطبيقات الواقعية لهذه الميزات في تصور البيانات.

دعونا نبدأ بتغطية المتطلبات الأساسية قبل الغوص في التنفيذ.

## المتطلبات الأساسية

قبل البدء، تأكد من أن لديك:
- **بيئة بايثون**:تثبيت Python 3.x من [python.org](https://www.python.org/).
- **مكتبة Aspose.Slides**:قم بالتثبيت عبر pip للتعامل مع العروض التقديمية بشكل فعال.
- **المعرفة الأساسية ببرمجة بايثون**:ستساعدك المعرفة بقواعد اللغة Python وعمليات الملفات على المتابعة.

## إعداد Aspose.Slides لـ Python

لاستخدام Aspose.Slides، ثبّته باستخدام pip. افتح الطرفية أو موجه الأوامر وشغّل:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص

توفر Aspose خيارات ترخيص مختلفة:
- **نسخة تجريبية مجانية**: قم بتنزيل النسخة التجريبية من [صفحة إصدار Aspose](https://releases.aspose.com/slides/python-net/).
- **رخصة مؤقتة**:احصل على ترخيص مؤقت للميزات الموسعة عبر [بوابة الشراء](https://purchase.aspose.com/temporary-license/).
- **شراء**:فكر في الشراء إذا وجدت أن الأداة لا غنى عنها ومتوفرة من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

#### التهيئة والإعداد الأساسي

فيما يلي كيفية تهيئة Aspose.Slides في البرنامج النصي Python الخاص بك:

```python
import aspose.slides as slides

# إنشاء كائن عرض تقديمي
def main():
    with slides.Presentation() as pres:
        # سيتم وضع الكود الخاص بك هنا
        pass

if __name__ == "__main__":
    main()
```

## دليل التنفيذ

### إضافة المخططات وتخصيصها

#### ملخص

في هذا القسم، سنضيف مخططًا عموديًا مجمعًا إلى الشريحة الخاصة بك وسنقوم بتخصيصه عن طريق تعيين زاوية دوران عنوان المحور الرأسي الخاص به.

#### خطوات:

##### الخطوة 1: إضافة مخطط عمودي مجمع

ابدأ بإضافة مخطط عند إحداثيات محددة وبأبعاد محددة:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # إضافة مخطط عمودي مجمع إلى الشريحة 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### الخطوة 2: تكوين عنوان المحور الرأسي

تمكين وتعيين زاوية الدوران لعنوان المحور الرأسي:

```python
def configure_chart(chart):
    # تمكين عنوان المحور الرأسي
    chart.axes.vertical_axis.has_title = True
    
    # ضبط زاوية الدوران إلى 90 درجة
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### الخطوة 3: احفظ العرض التقديمي الخاص بك

وأخيرًا، احفظ العرض التقديمي الخاص بك مع التغييرات:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # حفظ العرض التقديمي
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
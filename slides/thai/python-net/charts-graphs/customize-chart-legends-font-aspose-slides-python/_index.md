---
"date": "2025-04-22"
"description": "เรียนรู้วิธีปรับแต่งคุณสมบัติแบบอักษรของคำอธิบายแผนภูมิโดยใช้ Aspose.Slides สำหรับ Python ปรับปรุงการนำเสนอของคุณด้วยแบบอักษรตัวหนา ตัวเอียง และสีสำหรับรายการคำอธิบายแผนภูมิแต่ละรายการ"
"title": "ปรับแต่งแบบอักษรแผนภูมิตำนานโดยใช้ Aspose.Slides สำหรับ Python และคู่มือฉบับสมบูรณ์"
"url": "/th/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การปรับแต่งแบบอักษรของแผนภูมิตำนานในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ Python

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญ โดยเฉพาะอย่างยิ่งเมื่อต้องแสดงข้อมูลผ่านแผนภูมิ ความท้าทายทั่วไปคือการปรับแต่งคำอธิบายแผนภูมิให้สอดคล้องกับรูปแบบการนำเสนอหรือความต้องการด้านแบรนด์ของคุณ คู่มือนี้จะแสดงวิธีการปรับแต่งคุณสมบัติของแบบอักษร เช่น ความหนา ตัวเอียง ขนาด และสีสำหรับรายการคำอธิบายแต่ละรายการในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Python

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าและการใช้งาน Aspose.Slides สำหรับ Python
- การปรับแต่งคุณสมบัติแบบอักษรของคำอธิบายแผนภูมิ
- การใช้แบบอักษรเฉพาะ เช่น ตัวหนา ตัวเอียง และเปลี่ยนสี
- ตัวอย่างการใช้งานจริงในการปรับปรุงแผนภูมิด้วยแบบอักษรที่กำหนดเอง

มาสำรวจกันว่าคุณสามารถปรับแต่งนี้ได้อย่างไร

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- **ห้องสมุด**: Aspose.Slides สำหรับ Python ติดตั้งโดยใช้ pip
- **สิ่งแวดล้อม**:สภาพแวดล้อม Python (ควรเป็น Python 3.x) ที่ตั้งค่าบนเครื่องของคุณ
- **ความรู้**:ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Python และความคุ้นเคยกับการจัดการการนำเสนอผ่านโปรแกรม

## การตั้งค่า Aspose.Slides สำหรับ Python
### การติดตั้ง
ในการเริ่มต้น ให้ติดตั้งไลบรารี Aspose.Slides โดยรันคำสั่งต่อไปนี้ในเทอร์มินัลของคุณ:

```bash
pip install aspose.slides
```

### การขอใบอนุญาต
Aspose.Slides เป็นผลิตภัณฑ์เชิงพาณิชย์ที่มีตัวเลือกลิขสิทธิ์ต่างๆ:
- **ทดลองใช้งานฟรี**:รับใบอนุญาตชั่วคราวเพื่อใช้งานได้เต็มรูปแบบ
- **ใบอนุญาตชั่วคราว**:สมัครขอใบอนุญาตชั่วคราวเพื่อทดสอบฟีเจอร์ทั้งหมดโดยไม่มีข้อจำกัด
- **ซื้อ**:ซื้อการสมัครสมาชิกหรือใบอนุญาตถาวรตามความต้องการของคุณ

### การเริ่มต้นขั้นพื้นฐาน
นี่คือวิธีการเริ่มต้นและตั้งค่า Aspose.Slides ในสคริปต์ Python ของคุณ:

```python
import aspose.slides as slides

# สร้างอินสแตนซ์การนำเสนอด้วย slides.Presentation() เป็น pres:
    # รหัสของคุณที่นี่
```

## คู่มือการใช้งาน
ในส่วนนี้เราจะแนะนำการปรับแต่งคุณสมบัติแบบอักษรของรายการคำอธิบายแต่ละรายการ

### การเพิ่มและการเข้าถึงแผนภูมิ
ก่อนอื่น มาเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ของคุณ:

```python
# เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ตำแหน่ง (50, 50) โดยมีความกว้าง 600 และความสูง 400
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # นี่เป็นเพียงตัวแทนสำหรับวิธี Aspose.Slides ที่แท้จริง
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# การจำลอง pres.slides[0].shapes
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### การปรับแต่งคุณสมบัติแบบอักษรของตำนาน
#### การเข้าถึงรูปแบบข้อความของรายการตำนาน
ในการปรับเปลี่ยนคุณสมบัติแบบอักษรของรายการคำอธิบายเฉพาะ:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# การจำลองแผนภูมิ.คำอธิบาย.รายการ[1].รูปแบบข้อความ
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### การตั้งค่าคุณสมบัติแบบอักษร
ที่นี่ เราปรับแต่งลักษณะต่างๆ เช่น ความหนา ขนาด ตัวเอียง และสี:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# ตั้งค่าขนาดตัวอักษรเป็น 20 พอยต์
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# ตั้งค่าสีตัวอักษรเป็นสีน้ำเงินโดยใช้ชนิดเติมสีทึบ
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### การบันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอของคุณด้วยการปรับแต่งเหล่านี้:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
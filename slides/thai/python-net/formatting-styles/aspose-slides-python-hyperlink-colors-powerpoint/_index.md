---
"date": "2025-04-23"
"description": "เรียนรู้วิธีปรับแต่งสีไฮเปอร์ลิงก์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Python ปรับปรุงสไลด์ของคุณด้วยรูปแบบลิงก์ที่ปรับแต่งได้อย่างมีประสิทธิภาพ"
"title": "วิธีตั้งค่าสีไฮเปอร์ลิงก์ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python"
"url": "/th/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีตั้งค่าสีไฮเปอร์ลิงก์ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python

## การแนะนำ

การปรับแต่งสีไฮเปอร์ลิงก์ในสไลด์ของคุณจะทำให้การนำเสนอ PowerPoint ของคุณดูน่าสนใจยิ่งขึ้นด้วย Aspose.Slides สำหรับ Python คำแนะนำนี้จะแนะนำคุณเกี่ยวกับการตั้งค่าไฮเปอร์ลิงก์ด้วยสีเฉพาะในสไลด์ของคุณโดยใช้ Python

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่าสีไฮเปอร์ลิงก์ภายในรูปร่างข้อความใน PowerPoint
- ขั้นตอนต่างๆ ที่เกี่ยวข้องในการสร้างงานนำเสนอที่น่าสนใจทางภาพ
- คุณสมบัติหลักของ Aspose.Slides สำหรับ Python ที่ช่วยอำนวยความสะดวกในการปรับแต่งนี้

มาเจาะลึกข้อกำหนดเบื้องต้นที่จำเป็นก่อนที่จะเริ่มต้นกัน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าสภาพแวดล้อมของคุณพร้อมแล้วด้วยสิ่งต่อไปนี้:
- **ไลบรารีและเวอร์ชัน:** ติดตั้ง `aspose.slides` ห้องสมุด ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Python ไว้ในเครื่องของคุณแล้ว
- **ข้อกำหนดการตั้งค่าสภาพแวดล้อม:** บทช่วยสอนนี้ถือว่ามีการตั้งค่า Python ขั้นพื้นฐานบน Windows, Mac หรือ Linux
- **ข้อกำหนดความรู้เบื้องต้น:** ความคุ้นเคยกับการเขียนโปรแกรม Python จะเป็นประโยชน์

## การตั้งค่า Aspose.Slides สำหรับ Python

ในการเริ่มใช้ Aspose.Slides สำหรับ Python ให้ติดตั้งแพ็กเกจผ่าน pip:

```bash
pip install aspose.slides
```

**ขั้นตอนการรับใบอนุญาต:**
- **ทดลองใช้งานฟรี:** ดาวน์โหลดเวอร์ชันทดลองใช้ได้จาก [หน้าการเปิดตัวของ Aspose](https://releases-aspose.com/slides/python-net/).
- **ใบอนุญาตชั่วคราว:** ขอใบอนุญาตชั่วคราวได้ที่ [หน้าการซื้อ](https://purchase.aspose.com/temporary-license/) เพื่อการเข้าถึงแบบขยาย
- **ซื้อ:** หากต้องการปลดล็อคคุณสมบัติต่างๆ ได้อย่างสมบูรณ์โดยไม่มีข้อจำกัด โปรดพิจารณาซื้อใบอนุญาตจาก [หน้าการซื้อของ Aspose](https://purchase-aspose.com/buy).

**การเริ่มต้นขั้นพื้นฐาน:**
เมื่อติดตั้งและได้รับอนุญาตแล้ว ให้ทำการนำเข้า Aspose.Slides ในสคริปต์ของคุณ:

```python
import aspose.slides as slides
```

## คู่มือการใช้งาน

หัวข้อนี้จะแนะนำคุณเกี่ยวกับการตั้งค่าสีไฮเปอร์ลิงก์ภายในงานนำเสนอ PowerPoint

### ตั้งค่าคุณสมบัติสีไฮเปอร์ลิงก์

#### ภาพรวม

ปรับแต่งสีของไฮเปอร์ลิงก์ที่ฝังอยู่ในรูปร่างข้อความโดยใช้ Aspose.Slides สำหรับ Python ซึ่งจะช่วยเพิ่มความสามารถในการอ่านและความสวยงามของภาพ

##### ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

สร้างตัวอย่างของการนำเสนอ:

```python
with slides.Presentation() as presentation:
    # รหัสของคุณที่นี่
```

##### ขั้นตอนที่ 2: เพิ่มรูปร่างด้วยข้อความ

เพิ่มรูปทรงสี่เหลี่ยมผืนผ้าในสไลด์แรกและแทรกข้อความที่มีไฮเปอร์ลิงก์

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติไฮเปอร์ลิงก์

กำหนดไฮเปอร์ลิงก์และตั้งค่าสีของมัน `hyperlink_click` คุณสมบัติระบุว่าลิงก์ควรจะนำทางไปที่ใดเมื่อคลิก

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# ตั้งค่าแหล่งสีสำหรับไฮเปอร์ลิงก์ไปยังรูปแบบส่วน และกำหนดประเภทการเติมและสี
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### ขั้นตอนที่ 4: บันทึกการนำเสนอ

บันทึกการนำเสนอของคุณไปยังไดเร็กทอรีที่ระบุ:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
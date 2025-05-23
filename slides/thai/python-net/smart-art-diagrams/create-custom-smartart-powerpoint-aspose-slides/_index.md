---
"date": "2025-04-23"
"description": "เรียนรู้วิธีการสร้างและปรับแต่งกราฟิก SmartArt ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python เพื่อปรับปรุงการนำเสนอของคุณด้วยแผนผังองค์กรแบบไดนามิก"
"title": "วิธีการสร้างและปรับแต่ง SmartArt ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python"
"url": "/th/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างและปรับแต่ง SmartArt ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python

## การแนะนำ

การนำเสนอเป็นเครื่องมือสำคัญในการนำเสนอโครงสร้างองค์กรหรือการระดมความคิดในรูปแบบภาพ ด้วย Aspose.Slides สำหรับ Python คุณสามารถสร้างและปรับแต่งกราฟิก SmartArt ได้อย่างง่ายดาย บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการเพิ่มกราฟิก SmartArt ของแผนผังองค์กรลงในสไลด์ PowerPoint ของคุณ

**สิ่งที่คุณจะได้เรียนรู้:**
- การเพิ่มกราฟิก SmartArt ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python
- การปรับแต่งเค้าโครงของโหนด SmartArt ของคุณ
- บันทึกและส่งออกงานนำเสนออย่างมีประสิทธิภาพ

มาเริ่มต้นด้วยการตั้งค่าสภาพแวดล้อมของคุณกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนจะเริ่มสร้างกราฟิก SmartArt ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

### ห้องสมุดที่จำเป็น
- **Aspose.Slides สำหรับ Python**: ติดตั้งไลบรารีนี้โดยใช้ pip หากยังไม่ได้ทำ

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- การติดตั้ง Python ที่ใช้งานได้ (แนะนำ 3.x)
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Python
- ความคุ้นเคยกับ Microsoft PowerPoint เป็นสิ่งที่มีประโยชน์แต่ไม่จำเป็น

## การตั้งค่า Aspose.Slides สำหรับ Python

ในการเริ่มต้น ให้ตั้งค่าไลบรารี Aspose.Slides ในสภาพแวดล้อม Python ของคุณ:

**การติดตั้ง PIP:**
```bash
pip install aspose.slides
```

### ขั้นตอนการรับใบอนุญาต
Aspose นำเสนอตัวเลือกการออกใบอนุญาตที่หลากหลาย:
- **ทดลองใช้งานฟรี**:ดาวน์โหลดใบอนุญาตชั่วคราวเพื่อประเมินคุณสมบัติเต็มรูปแบบ
- **ใบอนุญาตชั่วคราว**:รับใบอนุญาตชั่วคราวฟรีเพื่อใช้งานในระยะสั้น
- **ซื้อ**:ควรพิจารณาซื้อการสมัครสมาชิกสำหรับโครงการระยะยาว

### การเริ่มต้นและการตั้งค่าเบื้องต้น

เมื่อติดตั้งแล้ว ให้เริ่มต้นสคริปต์ Python ของคุณด้วย Aspose.Slides ดังนี้:

```python
import aspose.slides as slides

# สร้างคลาส Presentation ด้วย slides.Presentation() เป็นการนำเสนอ:
    # โค้ดของคุณเพื่อเพิ่ม SmartArt จะอยู่ที่นี่
```

## คู่มือการใช้งาน

ตอนนี้เรามาดูขั้นตอนการเพิ่มและปรับแต่ง SmartArt ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python กัน

### การเพิ่มกราฟิก SmartArt

#### ภาพรวม
สร้างสไลด์ใหม่และเพิ่มแผนภูมิองค์กรประเภทกราฟิก SmartArt ลงไป:

```python
import aspose.slides as slides

# สร้างอินสแตนซ์การนำเสนอด้วย slides.Presentation() เป็นการนำเสนอ:
    # เพิ่ม SmartArt ที่มีขนาดที่กำหนดในตำแหน่ง (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### พารามิเตอร์และวัตถุประสงค์ของวิธีการ
- **เอ็กซ์,วาย**:ตำแหน่งของกราฟิก SmartArt บนสไลด์
- **ความกว้าง ความสูง**: ขนาดเพื่อการมองเห็นที่เหมาะสม
- **ประเภทเค้าโครง**: ระบุประเภทของเค้าโครง SmartArt ในกรณีนี้คือแผนผังองค์กร

### การปรับแต่งเค้าโครงแผนผังองค์กร

#### ภาพรวม
ปรับแต่งโหนดแรกในกราฟิก SmartArt ของเราโดยตั้งค่าเค้าโครงเป็น LEFT_HANGING:

```python
# ตั้งค่าโหนดแรกให้วางเลย์เอาต์แขวนด้านซ้าย
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### คำอธิบายตัวเลือกการกำหนดค่าคีย์
- **ประเภทเค้าโครงแผนภูมิองค์กร**:กำหนดวิธีแสดงโหนด ซึ่งจะเพิ่มความสามารถในการอ่านและความสวยงาม

### การบันทึกการนำเสนอ

สุดท้าย ให้บันทึกการนำเสนอของคุณไปยังไดเร็กทอรีที่ระบุ:

```python
# บันทึกการนำเสนอด้วย SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
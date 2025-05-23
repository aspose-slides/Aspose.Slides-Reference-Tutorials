---
"date": "2025-04-23"
"description": "เรียนรู้วิธีการสร้างและจัดรูปแบบรูปสี่เหลี่ยมผืนผ้าใน PowerPoint โดยอัตโนมัติด้วย Aspose.Slides สำหรับ Python พัฒนาทักษะการนำเสนอของคุณได้อย่างง่ายดาย"
"title": "สร้างรูปร่างสี่เหลี่ยมผืนผ้าอัตโนมัติใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python"
"url": "/th/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างและจัดรูปแบบรูปร่างสี่เหลี่ยมผืนผ้าใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Python
## การแนะนำ
คุณเคยพบว่าคุณต้องเพิ่มรูปร่างที่กำหนดเองอย่างรวดเร็วในงานนำเสนอ PowerPoint ของคุณแต่ประสบปัญหากับการขาดการทำงานอัตโนมัติหรือไม่ หากคุณเบื่อกับการจัดรูปแบบสี่เหลี่ยมผืนผ้าทีละสไลด์ด้วยตนเอง บทช่วยสอนนี้จะช่วยคุณได้ โดยใช้ประโยชน์จาก "Aspose.Slides สำหรับ Python" เราจะเพิ่มและกำหนดรูปแบบรูปร่างสี่เหลี่ยมผืนผ้าโดยอัตโนมัติด้วยโค้ดเพียงไม่กี่บรรทัด เมื่ออ่านคู่มือนี้จบ คุณจะเชี่ยวชาญ:
- การสร้างรูปสี่เหลี่ยมผืนผ้าด้วยโปรแกรม
- การใช้ตัวเลือกการจัดรูปแบบเช่นสีและรูปแบบเส้น
- บันทึกการนำเสนอของคุณได้อย่างง่ายดาย
มาเจาะลึกกันว่าคุณสามารถเปลี่ยนแปลงกระบวนการสร้างสไลด์ของคุณได้อย่างไร!
### ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มเขียนโค้ด ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:
- **งูหลาม** ติดตั้งไว้ในเครื่องของคุณแล้ว (แนะนำเวอร์ชัน 3.6 ขึ้นไป)
- **Aspose.Slides สำหรับ Python** ไลบรารีที่ช่วยให้เราจัดการการนำเสนอ PowerPoint ได้
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรม Python และความคุ้นเคยกับการติดตั้งแพ็กเกจโดยใช้ pip
## การตั้งค่า Aspose.Slides สำหรับ Python
### การติดตั้ง
หากต้องการติดตั้งแพ็กเกจ Aspose.Slides ให้เปิดเทอร์มินัลหรือพรอมต์คำสั่งและเรียกใช้:
```bash
pip install aspose.slides
```
คำสั่งนี้จะดึงและติดตั้ง Aspose.Slides เวอร์ชันล่าสุดสำหรับ Python จาก PyPI
### การขอใบอนุญาต
Aspose.Slides เป็นผลิตภัณฑ์เชิงพาณิชย์ แต่คุณสามารถเริ่มใช้งานโดยใช้ใบอนุญาตทดลองใช้งานฟรี วิธีขอรับใบอนุญาตมีดังนี้:
1. **ทดลองใช้งานฟรี:** เยี่ยม [ทดลองใช้ Aspose ฟรี](https://releases.aspose.com/slides/python-net/) และลงทะเบียนเพื่อรับการประเมินผล
2. **ใบอนุญาตชั่วคราว:** หากต้องการทดสอบแบบครอบคลุมมากขึ้นโดยไม่มีข้อจำกัด โปรดขอใบอนุญาตชั่วคราวได้ที่ [หน้าใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).
3. **ซื้อ:** เมื่อคุณพร้อมที่จะใช้งาน ให้ซื้อใบอนุญาตผ่านทาง [หน้าสั่งซื้อ Aspose](https://purchase-aspose.com/buy).
เมื่อได้รับแล้วให้ปฏิบัติตามเอกสารเพื่อนำใบอนุญาตไปใช้กับโครงการของคุณ
### การเริ่มต้นขั้นพื้นฐาน
นี่คือวิธีการเริ่มต้น Aspose.Slides สำหรับ Python:
```python
import aspose.slides as slides
\# เริ่มต้นการนำเสนอคลาส
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
สไนปเป็ตนี้จะสร้างการนำเสนอใหม่และยืนยันว่าพร้อมที่จะถูกจัดการแล้ว
## คู่มือการใช้งาน
### การสร้างรูปทรงสี่เหลี่ยมผืนผ้า
#### ภาพรวม
ในส่วนนี้เราจะเน้นที่การเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าลงในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Python
#### ขั้นตอนการสร้างรูปทรง
1. **เปิดหรือสร้างการนำเสนอ:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # เราจะเพิ่มรูปสี่เหลี่ยมผืนผ้าของเราที่นี่
   ```
2. **เข้าถึงสไลด์:**
   ดึงสไลด์แรกที่เราต้องการเพิ่มรูปร่าง
   ```python
   slide = pres.slides[0]
   ```
3. **เพิ่มรูปทรงสี่เหลี่ยมผืนผ้า:**
   ใช้ `add_auto_shape` วิธีการสร้างรูปสี่เหลี่ยมผืนผ้าบนสไลด์
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - พารามิเตอร์: `ShapeType.RECTANGLE`, ตำแหน่ง x (50), ตำแหน่ง y (150), ความกว้าง (150), ความสูง (50).
### การจัดรูปแบบรูปสี่เหลี่ยมผืนผ้า
#### ภาพรวม
ต่อไปเราจะนำการจัดรูปแบบไปใช้กับรูปร่างสี่เหลี่ยมผืนผ้าของเรา รวมถึงการเติมสีและสไตล์เส้น
#### ขั้นตอนการจัดรูปแบบ
1. **สีเติม:**
   ตั้งค่าการเติมสีทึบด้วยสีเฉพาะให้กับพื้นหลังของสี่เหลี่ยมผืนผ้า
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **สไตล์เส้น:**
   ปรับแต่งเส้นของสี่เหลี่ยมผืนผ้ารวมถึงสีและความกว้าง
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **บันทึกการนำเสนอ:**
   สุดท้ายให้บันทึกการนำเสนอลงในไฟล์
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
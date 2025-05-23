---
"date": "2025-04-22"
"description": "เรียนรู้วิธีการปรับเปลี่ยนข้อความ TextBox คำอธิบายปุ่ม และรูปภาพใน PowerPoint โดยใช้ Aspose.Slides กับ Python ปรับปรุงการนำเสนอของคุณด้วยองค์ประกอบแบบโต้ตอบ"
"title": "เรียนรู้ Aspose.Slides สำหรับ Python และปรับเปลี่ยนตัวควบคุม ActiveX ของ PowerPoint ได้อย่างง่ายดาย"
"url": "/th/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เรียนรู้ Aspose.Slides สำหรับ Python: การปรับเปลี่ยนตัวควบคุม ActiveX ของ PowerPoint

ในภูมิทัศน์ดิจิทัลที่เปลี่ยนแปลงอย่างรวดเร็วในปัจจุบัน การปรับแต่งการนำเสนอ Microsoft PowerPoint ถือเป็นสิ่งสำคัญสำหรับการสร้างเนื้อหาที่น่าสนใจ ไม่ว่าคุณจะกำลังพัฒนาโมดูลการฝึกอบรมแบบโต้ตอบหรือปรับปรุงการนำเสนอทางธุรกิจด้วยความสามารถในการป้อนข้อมูลจากผู้ใช้ การปรับแต่งตัวควบคุม ActiveX ของ PowerPoint สามารถเพิ่มฟังก์ชันการทำงานของการนำเสนอของคุณได้อย่างมาก บทช่วยสอนนี้จะอธิบายเกี่ยวกับการใช้ Aspose.Slides สำหรับ Python เพื่อเปลี่ยนข้อความ TextBox และคำบรรยายของปุ่ม แทนที่รูปภาพ เปลี่ยนตำแหน่ง หรือลบตัวควบคุม ActiveX จากสไลด์

## สิ่งที่คุณจะได้เรียนรู้
- วิธีการปรับเปลี่ยนข้อความ TextBox และคำอธิบายปุ่มในงานนำเสนอ PowerPoint
- เทคนิคในการแทนที่รูปภาพภายในตัวควบคุม ActiveX
- วิธีการเปลี่ยนตำแหน่งหรือลบตัวควบคุม ActiveX ได้อย่างมีประสิทธิภาพ
- การประยุกต์ใช้งานจริงของฟีเจอร์เหล่านี้ในสถานการณ์โลกแห่งความเป็นจริง

ก่อนที่จะเจาะลึก Aspose.Slides สำหรับ Python เรามาทบทวนข้อกำหนดเบื้องต้นกันก่อน

## ข้อกำหนดเบื้องต้น
หากต้องการทำตามบทช่วยสอนนี้ ให้แน่ใจว่าคุณมี:
- **งูหลาม**:ติดตั้งเวอร์ชัน 3.6 หรือสูงกว่าบนระบบของคุณ
- **Aspose.Slides สำหรับ Python ผ่านทาง .NET**: สามารถติดตั้งได้โดยใช้ pip
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Python และความคุ้นเคยกับโครงสร้างของ PowerPoint

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
1. **ติดตั้ง Aspose.Slides**-
   ใช้คำสั่งต่อไปนี้เพื่อติดตั้ง Aspose.Slides สำหรับ Python ผ่านทาง .NET:

   ```bash
   pip install aspose.slides
   ```

2. **การขอใบอนุญาต**- 
   เริ่มต้นโดยการได้รับ [ใบอนุญาตทดลองใช้งานฟรี](https://releases.aspose.com/slides/python-net/) หรือสมัครใบอนุญาตชั่วคราวเพื่อสำรวจขีดความสามารถเต็มรูปแบบโดยไม่มีข้อจำกัด

3. **การเริ่มต้นขั้นพื้นฐาน**-
   นำเข้าโมดูลที่จำเป็นและโหลดเอกสาร PowerPoint ของคุณตามที่แสดงด้านล่าง:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # โค้ดของคุณจะอยู่ที่นี่
   ```

## คู่มือการใช้งาน
### คุณสมบัติ: เปลี่ยนข้อความ TextBox และแทนที่รูปภาพ
#### ภาพรวม
คุณลักษณะนี้ช่วยให้คุณอัปเดตข้อความภายในตัวควบคุม TextBox ActiveX และแทนที่รูปภาพที่เกี่ยวข้อง ซึ่งมีประโยชน์สำหรับการปรับแต่งการนำเสนอหรือการอัปเดตเนื้อหาแบบไดนามิก

##### คำแนะนำทีละขั้นตอน
1. **โหลดงานนำเสนอ**-
   เริ่มต้นด้วยการโหลดงานนำเสนอ PowerPoint ของคุณที่มีตัวควบคุม ActiveX

   ```python
กำหนดการเปลี่ยนแปลง_กล่องข้อความและรูปภาพ():
    พร้อมสไลด์ Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") เป็นการนำเสนอ:
        สไลด์ = การนำเสนอ.สไลด์[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **สร้างภาพทดแทน**-
   สร้างภาพเพื่อแทนที่เนื้อหาต้นฉบับในระหว่างการเปิดใช้งาน ActiveX

   ```python
            import aspose.pydrawing as drawing

            # สร้างภาพที่มีขนาดตามที่กำหนด
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # เพิ่มเส้นขอบเพื่อให้ดูสวยงาม
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### คุณสมบัติ: เปลี่ยนคำบรรยายปุ่มและแทนที่รูปภาพ
#### ภาพรวม
อัปเดตคำอธิบายปุ่มภายในตัวควบคุม ActiveX ของการนำเสนอของคุณ ซึ่งจะช่วยเพิ่มความเป็นไปได้ในการโต้ตอบกับผู้ใช้แบบไดนามิก

##### คำแนะนำทีละขั้นตอน
1. **โหลดงานนำเสนอ**-
   เริ่มต้นด้วยการโหลดไฟล์ PowerPoint เหมือนเดิม

   ```python
กำหนด change_button_caption_and_image():
    พร้อมสไลด์ Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") เป็นการนำเสนอ:
        สไลด์ = การนำเสนอ.สไลด์[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **สร้างภาพทดแทน**-
   สร้างภาพเพื่อการทดแทนภาพ

   ```python
            # สร้างบิตแมปสำหรับขนาดของปุ่ม
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # เพิ่มเส้นขอบเพื่อความสวยงาม
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### คุณสมบัติ: ย้ายตัวควบคุม ActiveX ลงและบันทึกการนำเสนอ
#### ภาพรวม
เรียนรู้วิธีการเปลี่ยนตำแหน่งตัวควบคุม ActiveX ภายในสไลด์เพื่อเพิ่มความยืดหยุ่นของเค้าโครง

##### คำแนะนำทีละขั้นตอน
1. **โหลดงานนำเสนอ**-
   เปิดเอกสาร PowerPoint ของคุณเพื่อแก้ไข

   ```python
กำหนด move_active_x_controls_and_save():
    พร้อมสไลด์ Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") เป็นการนำเสนอ:
        สไลด์ = การนำเสนอ.สไลด์[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**บทสรุป:**
หากทำตามคำแนะนำนี้ คุณจะสามารถปรับเปลี่ยนตัวควบคุม ActiveX ของ PowerPoint ได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Slides สำหรับ Python ซึ่งจะช่วยเพิ่มการโต้ตอบและการปรับแต่งการนำเสนอของคุณ ทำให้ผู้ชมมีส่วนร่วมมากขึ้น

## คำแนะนำคีย์เวิร์ด
- “ปรับเปลี่ยนตัวควบคุม ActiveX ของ PowerPoint”
- "Aspose.Slides สำหรับ Python"
- “เปลี่ยนข้อความ TextBox ใน PowerPoint”
- “การแทนที่รูปภาพในตัวควบคุม ActiveX”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
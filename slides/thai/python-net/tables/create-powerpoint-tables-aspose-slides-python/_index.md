---
"date": "2025-04-24"
"description": "เรียนรู้วิธีสร้างตาราง PowerPoint โดยใช้ Aspose.Slides สำหรับ Python คำแนะนำทีละขั้นตอนนี้จะทำให้กระบวนการง่ายขึ้นและรับรองความสอดคล้องในงานนำเสนอของคุณ"
"title": "สร้างตาราง PowerPoint โดยใช้ Aspose.Slides และ Python พร้อมคำแนะนำทีละขั้นตอน"
"url": "/th/python-net/tables/create-powerpoint-tables-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างตาราง PowerPoint ด้วย Aspose.Slides และ Python

การสร้างตารางในงานนำเสนอ PowerPoint ด้วยโปรแกรมสามารถช่วยประหยัดเวลาและรับรองความสอดคล้องกันในเอกสารต่างๆ ไม่ว่าคุณจะกำลังสร้างรายงาน สร้างสื่อการฝึกอบรม หรือพัฒนาเครื่องมือสำหรับการนำเสนออัตโนมัติ การใช้ Aspose.Slides สำหรับ Python จะทำให้กระบวนการนี้ง่ายขึ้นด้วยการผสานรวมการสร้างตารางเข้ากับฐานโค้ดของคุณได้อย่างราบรื่น คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนต่างๆ ในการสร้างตาราง PowerPoint ในสไลด์แรกโดยใช้ Aspose.Slides และ Python

## สิ่งที่คุณจะได้เรียนรู้:
- วิธีตั้งค่าสภาพแวดล้อมของคุณสำหรับ Aspose.Slides ด้วย Python
- คำแนะนำทีละขั้นตอนสำหรับการสร้างตารางในสไลด์ PowerPoint
- การประยุกต์ใช้งานจริงของการรวมตารางเข้ากับงานนำเสนอ
- ข้อควรพิจารณาด้านประสิทธิภาพเมื่อทำงานกับ Aspose.Slides

มาเจาะลึกถึงข้อกำหนดเบื้องต้นและเริ่มกันเลย!

### ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าสภาพแวดล้อมของคุณได้รับการตั้งค่าอย่างถูกต้อง นี่คือสิ่งที่คุณต้องการ:
1. **สภาพแวดล้อม Python**:ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Python 3.x ไว้ในระบบของคุณแล้ว
2. **Aspose.Slides สำหรับ Python**:ไลบรารีนี้จะเป็นเครื่องมือหลักของเราในการจัดการไฟล์ PowerPoint
3. **IDE สำหรับการพัฒนาหรือ Text Editor**เช่น PyCharm, VSCode หรือโปรแกรมแก้ไขใดๆ ที่คุณต้องการ

### การตั้งค่า Aspose.Slides สำหรับ Python

หากต้องการเริ่มใช้ Aspose.Slides สำหรับ Python ให้ทำตามขั้นตอนเหล่านี้:

**ติดตั้งผ่าน pip:**

```bash
pip install aspose.slides
```

**การได้มาซึ่งใบอนุญาต:** 
- **ทดลองใช้งานฟรี**: ดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้จาก [เว็บไซต์อาโพส](https://releases-aspose.com/slides/python-net/).
- **ใบอนุญาตชั่วคราว**:รับใบอนุญาตชั่วคราวเพื่อใช้งานต่อเนื่องได้โดยเข้าไปที่ [ลิงค์](https://purchase-aspose.com/temporary-license/).
- **ซื้อ**:หากต้องการคุณสมบัติครบถ้วน โปรดพิจารณาซื้อใบอนุญาตจาก [หน้าการซื้อ](https://purchase-aspose.com/buy).

**การเริ่มต้นขั้นพื้นฐาน:**

หลังจากติดตั้งแล้ว คุณสามารถเริ่มใช้ Aspose.Slides ในสคริปต์ Python ของคุณได้ นำเข้าไลบรารีตามที่แสดงด้านล่าง:

```python
import aspose.slides as slides
```

### คู่มือการใช้งาน

ตอนนี้เราได้ตั้งค่าสภาพแวดล้อมของเราเรียบร้อยแล้ว มาเริ่มสร้างตารางกันเลย

#### การสร้างตารางบนสไลด์

**ภาพรวม**เราจะสร้างตารางง่าย ๆ และเพิ่มลงในสไลด์แรกของการนำเสนอ PowerPoint 

##### ขั้นตอนที่ 1: สร้างอินสแตนซ์ของคลาสการนำเสนอ

การ `Presentation` คลาสนี้แสดงถึงไฟล์ PPT ที่นี่เราจะเปิดหรือสร้างงานนำเสนอใหม่:

```python
with slides.Presentation() as pres:
    # อินสแตนซ์การนำเสนอจะถูกใช้ภายในบล็อกตัวจัดการบริบทนี้
```

##### ขั้นตอนที่ 2: เข้าถึงสไลด์แรก

การเข้าถึงสไลด์แรกช่วยให้เราเพิ่มตารางของเราที่นั่นได้:

```python
slide = pres.slides[0]  # นี่จะดึงสไลด์แรกจากการนำเสนอ
```

##### ขั้นตอนที่ 3: กำหนดขนาดตารางและเพิ่มลงในสไลด์

กำหนดความกว้างของคอลัมน์และความสูงของแถว จากนั้นเพิ่มตารางตามพิกัดที่กำหนด (x=50, y=50):

```python
dbl_cols = [50, 50, 50]  # ความกว้างของคอลัมน์
dbl_rows = [50, 30, 30, 30, 30]  # ความสูงของแถว

table = slide.shapes.add_table(50, 50, dbl_cols, dbl_rows)  # การเพิ่มตารางลงในสไลด์
```

##### ขั้นตอนที่ 4: เติมข้อความลงในเซลล์ตาราง

ทำซ้ำผ่านแต่ละเซลล์ในตารางและเพิ่มข้อความ:

```python
for row in table.rows:
    for cell in row:
        tf = cell.text_frame
        tf.text = "T" + str(cell.first_row_index) + str(cell.first_column_index)
        
        if tf.paragraphs:  # ให้แน่ใจว่ามีย่อหน้าที่จะแก้ไข
            tf.paragraphs[0].portions[0].portion_format.font_height = 10
            tf.paragraphs[0].paragraph_format.bullet.type = slides.BulletType.NONE
```

##### ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอของคุณไปยังตำแหน่งที่ระบุ:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/tables_create_table_out.ppt\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
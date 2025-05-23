---
"date": "2025-04-23"
"description": "เรียนรู้วิธีปรับมุมการหมุนของชื่อแผนภูมิในการนำเสนอโดยใช้ Aspose.Slides สำหรับ Python เพื่อเพิ่มความสามารถในการอ่านและความสวยงาม"
"title": "วิธีตั้งค่าการหมุนชื่อแกนแนวตั้งของแผนภูมิใน Aspose.Slides สำหรับ Python"
"url": "/th/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีตั้งค่าการหมุนชื่อแกนแนวตั้งของแผนภูมิใน Aspose.Slides สำหรับ Python

## การแนะนำ

ในการนำเสนอข้อมูล การปรับปรุงความสามารถในการอ่านแผนภูมิถือเป็นสิ่งสำคัญ การปรับมุมการหมุนของชื่อแกนแนวตั้งของแผนภูมิโดยใช้ Aspose.Slides สำหรับ Python จะทำให้ชื่อแผนภูมิพอดีหรือโดดเด่นในสไลด์ของคุณได้ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการตั้งค่ามุมการหมุนนี้เพื่อปรับปรุงทั้งการใช้งานและความสวยงาม

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการติดตั้งและกำหนดค่า Aspose.Slides สำหรับ Python
- ขั้นตอนในการเพิ่มและปรับแต่งแผนภูมิภายในสไลด์ของคุณ
- เทคนิคการตั้งมุมการหมุนของชื่อแผนภูมิ
- การประยุกต์ใช้งานจริงสำหรับฟีเจอร์เหล่านี้ในการแสดงภาพข้อมูล

มาเริ่มต้นด้วยการครอบคลุมข้อกำหนดเบื้องต้นก่อนจะลงมือปฏิบัติ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเริ่มต้น ให้แน่ใจว่าคุณมี:
- **สภาพแวดล้อม Python**:ติดตั้ง Python 3.x จาก [python.org](https://www-python.org/).
- **ห้องสมุด Aspose.Slides**:ติดตั้งผ่าน pip เพื่อจัดการการนำเสนอได้อย่างมีประสิทธิภาพ
- **ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Python**:ความคุ้นเคยกับรูปแบบภาษา Python และการดำเนินการกับไฟล์จะช่วยให้คุณทำตามได้

## การตั้งค่า Aspose.Slides สำหรับ Python

หากต้องการใช้ Aspose.Slides ให้ติดตั้งโดยใช้ pip เปิดเทอร์มินัลหรือพรอมต์คำสั่งแล้วรัน:

```bash
pip install aspose.slides
```

### ขั้นตอนการรับใบอนุญาต

Aspose นำเสนอตัวเลือกใบอนุญาตที่แตกต่างกัน:
- **ทดลองใช้งานฟรี**:ดาวน์โหลดเวอร์ชันทดลองใช้ได้จาก [หน้าการเปิดตัวของ Aspose](https://releases-aspose.com/slides/python-net/).
- **ใบอนุญาตชั่วคราว**:รับใบอนุญาตชั่วคราวสำหรับฟีเจอร์ขยายเพิ่มเติมผ่านทาง [พอร์ทัลการซื้อ](https://purchase-aspose.com/temporary-license/).
- **ซื้อ**:พิจารณาซื้อหากคุณพบว่าเครื่องมือนี้จำเป็นซึ่งมีจำหน่ายจาก [หน้าสั่งซื้อ Aspose](https://purchase-aspose.com/buy).

#### การเริ่มต้นและการตั้งค่าเบื้องต้น

วิธีการเริ่มต้น Aspose.Slides ในสคริปต์ Python ของคุณมีดังนี้:

```python
import aspose.slides as slides

# สร้างวัตถุการนำเสนอ
def main():
    with slides.Presentation() as pres:
        # โค้ดของคุณจะอยู่ที่นี่
        pass

if __name__ == "__main__":
    main()
```

## คู่มือการใช้งาน

### การเพิ่มและปรับแต่งแผนภูมิ

#### ภาพรวม

ในส่วนนี้ เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ของคุณและปรับแต่งโดยการตั้งค่ามุมการหมุนของชื่อแกนแนวตั้ง

#### ขั้นตอน:

##### ขั้นตอนที่ 1: เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม

เริ่มต้นด้วยการเพิ่มแผนภูมิตามพิกัดที่กำหนดพร้อมมิติที่กำหนด:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในสไลด์ที่ 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### ขั้นตอนที่ 2: กำหนดค่าชื่อแกนแนวตั้ง

เปิดใช้งานและตั้งค่ามุมการหมุนสำหรับชื่อแกนแนวตั้ง:

```python
def configure_chart(chart):
    # เปิดใช้งานชื่อแกนแนวตั้ง
    chart.axes.vertical_axis.has_title = True
    
    # ตั้งค่ามุมการหมุนเป็น 90 องศา
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### ขั้นตอนที่ 3: บันทึกการนำเสนอของคุณ

สุดท้ายให้บันทึกการนำเสนอของคุณพร้อมกับการเปลี่ยนแปลง:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # บันทึกการนำเสนอ
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
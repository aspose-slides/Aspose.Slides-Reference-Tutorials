---
"date": "2025-04-23"
"description": "เรียนรู้วิธีตั้งค่าการนำเสนอ PowerPoint ให้เป็นแบบอ่านอย่างเดียวและนับจำนวนสไลด์ด้วยโปรแกรมโดยใช้ Aspose.Slides สำหรับ Python เหมาะอย่างยิ่งสำหรับการแบ่งปันเอกสารที่ปลอดภัยและการรายงานอัตโนมัติ"
"title": "ตั้งค่า PowerPoint ให้อ่านอย่างเดียวและนับสไลด์ด้วย Python โดยใช้ Aspose.Slides"
"url": "/th/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ตั้งค่า PowerPoint ให้อ่านอย่างเดียวและนับสไลด์ด้วย Python

## การแนะนำ
คุณเคยเผชิญกับความท้าทายในการแจกจ่ายงานนำเสนอโดยที่ยังคงไม่เปลี่ยนแปลงหรือไม่ หรือบางทีคุณอาจต้องการวิธีง่ายๆ ในการตรวจสอบว่ามีสไลด์กี่สไลด์ในงานนำเสนอของคุณโดยไม่ต้องเปิดดู ด้วย **Aspose.Slides สำหรับ Python**งานเหล่านี้จะกลายเป็นเรื่องง่ายๆ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการตั้งค่าการนำเสนอ PowerPoint เป็นแบบอ่านอย่างเดียวและการนับสไลด์โดยใช้ Aspose.Slides ซึ่งเป็นโซลูชันที่มีประสิทธิภาพสำหรับการจัดการไฟล์ PowerPoint ของคุณด้วยโปรแกรม

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่าการป้องกันการเขียนบนงานนำเสนอ PowerPoint
- วิธีบันทึกไฟล์ PowerPoint โดยมีข้อจำกัดแบบอ่านอย่างเดียว
- วิธีการโหลดงานนำเสนอและนับจำนวนสไลด์อย่างมีประสิทธิภาพ

มาเจาะลึกกันว่าคุณสามารถบรรลุงานเหล่านี้ได้อย่างราบรื่นใน Python ได้อย่างไร

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมี:
- **ไพธอน 3.6+** ติดตั้งอยู่บนระบบของคุณแล้ว
- การเข้าถึงอินเทอร์เฟซบรรทัดคำสั่งสำหรับการติดตั้งแพ็คเกจ

คุณจะต้องติดตั้ง Aspose.Slides สำหรับ Python ด้วย ไลบรารีอันทรงพลังนี้ช่วยให้จัดการไฟล์ PowerPoint ขั้นสูงได้โดยตรงจากสภาพแวดล้อม Python ของคุณ แม้ว่าเวอร์ชันฟรีจะมีฟังก์ชันการทำงานที่จำกัด แต่การซื้อใบอนุญาต (ไม่ว่าจะผ่านการทดลองใช้ฟรีหรือการซื้อ) จะช่วยเพิ่มความสามารถได้อย่างมาก

## การตั้งค่า Aspose.Slides สำหรับ Python
หากต้องการเริ่มใช้งาน Aspose.Slides ใน Python คุณจะต้องติดตั้งก่อน โดยทำตามขั้นตอนดังนี้:

### การติดตั้ง pip
เรียกใช้คำสั่งต่อไปนี้ในเทอร์มินัลหรือพรอมต์คำสั่งของคุณ:

```bash
pip install aspose.slides
```

นี่จะดาวน์โหลดและติดตั้ง Aspose.Slides เวอร์ชันล่าสุดสำหรับ Python

### ขั้นตอนการรับใบอนุญาต
1. **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟังก์ชันพื้นฐาน
2. **ใบอนุญาตชั่วคราว**:รับใบอนุญาตชั่วคราวเพื่อปลดล็อคคุณสมบัติเต็มรูปแบบในช่วงระยะเวลาประเมินผลของคุณ
3. **ซื้อ**:ควรพิจารณาซื้อใบอนุญาตเพื่อการเข้าถึงและการสนับสนุนอย่างต่อเนื่อง

เมื่อคุณมีไฟล์ใบอนุญาตแล้ว ให้โหลดลงในสคริปต์ของคุณดังนี้:

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## คู่มือการใช้งาน
ในส่วนนี้ เราจะแบ่งการใช้งานออกเป็นสองคุณลักษณะหลัก: การตั้งค่าการนำเสนอเป็นแบบอ่านอย่างเดียว และการนับสไลด์

### คุณสมบัติ 1: บันทึกการนำเสนอเป็นแบบอ่านอย่างเดียว
#### ภาพรวม
ฟีเจอร์นี้ช่วยให้คุณตั้งค่าการป้องกันการเขียนในไฟล์ PowerPoint ได้ โดยรับรองว่าจะไม่สามารถแก้ไขได้หากไม่ได้ป้อนรหัสผ่าน ซึ่งมีประโยชน์อย่างยิ่งในการแจกจ่ายงานนำเสนอที่ผู้รับไม่ควรเปลี่ยนแปลง

#### ขั้นตอน
##### ขั้นตอนที่ 1: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
เริ่มต้นด้วยการสร้าง `Presentation` วัตถุ นี่แสดงถึงไฟล์ PPT ของคุณใน Python

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
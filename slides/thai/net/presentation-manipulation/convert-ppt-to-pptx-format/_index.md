---
"description": "เรียนรู้วิธีการแปลง PPT เป็น PPTX ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับการแปลงรูปแบบที่ราบรื่น"
"linktitle": "แปลง PPT เป็นรูปแบบ PPTX"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "แปลง PPT เป็นรูปแบบ PPTX"
"url": "/th/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลง PPT เป็นรูปแบบ PPTX


หากคุณเคยจำเป็นต้องแปลงไฟล์ PowerPoint จากรูปแบบ PPT แบบเก่าไปเป็นรูปแบบ PPTX ใหม่โดยใช้ .NET คุณมาถูกที่แล้ว ในบทช่วยสอนแบบทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการโดยใช้ Aspose.Slides สำหรับ API ของ .NET ด้วยไลบรารีอันทรงพลังนี้ คุณสามารถจัดการการแปลงดังกล่าวได้อย่างง่ายดาย เริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสิ่งต่อไปนี้แล้ว:

- Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio แล้ว และพร้อมสำหรับการพัฒนา .NET
- Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ .NET จาก [ที่นี่](https://releases-aspose.com/slides/net/).

## การตั้งค่าโครงการ

1. สร้างโครงการใหม่: เปิด Visual Studio และสร้างโครงการ C# ใหม่

2. เพิ่มการอ้างอิงถึง Aspose.Slides: คลิกขวาที่โครงการของคุณใน Solution Explorer เลือก "จัดการแพ็คเกจ NuGet" และค้นหา "Aspose.Slides" ติดตั้งแพ็คเกจ

3. นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Slides;
```

## การแปลง PPT เป็น PPTX

ตอนนี้เราได้ตั้งค่าโครงการเรียบร้อยแล้ว มาเขียนโค้ดเพื่อแปลงไฟล์ PPT เป็น PPTX กัน

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์ PPT
Presentation pres = new Presentation(srcFileName);

// บันทึกการนำเสนอในรูปแบบ PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

ในชิ้นส่วนโค้ดนี้:

- `dataDir` ควรแทนที่ด้วยเส้นทางไดเร็กทอรีที่ไฟล์ PPT ของคุณอยู่
- `outPath` ควรแทนที่ด้วยไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PPTX ที่แปลงแล้ว
- `srcFileName` คือชื่อไฟล์ PPT ที่คุณอินพุต
- `destFileName` คือชื่อที่ต้องการสำหรับไฟล์ PPTX เอาท์พุต

## บทสรุป

ขอแสดงความยินดี! คุณได้แปลงงานนำเสนอ PowerPoint จากรูปแบบ PPT เป็นรูปแบบ PPTX สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET API ไลบรารีอันทรงพลังนี้ช่วยลดความซับซ้อนของงานต่างๆ เช่นนี้ ทำให้ประสบการณ์การพัฒนา .NET ของคุณราบรื่นยิ่งขึ้น

หากคุณยังไม่ได้ทำ [ดาวน์โหลด Aspose.Slides สำหรับ .NET](https://releases.aspose.com/slides/net/) และสำรวจศักยภาพของมันต่อไป

สำหรับบทช่วยสอนและเคล็ดลับเพิ่มเติม โปรดเยี่ยมชม [เอกสารประกอบ](https://reference-aspose.com/slides/net/).

## คำถามที่พบบ่อย

### 1. Aspose.Slides สำหรับ .NET คืออะไร?
Aspose.Slides สำหรับ .NET เป็นไลบรารี .NET ที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงการนำเสนอ PowerPoint ได้ด้วยโปรแกรม

### 2. ฉันสามารถแปลงรูปแบบอื่นเป็น PPTX โดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบต่างๆ รวมถึง PPT, PPTX, ODP และอื่นๆ อีกมากมาย

### 3. สามารถใช้ Aspose.Slides สำหรับ .NET ได้ฟรีหรือไม่?
ไม่ มันเป็นห้องสมุดเชิงพาณิชย์ แต่คุณสามารถสำรวจได้ [ทดลองใช้งานฟรี](https://releases.aspose.com/) เพื่อประเมินคุณสมบัติของมัน

### 4. มีรูปแบบเอกสารอื่น ๆ ที่ได้รับการรองรับโดย Aspose.Slides สำหรับ .NET หรือไม่
ใช่ Aspose.Slides สำหรับ .NET ยังรองรับการทำงานกับเอกสาร Word, สเปรดชีต Excel และรูปแบบไฟล์อื่นๆ ด้วย

### 5. ฉันจะได้รับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
คุณสามารถค้นหาคำตอบสำหรับคำถามของคุณและขอรับการสนับสนุนได้ที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
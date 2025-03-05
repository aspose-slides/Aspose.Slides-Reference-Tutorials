---
title: แปลง PPT เป็นรูปแบบ PPTX
linktitle: แปลง PPT เป็นรูปแบบ PPTX
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลง PPT เป็น PPTX ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับการแปลงรูปแบบที่ราบรื่น
type: docs
weight: 25
url: /th/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

หากคุณจำเป็นต้องแปลงไฟล์ PowerPoint จากรูปแบบ PPT เก่าไปเป็นรูปแบบ PPTX ที่ใหม่กว่าโดยใช้ .NET แสดงว่าคุณมาถูกที่แล้ว ในบทช่วยสอนแบบทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการโดยใช้ Aspose.Slides สำหรับ .NET API ด้วยไลบรารีอันทรงพลังนี้ คุณสามารถจัดการกับการแปลงดังกล่าวได้อย่างง่ายดาย มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าต่อไปนี้:

- Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio และพร้อมสำหรับการพัฒนา .NET
-  Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/slides/net/).

## การจัดตั้งโครงการ

1. สร้างโครงการใหม่: เปิด Visual Studio และสร้างโครงการ C# ใหม่

2. เพิ่มการอ้างอิงไปยัง Aspose.Slides: คลิกขวาที่โปรเจ็กต์ของคุณใน Solution Explorer เลือก "จัดการแพ็คเกจ NuGet" และค้นหา "Aspose.Slides" ติดตั้งแพ็คเกจ

3. นำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Slides;
```

## แปลง PPT เป็น PPTX

ตอนนี้เราได้ตั้งค่าโครงการแล้ว เรามาเขียนโค้ดเพื่อแปลงไฟล์ PPT เป็น PPTX กันดีกว่า

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์ PPT
Presentation pres = new Presentation(srcFileName);

//บันทึกการนำเสนอในรูปแบบ PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

ในข้อมูลโค้ดนี้:

- `dataDir` ควรแทนที่ด้วยเส้นทางไดเร็กทอรีที่มีไฟล์ PPT ของคุณอยู่
- `outPath` ควรแทนที่ด้วยไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PPTX ที่แปลงแล้ว
- `srcFileName` คือชื่อของไฟล์ PPT อินพุตของคุณ
- `destFileName` เป็นชื่อที่ต้องการสำหรับไฟล์ PPTX เอาต์พุต

## บทสรุป

ยินดีด้วย! คุณได้แปลงงานนำเสนอ PowerPoint จากรูปแบบ PPT เป็นรูปแบบ PPTX ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET API ไลบรารีอันทรงพลังนี้ทำให้งานที่ซับซ้อนเช่นนี้ง่ายขึ้น ทำให้ประสบการณ์การพัฒนา .NET ของคุณราบรื่นยิ่งขึ้น

 หากคุณยังไม่ได้[ดาวน์โหลด Aspose.Slides สำหรับ .NET](https://releases.aspose.com/slides/net/) และสำรวจความสามารถของตนต่อไป

 สำหรับบทช่วยสอนและเคล็ดลับเพิ่มเติม โปรดไปที่ของเรา[เอกสารประกอบ](https://reference.aspose.com/slides/net/).

## คำถามที่พบบ่อย

### 1. Aspose.Slides สำหรับ .NET คืออะไร
Aspose.Slides สำหรับ .NET คือไลบรารี .NET ที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม

### 2. ฉันสามารถแปลงรูปแบบอื่นเป็น PPTX โดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบต่างๆ รวมถึง PPT, PPTX, ODP และอื่นๆ

### 3. Aspose.Slides สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 ไม่ มันเป็นห้องสมุดเชิงพาณิชย์ แต่คุณสามารถสำรวจได้[ทดลองฟรี](https://releases.aspose.com/) เพื่อประเมินคุณสมบัติของมัน

### 4. Aspose.Slides สำหรับ .NET รองรับรูปแบบเอกสารอื่นๆ หรือไม่
ใช่ Aspose.Slides สำหรับ .NET ยังรองรับการทำงานกับเอกสาร Word, สเปรดชีต Excel และรูปแบบไฟล์อื่นๆ อีกด้วย

### 5. ฉันจะรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาคำตอบสำหรับคำถามของคุณและขอรับการสนับสนุนได้ใน[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/).


---
"description": "แปลงงานนำเสนอ PowerPoint เป็น HTML พร้อมแบบอักษรฝังตัวโดยใช้ Aspose.Slides สำหรับ .NET รักษาความคิดริเริ่มได้อย่างราบรื่น"
"linktitle": "แปลงงานนำเสนอเป็น HTML ด้วยแบบอักษรฝังตัว"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "แปลงงานนำเสนอเป็น HTML ด้วยแบบอักษรฝังตัว"
"url": "/th/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงงานนำเสนอเป็น HTML ด้วยแบบอักษรฝังตัว


ในยุคดิจิทัลทุกวันนี้ การแบ่งปันงานนำเสนอและเอกสารออนไลน์กลายเป็นเรื่องปกติไปแล้ว อย่างไรก็ตาม ความท้าทายประการหนึ่งที่มักเกิดขึ้นคือการตรวจสอบให้แน่ใจว่าแบบอักษรของคุณแสดงอย่างถูกต้องเมื่อแปลงงานนำเสนอเป็น HTML บทช่วยสอนทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการใช้ Aspose.Slides สำหรับ .NET เพื่อแปลงงานนำเสนอเป็น HTML พร้อมแบบอักษรที่ฝังไว้ เพื่อให้แน่ใจว่าเอกสารของคุณมีลักษณะตามที่คุณตั้งใจไว้

## บทนำสู่ Aspose.Slides สำหรับ .NET

ก่อนที่เราจะเจาะลึกในบทช่วยสอนนี้ เรามาทำความรู้จัก Aspose.Slides สำหรับ .NET กันก่อน Aspose.Slides เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถทำงานกับการนำเสนอ PowerPoint ในแอปพลิเคชัน .NET ได้ ด้วย Aspose.Slides คุณสามารถสร้าง แก้ไข และแปลงไฟล์ PowerPoint ได้ด้วยโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Aspose.Slides สำหรับ .NET: คุณควรติดตั้งไลบรารี Aspose.Slides ไว้ในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

1. สร้างโครงการใหม่หรือเปิดโครงการที่มีอยู่แล้วในสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ

2. เพิ่มการอ้างอิงถึงไลบรารี Aspose.Slides ในโปรเจ็กต์ของคุณ

3. นำเข้าเนมสเปซที่จำเป็นในโค้ดของคุณ:

   ```csharp
   using Aspose.Slides;
   ```

## ขั้นตอนที่ 2: โหลดงานนำเสนอของคุณ

ในการเริ่มต้น คุณต้องโหลดงานนำเสนอที่คุณต้องการแปลงเป็น HTML แทนที่ `"Your Document Directory"` พร้อมไดเร็กทอรีจริงที่ไฟล์การนำเสนอของคุณตั้งอยู่

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // รหัสของคุณอยู่ที่นี่
}
```

## ขั้นตอนที่ 3: ไม่รวมแบบอักษรการนำเสนอเริ่มต้น

ในขั้นตอนนี้ คุณสามารถระบุแบบอักษรเริ่มต้นของงานนำเสนอที่คุณต้องการไม่ให้ฝังได้ ซึ่งจะช่วยปรับขนาดไฟล์ HTML ที่ได้ให้เหมาะสม

```csharp
string[] fontNameExcludeList = { };
```

## ขั้นตอนที่ 4: เลือกตัวควบคุม HTML

ขณะนี้คุณมีสองตัวเลือกในการฝังแบบอักษรใน HTML:

### ตัวเลือกที่ 1: ฝังแบบอักษรทั้งหมด

หากต้องการฝังแบบอักษรทั้งหมดที่ใช้ในการนำเสนอ ให้ใช้ `EmbedAllFontsHtmlController`-

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### ตัวเลือกที่ 2: เชื่อมโยงแบบอักษรทั้งหมด

หากต้องการเชื่อมโยงไปยังแบบอักษรทั้งหมดที่ใช้ในการนำเสนอ ให้ใช้ `LinkAllFontsHtmlController`คุณควรระบุไดเร็กทอรีที่แบบอักษรตั้งอยู่บนระบบของคุณ

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## ขั้นตอนที่ 5: กำหนดตัวเลือก HTML

สร้าง `HtmlOptions` วัตถุและตั้งค่าตัวจัดรูปแบบ HTML เป็นตัวที่คุณเลือกในขั้นตอนก่อนหน้า

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // ใช้ embedFontsController เพื่อฝังแบบอักษรทั้งหมด
};
```

## ขั้นตอนที่ 6: บันทึกเป็น HTML

สุดท้าย ให้บันทึกงานนำเสนอเป็นไฟล์ HTML คุณสามารถเลือกได้ `SaveFหรือmat.Html` or `SaveFormat.Html5` ขึ้นอยู่กับความต้องการของคุณ

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## บทสรุป

ขอแสดงความยินดี! คุณได้แปลงงานนำเสนอของคุณเป็น HTML พร้อมแบบอักษรฝังตัวโดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว การดำเนินการนี้จะช่วยให้มั่นใจได้ว่าแบบอักษรของคุณจะแสดงอย่างถูกต้องเมื่อแชร์งานนำเสนอของคุณทางออนไลน์

ตอนนี้คุณสามารถแบ่งปันงานนำเสนอที่มีรูปแบบสวยงามของคุณได้อย่างง่ายดายและมั่นใจ เพราะมั่นใจได้ว่าผู้ฟังจะมองเห็นงานนำเสนอเหล่านั้นตามที่คุณตั้งใจไว้ทุกประการ

สำหรับข้อมูลเพิ่มเติมและการอ้างอิง API โดยละเอียด โปรดดูที่ [เอกสาร Aspose.Slides สำหรับ .NET](https://reference-aspose.com/slides/net/).

## คำถามที่พบบ่อย

### 1. ฉันสามารถแปลงการนำเสนอ PowerPoint เป็น HTML โดยใช้ Aspose.Slides สำหรับ .NET ในโหมดแบทช์ได้หรือไม่

ใช่ คุณสามารถแปลงงานนำเสนอหลาย ๆ ไฟล์เป็น HTML ได้โดยใช้ Aspose.Slides สำหรับ .NET โดยการวนซ้ำผ่านไฟล์งานนำเสนอของคุณและใช้กระบวนการแปลงกับแต่ละไฟล์

### 2. มีวิธีปรับแต่งลักษณะที่ปรากฏของผลลัพธ์ HTML หรือไม่

แน่นอน! Aspose.Slides สำหรับ .NET มีตัวเลือกต่าง ๆ เพื่อปรับแต่งลักษณะที่ปรากฏและการจัดรูปแบบของผลลัพธ์ HTML เช่น การปรับสี แบบอักษร และเค้าโครง

### 3. มีข้อจำกัดใด ๆ สำหรับการฝังแบบอักษรใน HTML โดยใช้ Aspose.Slides สำหรับ .NET หรือไม่

แม้ว่า Aspose.Slides สำหรับ .NET จะมีความสามารถในการฝังฟอนต์ได้อย่างยอดเยี่ยม แต่โปรดจำไว้ว่าขนาดไฟล์ HTML ของคุณอาจเพิ่มขึ้นเมื่อฝังฟอนต์ ตรวจสอบให้แน่ใจว่าคุณได้ปรับตัวเลือกฟอนต์ให้เหมาะสมกับการใช้งานบนเว็บ

### 4. ฉันสามารถแปลงงานนำเสนอ PowerPoint เป็นรูปแบบอื่นด้วย Aspose.Slides สำหรับ .NET ได้หรือไม่

ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบเอาต์พุตหลากหลาย รวมถึง PDF รูปภาพ และอื่นๆ อีกมากมาย คุณสามารถแปลงงานนำเสนอเป็นรูปแบบที่ต้องการได้อย่างง่ายดาย

### 5. ฉันสามารถค้นหาทรัพยากรเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ใด

คุณสามารถเข้าถึงทรัพยากรมากมาย รวมถึงเอกสารเกี่ยวกับ [เอกสารอ้างอิง Aspose.Slides สำหรับ API ของ .NET](https://reference-aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
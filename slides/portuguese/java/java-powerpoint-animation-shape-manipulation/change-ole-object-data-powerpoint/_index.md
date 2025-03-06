---
title: Alterar dados de objeto OLE no PowerPoint
linktitle: Alterar dados de objeto OLE no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como alterar dados de objetos OLE no PowerPoint usando Aspose.Slides para Java. Um guia passo a passo para atualizações fáceis e eficientes.
weight: 14
url: /pt/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
Alterar dados de objetos OLE em apresentações do PowerPoint pode ser uma tarefa crucial quando você precisa atualizar o conteúdo incorporado sem editar manualmente cada slide. Este guia abrangente irá guiá-lo através do processo usando Aspose.Slides for Java, uma biblioteca poderosa projetada para lidar com apresentações em PowerPoint. Quer você seja um desenvolvedor experiente ou esteja apenas começando, você achará este tutorial útil e fácil de seguir.
## Pré-requisitos
Antes de nos aprofundarmos no código, vamos garantir que você tenha tudo o que precisa para começar.
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixá-lo em[Site da Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides para Java: Baixe a versão mais recente do[Página de download do Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Ambiente de desenvolvimento integrado (IDE): você pode usar qualquer IDE Java, como IntelliJ IDEA, Eclipse ou NetBeans.
4.  Aspose.Cells for Java: Isso é necessário para modificar os dados incorporados no objeto OLE. Baixe em[Página de download do Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  Arquivo de apresentação: tenha um arquivo PowerPoint pronto com um objeto OLE incorporado. Para este tutorial, vamos nomeá-lo`ChangeOLEObjectData.pptx`.
## Importar pacotes
Primeiro, vamos importar os pacotes necessários para o seu projeto Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Agora, vamos dividir o processo em etapas simples e gerenciáveis.
## Etapa 1: carregar a apresentação do PowerPoint
Para começar, você precisa carregar a apresentação do PowerPoint que contém o objeto OLE.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Etapa 2: acesse o slide que contém o objeto OLE
A seguir, obtenha o slide onde o objeto OLE está incorporado.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Etapa 3: Encontre o objeto OLE no slide
Itere pelas formas do slide para localizar o objeto OLE.
```java
OleObjectFrame ole = null;
// Atravessando todas as formas para o quadro Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Etapa 4: extrair os dados incorporados do objeto OLE
Se o objeto OLE for encontrado, extraia seus dados incorporados.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Etapa 5: modificar os dados incorporados usando Aspose.Cells
Agora, use Aspose.Cells para ler e modificar os dados incorporados, que neste caso é provavelmente uma pasta de trabalho do Excel.
```java
    Workbook wb = new Workbook(msln);
    // Modifique os dados da pasta de trabalho
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Etapa 6: salve os dados modificados de volta no objeto OLE
Depois de fazer as alterações necessárias, salve a pasta de trabalho modificada novamente no objeto OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Etapa 7: salve a apresentação atualizada
Por fim, salve a apresentação atualizada do PowerPoint.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusão
Atualizar dados de objetos OLE em apresentações do PowerPoint usando Aspose.Slides for Java é um processo direto, uma vez dividido em etapas simples. Este guia orientou você no carregamento de uma apresentação, no acesso e na modificação de dados OLE incorporados e no salvamento da apresentação atualizada. Com essas etapas, você pode gerenciar e atualizar com eficiência o conteúdo incorporado em seus slides do PowerPoint de maneira programática.
## Perguntas frequentes
### O que é um objeto OLE no PowerPoint?
Um objeto OLE (Object Linking and Embedding) permite incorporar conteúdo de outros aplicativos, como planilhas do Excel, em slides do PowerPoint.
### Posso usar Aspose.Slides com outras linguagens de programação?
Sim, Aspose.Slides oferece suporte a várias linguagens, incluindo .NET, Python e C++.
### Preciso do Aspose.Cells para modificar objetos OLE no PowerPoint?
Sim, se o objeto OLE for uma planilha do Excel, você precisará do Aspose.Cells para modificá-lo.
### Existe uma versão de teste do Aspose.Slides?
 Sim, você pode obter um[teste grátis](https://releases.aspose.com/) para testar os recursos do Aspose.Slides.
### Onde posso encontrar a documentação do Aspose.Slides?
 Você pode encontrar documentação detalhada no[Página de documentação do Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

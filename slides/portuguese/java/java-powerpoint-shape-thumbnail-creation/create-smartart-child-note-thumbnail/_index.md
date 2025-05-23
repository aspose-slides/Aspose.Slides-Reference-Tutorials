---
"description": "Aprenda a criar miniaturas de notas filhas SmartArt em Java com Aspose.Slides, aprimorando suas apresentações do PowerPoint sem esforço."
"linktitle": "Criar miniatura de nota infantil SmartArt"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Criar miniatura de nota infantil SmartArt"
"url": "/pt/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Criar miniatura de nota infantil SmartArt

## Introdução
Neste tutorial, exploraremos como criar miniaturas de notas filhas SmartArt em Java usando o Aspose.Slides. O Aspose.Slides é uma poderosa API Java que permite que desenvolvedores trabalhem com apresentações do PowerPoint programaticamente, possibilitando que criem, modifiquem e manipulem slides com facilidade.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado no seu sistema.
2. A biblioteca Aspose.Slides para Java foi baixada e configurada em seu projeto. Você pode baixar a biblioteca em [aqui](https://releases.aspose.com/slides/java/).

## Pacotes de importação
Certifique-se de importar os pacotes necessários na sua classe Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Etapa 1: Configure seu projeto
Certifique-se de ter um projeto Java configurado com a biblioteca Aspose.Slides.
## Etapa 2: Crie uma apresentação
Instanciar o `Presentation` classe para representar o arquivo PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Etapa 3: Adicionar SmartArt
Adicione SmartArt ao slide da sua apresentação:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Etapa 4: Obtenha uma referência de nó
Obtenha a referência de um nó usando seu índice:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Etapa 5: Obtenha a miniatura
Recupere a imagem em miniatura do nó SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Etapa 6: Salvar miniatura
Salve a imagem em miniatura em um arquivo:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Repita essas etapas para cada nó SmartArt, conforme necessário na sua apresentação.

## Conclusão
Neste tutorial, aprendemos a criar miniaturas de notas filhas SmartArt em Java usando o Aspose.Slides. Com esse conhecimento, você pode aprimorar suas apresentações do PowerPoint programaticamente, adicionando elementos visualmente atraentes com facilidade.
## Perguntas frequentes
### Posso usar o Aspose.Slides para manipular arquivos existentes do PowerPoint?
Sim, o Aspose.Slides permite que você modifique arquivos existentes do PowerPoint, incluindo adicionar, remover ou editar slides e seus conteúdos.
### O Aspose.Slides suporta a exportação de slides para diferentes formatos de arquivo?
Com certeza! O Aspose.Slides suporta a exportação de slides para vários formatos, incluindo PDF, imagens e HTML, entre outros.
### O Aspose.Slides é adequado para automação de PowerPoint em nível empresarial?
Sim, o Aspose.Slides foi projetado para lidar com tarefas de automação do PowerPoint de nível empresarial de forma eficiente e confiável.
### Posso criar diagramas SmartArt complexos programaticamente com o Aspose.Slides?
Com certeza! O Aspose.Slides oferece suporte abrangente para criar e manipular diagramas SmartArt de complexidades variadas.
### O Aspose.Slides oferece suporte técnico para desenvolvedores?
Sim, o Aspose.Slides fornece suporte técnico dedicado para desenvolvedores por meio de seus [fórum](https://forum.aspose.com/c/slides/11) e outros canais.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
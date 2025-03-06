---
title: Criar miniatura de nota infantil SmartArt
linktitle: Criar miniatura de nota infantil SmartArt
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar miniaturas de notas infantis SmartArt em Java com Aspose.Slides, aprimorando suas apresentações em PowerPoint sem esforço.
weight: 15
url: /pt/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
Neste tutorial, exploraremos como criar miniaturas de notas infantis SmartArt em Java usando Aspose.Slides. Aspose.Slides é uma API Java poderosa que permite aos desenvolvedores trabalhar com apresentações do PowerPoint de forma programática, permitindo-lhes criar, modificar e manipular slides com facilidade.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Slides para Java baixada e configurada em seu projeto. Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/slides/java/).

## Importar pacotes
Certifique-se de importar os pacotes necessários em sua classe Java:
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
## Etapa 1: configure seu projeto
Certifique-se de ter um projeto Java instalado e configurado com a biblioteca Aspose.Slides.
## Etapa 2: crie uma apresentação
 Instancie o`Presentation` classe para representar o arquivo PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Etapa 3: adicionar SmartArt
Adicione SmartArt ao slide da sua apresentação:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Etapa 4: Obtenha uma referência de nó
Obtenha a referência de um nó usando seu índice:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Etapa 5: obter miniatura
Recupere a imagem em miniatura do nó SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Etapa 6: salvar miniatura
Salve a imagem em miniatura em um arquivo:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Repita essas etapas para cada nó SmartArt conforme necessário na sua apresentação.

## Conclusão
Neste tutorial, aprendemos como criar miniaturas de notas filhas SmartArt em Java usando Aspose.Slides. Com esse conhecimento, você pode aprimorar suas apresentações do PowerPoint de maneira programática, adicionando elementos visualmente atraentes com facilidade.
## Perguntas frequentes
### Posso usar Aspose.Slides para manipular arquivos PowerPoint existentes?
Sim, Aspose.Slides permite modificar arquivos PowerPoint existentes, incluindo adicionar, remover ou editar slides e seu conteúdo.
### O Aspose.Slides oferece suporte à exportação de slides para diferentes formatos de arquivo?
Absolutamente! Aspose.Slides suporta a exportação de slides para vários formatos, incluindo PDF, imagens e HTML, entre outros.
### O Aspose.Slides é adequado para automação de PowerPoint de nível empresarial?
Sim, o Aspose.Slides foi projetado para lidar com tarefas de automação do PowerPoint de nível empresarial de maneira eficiente e confiável.
### Posso criar diagramas SmartArt complexos programaticamente com Aspose.Slides?
Certamente! Aspose.Slides fornece suporte abrangente para criação e manipulação de diagramas SmartArt de complexidades variadas.
### O Aspose.Slides oferece suporte técnico para desenvolvedores?
 Sim, Aspose.Slides fornece suporte técnico dedicado para desenvolvedores por meio de seus[fórum](https://forum.aspose.com/c/slides/11) e outros canais.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

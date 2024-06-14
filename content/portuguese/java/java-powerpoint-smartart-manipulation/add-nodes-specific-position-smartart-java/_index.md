---
title: Adicionar nós em posições específicas no SmartArt usando Java
linktitle: Adicionar nós em posições específicas no SmartArt usando Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Descubra como adicionar nós em posições específicas no SmartArt usando Java com Aspose.Slides. Crie apresentações dinâmicas sem esforço.
type: docs
weight: 16
url: /pt/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---
## Introdução
Neste tutorial, orientaremos você no processo de adição de nós em posições específicas no SmartArt usando Java com Aspose.Slides. SmartArt é um recurso do PowerPoint que permite criar diagramas e gráficos visualmente atraentes.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Slides para Java baixada. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).
3. Conhecimento básico da linguagem de programação Java.

## Importar pacotes
Primeiro, vamos importar os pacotes necessários em nosso código Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Etapa 1: crie uma instância de apresentação
Comece criando uma instância da classe Presentation:
```java
Presentation pres = new Presentation();
```
## Passo 2: Acesse o slide da apresentação
Acesse o slide onde deseja adicionar o SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Etapa 3: adicionar forma SmartArt
Adicione uma forma SmartArt ao slide:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Etapa 4: acessar o nó SmartArt
Acesse o nó SmartArt no índice desejado:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Etapa 5: adicionar nó filho em posição específica
Adicione um novo nó filho em uma posição específica no nó pai:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Etapa 6: adicionar texto ao nó
Defina o texto para o nó recém-adicionado:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Etapa 7: salve a apresentação
Salve a apresentação modificada:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusão
Neste tutorial, você aprendeu como adicionar nós em posições específicas no SmartArt usando Java com Aspose.Slides. Seguindo estas etapas, você pode manipular formas SmartArt programaticamente para criar apresentações dinâmicas.
## Perguntas frequentes
### Posso adicionar vários nós de uma vez?
Sim, você pode adicionar vários nós programaticamente, iterando nas posições desejadas.
### O Aspose.Slides é compatível com todas as versões do PowerPoint?
Aspose.Slides suporta vários formatos de PowerPoint, garantindo compatibilidade com a maioria das versões.
### Posso personalizar a aparência dos nós SmartArt?
Sim, você pode personalizar a aparência dos nós, incluindo tamanho, cor e estilo.
### O Aspose.Slides oferece suporte para outras linguagens de programação?
Sim, Aspose.Slides fornece bibliotecas para várias linguagens de programação, incluindo .NET e Python.
### Existe uma versão de teste disponível para Aspose.Slides?
 Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
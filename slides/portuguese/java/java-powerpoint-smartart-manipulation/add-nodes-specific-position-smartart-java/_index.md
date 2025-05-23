---
"description": "Descubra como adicionar nós em posições específicas no SmartArt usando Java com Aspose.Slides. Crie apresentações dinâmicas sem esforço."
"linktitle": "Adicionar nós em posições específicas no SmartArt usando Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Adicionar nós em posições específicas no SmartArt usando Java"
"url": "/pt/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar nós em posições específicas no SmartArt usando Java

## Introdução
Neste tutorial, guiaremos você pelo processo de adição de nós em posições específicas no SmartArt usando Java com Aspose.Slides. O SmartArt é um recurso do PowerPoint que permite criar diagramas e gráficos visualmente atraentes.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado no seu sistema.
2. Biblioteca Aspose.Slides para Java baixada. Você pode baixá-la em [aqui](https://releases.aspose.com/slides/java/).
3. Conhecimento básico da linguagem de programação Java.

## Pacotes de importação
Primeiro, vamos importar os pacotes necessários em nosso código Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Etapa 1: Criar uma instância de apresentação
Comece criando uma instância da classe Presentation:
```java
Presentation pres = new Presentation();
```
## Etapa 2: acesse o slide da apresentação
Acesse o slide onde deseja adicionar o SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Etapa 3: Adicionar forma SmartArt
Adicione uma forma SmartArt ao slide:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Etapa 4: Acesse o nó SmartArt
Acesse o nó SmartArt no índice desejado:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Etapa 5: Adicionar nó filho em posição específica
Adicione um novo nó filho em uma posição específica no nó pai:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Etapa 6: Adicionar texto ao nó
Defina o texto para o nó recém-adicionado:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Etapa 7: Salve a apresentação
Salve a apresentação modificada:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusão
Neste tutorial, você aprendeu a adicionar nós em posições específicas no SmartArt usando Java com Aspose.Slides. Seguindo esses passos, você poderá manipular formas SmartArt programaticamente para criar apresentações dinâmicas.
## Perguntas frequentes
### Posso adicionar vários nós de uma só vez?
Sim, você pode adicionar vários nós programaticamente iterando sobre as posições desejadas.
### O Aspose.Slides é compatível com todas as versões do PowerPoint?
O Aspose.Slides suporta vários formatos do PowerPoint, garantindo compatibilidade com a maioria das versões.
### Posso personalizar a aparência dos nós SmartArt?
Sim, você pode personalizar a aparência dos nós, incluindo tamanho, cor e estilo.
### Aspose.Slides oferece suporte para outras linguagens de programação?
Sim, o Aspose.Slides fornece bibliotecas para diversas linguagens de programação, incluindo .NET e Python.
### Existe uma versão de teste disponível para o Aspose.Slides?
Sim, você pode baixar uma versão de teste gratuita em [aqui](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
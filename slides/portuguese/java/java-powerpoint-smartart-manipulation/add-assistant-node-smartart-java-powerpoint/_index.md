---
title: Adicionar nó assistente ao SmartArt em Java PowerPoint
linktitle: Adicionar nó assistente ao SmartArt em Java PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como adicionar um nó assistente ao SmartArt em apresentações Java PowerPoint usando Aspose.Slides. Aprimore suas habilidades de edição do PowerPoint.
weight: 17
url: /pt/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar nó assistente ao SmartArt em Java PowerPoint

## Introdução
Neste tutorial, orientaremos você no processo de adição de um nó assistente ao SmartArt em apresentações Java PowerPoint usando Aspose.Slides.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Java Development Kit (JDK): Certifique-se de ter o Java instalado em seu sistema. Você pode baixar e instalar o JDK mais recente em[aqui](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Baixe e instale a biblioteca Aspose.Slides for Java em[esse link](https://releases.aspose.com/slides/java/).

## Importar pacotes
Para começar, importe os pacotes necessários em seu código Java:
```java
import com.aspose.slides.*;
```
## Etapa 1: configurar a apresentação
Comece criando uma instância de Apresentação usando o caminho para seu arquivo PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Etapa 2: percorrer as formas
Percorra todas as formas dentro do primeiro slide da apresentação:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Etapa 3: verifique as formas SmartArt
Verifique se a forma é do tipo SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Etapa 4: percorrer os nós SmartArt
Percorra todos os nós da forma SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Etapa 5: verificar o nó assistente
Verifique se o nó é um nó assistente:
```java
if (node.isAssistant())
```
## Etapa 6: definir o nó do assistente como normal
Se o nó for um nó assistente, configure-o como um nó normal:
```java
node.setAssistant(false);
```
## Etapa 7: Salvar apresentação
Salve a apresentação modificada:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Conclusão
Parabéns! Você adicionou com êxito um nó assistente ao SmartArt em sua apresentação Java PowerPoint usando Aspose.Slides.

## Perguntas frequentes
### Posso adicionar vários nós assistentes a um SmartArt na apresentação?
Sim, você pode adicionar vários nós assistentes repetindo o processo para cada nó.
### Este tutorial funciona para modelos do PowerPoint e do PowerPoint?
Sim, você pode aplicar este tutorial a apresentações e modelos do PowerPoint.
### O Aspose.Slides é compatível com todas as versões do PowerPoint?
Aspose.Slides suporta versões do PowerPoint de 97-2003 até a versão mais recente.
### Posso personalizar a aparência do nó assistente?
Sim, você pode personalizar a aparência usando várias propriedades e métodos fornecidos pelo Aspose.Slides.
### Existe algum limite para o número de nós em um SmartArt?
O SmartArt no PowerPoint oferece suporte a um grande número de nós, mas é recomendável mantê-lo razoável para melhor legibilidade.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

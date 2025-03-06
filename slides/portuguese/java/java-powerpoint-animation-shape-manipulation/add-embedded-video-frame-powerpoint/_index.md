---
title: Adicionar quadro de vídeo incorporado no PowerPoint
linktitle: Adicionar quadro de vídeo incorporado no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como incorporar quadros de vídeo no PowerPoint usando Aspose.Slides for Java com este tutorial passo a passo. Aprimore suas apresentações facilmente.
weight: 21
url: /pt/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar quadro de vídeo incorporado no PowerPoint

## Introdução
Adicionar vídeos às suas apresentações do PowerPoint pode torná-las mais envolventes e informativas. Usando Aspose.Slides for Java, você pode incorporar facilmente vídeos diretamente em seus slides. Neste tutorial, orientaremos você passo a passo no processo, garantindo que você entenda cada parte do código e como ele funciona. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia o ajudará a aprimorar suas apresentações com vídeos incorporados.
## Pré-requisitos
Antes de mergulhar no código, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em sua máquina.
2. Aspose.Slides para Java: Baixe e instale a biblioteca Aspose.Slides para Java.
3. Ambiente de Desenvolvimento Integrado (IDE): Use um IDE como IntelliJ IDEA ou Eclipse para uma melhor experiência de desenvolvimento.
4. Arquivo de vídeo: tenha um arquivo de vídeo que deseja incorporar à sua apresentação do PowerPoint.
## Importar pacotes
Primeiro, você precisará importar os pacotes necessários para trabalhar com Aspose.Slides. Essas importações ajudarão você a gerenciar slides, vídeos e arquivos de apresentação.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Etapa 1: configure seu ambiente
Antes de começar a codificar, certifique-se de que seu ambiente esteja configurado corretamente. Isso envolve a criação dos diretórios necessários e a preparação do arquivo de vídeo.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Crie um diretório se ainda não estiver presente.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Etapa 2: instanciar aula de apresentação
 Crie uma instância do`Presentation` aula. Esta classe representa seu arquivo PowerPoint.
```java
// Instancie a classe Presentation que representa o PPTX
Presentation pres = new Presentation();
```
## Etapa 3: obtenha o primeiro slide
Acesse o primeiro slide da apresentação onde você irá incorporar o vídeo.
```java
// Obtenha o primeiro slide
ISlide sld = pres.getSlides().get_Item(0);
```
## Etapa 4: adicione o vídeo à apresentação
Incorpore o arquivo de vídeo na apresentação. Certifique-se de que o caminho do vídeo esteja especificado corretamente.
```java
// Incorporar vídeo na apresentação
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Etapa 5: adicionar quadro de vídeo ao slide
Crie um quadro de vídeo no slide e defina suas dimensões e posição.
```java
// Adicionar quadro de vídeo
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Etapa 6: configurar propriedades do quadro de vídeo
Defina o vídeo para o quadro de vídeo e defina suas configurações de reprodução, como modo de reprodução e volume.
```java
// Definir vídeo para quadro de vídeo
vf.setEmbeddedVideo(vid);
// Defina o modo de reprodução e o volume do vídeo
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Etapa 7: salve a apresentação
Salve a apresentação com o vídeo incorporado no diretório especificado.
```java
// Grave o arquivo PPTX no disco
pres.save(resultPath, SaveFormat.Pptx);
```
## Etapa 8: limpar recursos
Por fim, descarte o objeto de apresentação para liberar recursos.
```java
// Descarte o objeto de apresentação
if (pres != null) pres.dispose();
```
## Conclusão
Incorporar um vídeo em suas apresentações do PowerPoint usando Aspose.Slides for Java é um processo simples. Seguindo as etapas descritas neste guia, você pode aprimorar suas apresentações com conteúdo de vídeo envolvente. Lembre-se de que a prática leva à perfeição, então experimente incorporar vídeos diferentes e ajustar suas propriedades para ver o que funciona melhor para suas necessidades.
## Perguntas frequentes
### Posso incorporar vários vídeos em um único slide?
Sim, você pode incorporar vários vídeos em um único slide adicionando vários quadros de vídeo.
### Como posso controlar a reprodução do vídeo?
 Você pode controlar a reprodução usando o`setPlayMode` e`setVolume` métodos do`IVideoFrame` aula.
### Quais formatos de vídeo são suportados pelo Aspose.Slides?
Aspose.Slides suporta vários formatos de vídeo, incluindo MP4, AVI e WMV.
### Preciso de uma licença para usar o Aspose.Slides?
Sim, você precisa de uma licença válida para usar o Aspose.Slides. Você pode obter uma licença temporária para avaliação.
### Posso personalizar o tamanho e a posição do quadro do vídeo?
Sim, você pode personalizar o tamanho e a posição definindo os parâmetros apropriados ao adicionar o quadro do vídeo.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

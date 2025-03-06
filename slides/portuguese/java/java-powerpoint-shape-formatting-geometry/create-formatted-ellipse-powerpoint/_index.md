---
title: Crie uma elipse formatada no PowerPoint
linktitle: Crie uma elipse formatada no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar uma elipse formatada no PowerPoint usando Aspose.Slides for Java com nosso guia passo a passo detalhado.
weight: 17
url: /pt/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie uma elipse formatada no PowerPoint

## Introdução
Bem-vindo a este tutorial abrangente sobre como criar uma elipse formatada no PowerPoint usando Aspose.Slides para Java. Aspose.Slides é uma biblioteca poderosa que permite aos desenvolvedores manipular arquivos do PowerPoint programaticamente. Esteja você automatizando a geração de slides ou aprimorando apresentações com formas personalizadas, este guia orientará você em cada etapa, garantindo que você possa adicionar uma elipse perfeitamente formatada aos seus slides com facilidade. Vamos mergulhar e ver como podemos conseguir isso!
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Kit de desenvolvimento Java (JDK): certifique-se de ter o JDK 1.6 ou superior instalado.
2.  Aspose.Slides para Java: Baixe a versão mais recente em[Aspose.Slides para Java](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Use um IDE como IntelliJ IDEA ou Eclipse.
4. Conhecimento básico de Java: É necessária familiaridade com programação Java.
## Importar pacotes
Para começar a usar o Aspose.Slides, você precisa importar os pacotes necessários. Veja como você pode fazer isso:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Etapa 1: configure o diretório do seu projeto
Primeiro, você precisa de um diretório para armazenar seus arquivos do PowerPoint.
### Criar diretório
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Certifique-se de substituir`"Your Document Directory"` com o caminho real onde você deseja armazenar seus arquivos.
## Etapa 2: inicializar a apresentação
Agora, instancie a classe Presentation, que representa o arquivo PowerPoint.
```java
// Instancie a classe Presentation que representa o PPTX
Presentation pres = new Presentation();
```
## Etapa 3: obtenha o primeiro slide
A seguir, obtenha o primeiro slide da apresentação onde você adicionará a elipse.
```java
// Obtenha o primeiro slide
ISlide sld = pres.getSlides().get_Item(0);
```
## Etapa 4: adicione uma forma de elipse
Adicione uma forma automática do tipo elipse ao slide.
```java
// Adicionar forma automática do tipo elipse
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Aqui,`50, 150, 150, 50` são as coordenadas e o tamanho da elipse (posição x, posição y, largura, altura).
## Etapa 5: aplicar formatação à elipse
Agora, aplique alguma formatação à elipse. Definiremos uma cor de preenchimento sólida e uma cor de linha.
### Definir cor de preenchimento
```java
// Aplicar alguma formatação à forma de elipse
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Definir cor e largura da linha
```java
// Aplique alguma formatação à linha da Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Etapa 6: salve a apresentação
Por fim, salve a apresentação no diretório especificado.
```java
// Grave o arquivo PPTX no disco
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Etapa 7: Descarte o objeto de apresentação
Descarte o objeto de apresentação para liberar recursos.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusão
Parabéns! Você criou com sucesso uma elipse formatada em uma apresentação do PowerPoint usando Aspose.Slides para Java. Este tutorial orientou você na configuração do seu projeto, adicionando uma elipse, aplicando formatação e salvando sua apresentação. Com essas habilidades, agora você pode aprimorar seus slides do PowerPoint de maneira programática, tornando suas apresentações mais dinâmicas e visualmente atraentes.
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar e gerenciar apresentações do PowerPoint de forma programática.
### Posso usar Aspose.Slides for Java com qualquer IDE?
Sim, você pode usar Aspose.Slides for Java com qualquer IDE Java como IntelliJ IDEA, Eclipse ou NetBeans.
### Preciso de uma licença para Aspose.Slides?
Sim, Aspose.Slides é um produto comercial e você precisa de uma licença para obter todas as funcionalidades. Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar mais documentação sobre Aspose.Slides for Java?
 Você pode encontrar documentação detalhada no Aspose.Slides for Java[página de documentação](https://reference.aspose.com/slides/java/).
### Existe suporte disponível para Aspose.Slides?
 Sim, Aspose oferece suporte por meio de seu[fórum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

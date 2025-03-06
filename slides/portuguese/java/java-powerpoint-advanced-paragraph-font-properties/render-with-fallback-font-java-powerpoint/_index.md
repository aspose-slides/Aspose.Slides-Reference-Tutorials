---
title: Renderizar com fonte substituta em Java PowerPoint
linktitle: Renderizar com fonte substituta em Java PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como renderizar texto com fontes substitutas em apresentações Java PowerPoint usando Aspose.Slides. Siga este guia passo a passo para uma implementação perfeita.
weight: 13
url: /pt/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
Criar e manipular apresentações do PowerPoint em Java pode ser um desafio, mas com Aspose.Slides você pode fazer isso de forma eficiente. Um recurso crucial é a capacidade de renderizar texto com fontes substitutas. Este artigo fornece um guia passo a passo detalhado sobre como implementar fontes substitutas em seus slides do PowerPoint usando Aspose.Slides para Java.
## Pré-requisitos
Antes de mergulhar na implementação, vamos ter certeza de que você tem tudo o que precisa:
1. Kit de desenvolvimento Java (JDK): certifique-se de ter o JDK instalado em seu sistema.
2.  Aspose.Slides para Java: você pode baixá-lo no[Página de download do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Um IDE como IntelliJ IDEA ou Eclipse tornará seu processo de desenvolvimento mais suave.
4. Dependências: inclua Aspose.Slides nas dependências do seu projeto.
## Importar pacotes
Primeiro, precisamos importar os pacotes necessários em nosso programa Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Vamos dividir o processo em etapas gerenciáveis.
## Etapa 1: configure seu projeto
 Antes de escrever qualquer código, certifique-se de que seu projeto esteja configurado corretamente. Isso inclui adicionar a biblioteca Aspose.Slides ao seu projeto. Você pode fazer isso baixando a biblioteca em[Aspose.Slides para Java](https://releases.aspose.com/slides/java/) e adicionando-o ao seu caminho de construção.
## Etapa 2: inicializar as regras de substituição de fontes
 Você precisa criar uma instância do`IFontFallBackRulesCollection` classe e adicionar regras a ela. Essas regras definem os substitutos de fontes para intervalos Unicode específicos.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma nova instância de uma coleção de regras
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Crie uma série de regras
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Etapa 3: modificar regras substitutas
Nesta etapa, modificaremos as regras substitutas removendo as fontes substitutas existentes e atualizando as regras para intervalos Unicode específicos.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Tentando remover a fonte FallBack “Tahoma” das regras carregadas
    fallBackRule.remove("Tahoma");
    // Atualizar regras para o intervalo especificado
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Remova todas as regras existentes da lista
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Etapa 4: carregar a apresentação
Carregue a apresentação do PowerPoint que deseja modificar.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Etapa 5: atribuir regras substitutas à apresentação
Atribua as regras substitutas preparadas ao gerenciador de fontes da apresentação.
```java
try {
    // Atribuindo a lista de regras preparada para uso
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Renderizando uma miniatura usando a coleção de regras inicializada e salvando-a em PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Etapa 6: salvar e testar
Por fim, salve seu trabalho e teste a implementação para garantir que tudo funcione conforme o esperado. Se você encontrar algum problema, verifique sua configuração e certifique-se de que todas as dependências foram adicionadas corretamente.
## Conclusão
Seguindo este guia, você pode renderizar texto de forma eficiente com fontes substitutas em suas apresentações do PowerPoint usando Aspose.Slides para Java. Esse processo garante que suas apresentações mantenham uma formatação consistente, mesmo que as fontes primárias não estejam disponíveis. Boa codificação!
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma biblioteca que permite aos desenvolvedores criar, modificar e renderizar apresentações do PowerPoint em aplicativos Java.
### Como adiciono Aspose.Slides ao meu projeto?
 Você pode baixar a biblioteca do[Página de download do Aspose.Slides](https://releases.aspose.com/slides/java/) e adicione-o ao caminho de construção do seu projeto.
### O que são fontes substitutas?
Fontes substitutas são fontes alternativas usadas quando a fonte especificada não está disponível ou não oferece suporte a determinados caracteres.
### Posso usar várias regras substitutas?
Sim, você pode adicionar várias regras substitutas para lidar com diferentes intervalos e fontes Unicode.
### Onde posso obter suporte para Aspose.Slides?
 Você pode obter suporte do[Fórum de suporte Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

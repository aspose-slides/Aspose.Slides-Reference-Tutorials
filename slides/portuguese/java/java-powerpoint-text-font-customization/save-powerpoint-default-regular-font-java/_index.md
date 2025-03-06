---
title: Salvar PowerPoint com fonte regular padrão usando Java
linktitle: Salvar PowerPoint com fonte regular padrão usando Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como manipular apresentações do PowerPoint programaticamente usando Aspose.Slides para Java. Domine o manuseio do Java PowerPoint com tutoriais passo a passo.
type: docs
weight: 12
url: /pt/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---
## Introdução
No domínio do desenvolvimento Java, criar e manipular apresentações do PowerPoint de forma programática pode aumentar muito a produtividade e as opções de personalização. Aspose.Slides for Java é uma biblioteca robusta que permite aos desenvolvedores lidar com arquivos PowerPoint de maneira eficiente, oferecendo um conjunto abrangente de recursos, desde modificações simples até apresentações complexas.
## Pré-requisitos
Antes de começar a usar Aspose.Slides para Java, certifique-se de ter os seguintes pré-requisitos configurados:
1. Java Development Kit (JDK): Aspose.Slides for Java requer JDK 1.8 ou superior para funcionar corretamente.
2. Aspose.Slides for Java JAR: Baixe a versão mais recente do Aspose.Slides for Java em[aqui](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Use IntelliJ IDEA, Eclipse ou outro IDE Java de sua escolha.
4. Compreensão básica de Java: É necessária familiaridade com os fundamentos da linguagem de programação Java.

## Importar pacotes
Para começar a usar Aspose.Slides for Java, importe os pacotes necessários:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Isso garante que você tenha acesso a todas as classes e métodos fornecidos por Aspose.Slides for Java.
## Etapa 1: configure seu projeto
Primeiro, crie um novo projeto Java em seu IDE e inclua o arquivo Aspose.Slides for Java JAR no caminho de construção do seu projeto.
## Etapa 2: inicializar o objeto de apresentação
 Instanciar um`Presentation` objeto carregando um arquivo PowerPoint existente (.pptx) do seu diretório local.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Carregar apresentação
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Substituir`"Your Document Directory"` e`"Your Output Directory"` com seus caminhos de arquivo reais.
## Etapa 3: salvar a apresentação com fontes regulares padrão
 Especifique a fonte regular padrão para os formatos de saída (HTML e PDF) usando`HtmlOptions` e`PdfOptions` respectivamente.
```java
try {
    // Opções de salvamento de HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Opções de salvamento de PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Certifique-se de substituir`"Arial Black"` e`"Lucida Console"` com as fontes regulares padrão desejadas.

## Conclusão
Seguindo essas etapas, você aprendeu como manipular apresentações do PowerPoint usando Aspose.Slides for Java de maneira eficaz. Esse recurso permite automatizar tarefas, personalizar apresentações e aprimorar seus aplicativos Java com funcionalidades avançadas de manipulação do PowerPoint.
## Perguntas frequentes
### O Aspose.Slides for Java funciona com versões mais antigas do JDK?
Aspose.Slides for Java requer JDK 1.8 ou superior para compatibilidade.
### Como posso obter licenciamento temporário para Aspose.Slides for Java?
 Você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar documentação mais detalhada sobre Aspose.Slides for Java?
 Explore a documentação abrangente[aqui](https://reference.aspose.com/slides/java/).
### Existe suporte da comunidade disponível para Aspose.Slides for Java?
 Sim, você pode obter suporte da comunidade[aqui](https://forum.aspose.com/c/slides/11).
### Posso experimentar o Aspose.Slides para Java gratuitamente?
 Sim, baixe uma versão de avaliação gratuita[aqui](https://releases.aspose.com/).
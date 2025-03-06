---
title: Exportar apresentação para formato XAML
linktitle: Exportar apresentação para formato XAML
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como exportar apresentações para o formato XAML usando Aspose.Slides for .NET. Crie conteúdo interativo sem esforço!
type: docs
weight: 27
url: /pt/net/presentation-conversion/export-presentation-to-xaml-format/
---

No mundo do desenvolvimento de software, é essencial ter ferramentas que possam simplificar tarefas complexas. Aspose.Slides for .NET é uma ferramenta que permite trabalhar com apresentações do PowerPoint de forma programática. Neste tutorial passo a passo, exploraremos como exportar uma apresentação para o formato XAML usando Aspose.Slides for .NET. 

## Introdução ao Aspose.Slides para .NET

Antes de mergulharmos no tutorial, vamos apresentar brevemente o Aspose.Slides para .NET. É uma biblioteca poderosa que permite aos desenvolvedores criar, modificar, converter e gerenciar apresentações do PowerPoint sem precisar do próprio Microsoft PowerPoint. Com Aspose.Slides for .NET, você pode automatizar diversas tarefas relacionadas a apresentações em PowerPoint, tornando seu processo de desenvolvimento mais eficiente.

## Pré-requisitos

Para acompanhar este tutorial, você precisará do seguinte:

1. Aspose.Slides for .NET: Certifique-se de ter a biblioteca Aspose.Slides for .NET instalada e pronta para uso em seu projeto .NET.

2. Apresentação de origem: tenha uma apresentação do PowerPoint (PPTX) que deseja exportar para o formato XAML. Certifique-se de saber o caminho para esta apresentação.

3. Diretório de saída: escolha um diretório onde deseja salvar os arquivos XAML gerados.

## Etapa 1: configure seu projeto

Nesta primeira etapa montaremos nosso projeto e nos certificaremos de que temos todos os componentes necessários prontos. Certifique-se de ter adicionado uma referência à biblioteca Aspose.Slides for .NET em seu projeto.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Caminho para apresentação de origem
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 Substituir`"Your Document Directory"` pelo caminho para o diretório que contém sua apresentação original do PowerPoint. Além disso, especifique o diretório de saída onde os arquivos XAML gerados serão salvos.

## Etapa 2: exportar a apresentação para XAML

Agora, vamos exportar a apresentação do PowerPoint para o formato XAML. Usaremos Aspose.Slides for .NET para conseguir isso. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Crie opções de conversão
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Defina seu próprio serviço de economia de produção
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Converter slides
    pres.Save(xamlOptions);

    // Salve arquivos XAML em um diretório de saída
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 Neste trecho de código, carregamos a apresentação de origem, criamos opções de conversão XAML e definimos um serviço personalizado de economia de saída usando`NewXamlSaver`. Em seguida, salvamos os arquivos XAML no diretório de saída especificado.

## Etapa 3: classe de proteção XAML personalizada

 Para implementar o protetor XAML personalizado, criaremos uma classe chamada`NewXamlSaver` que implementa o`IXamlOutputSaver` interface.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

Esta classe tratará do salvamento de arquivos XAML no diretório de saída.

## Conclusão

Parabéns! Você aprendeu com sucesso como exportar uma apresentação do PowerPoint para o formato XAML usando Aspose.Slides for .NET. Esta pode ser uma habilidade valiosa ao trabalhar em projetos que envolvem a manipulação de apresentações.

Sinta-se à vontade para explorar mais recursos e capacidades do Aspose.Slides for .NET para aprimorar suas tarefas de automação do PowerPoint.

## Perguntas frequentes

1. ### O que é Aspose.Slides para .NET?
Aspose.Slides for .NET é uma biblioteca .NET para trabalhar programaticamente com apresentações do PowerPoint.

2. ### Onde posso obter o Aspose.Slides para .NET?
 Você pode baixar Aspose.Slides para .NET em[aqui](https://purchase.aspose.com/buy).

3. ### Existe um teste gratuito disponível?
 Sim, você pode obter uma avaliação gratuita do Aspose.Slides for .NET[aqui](https://releases.aspose.com/).

4. ### Como posso obter uma licença temporária do Aspose.Slides for .NET?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

5. ### Onde posso obter suporte para Aspose.Slides for .NET?
 Você pode encontrar suporte e discussões na comunidade[aqui](https://forum.aspose.com/).

 Para mais tutoriais e recursos, visite o[Documentação da API Aspose.Slides](https://reference.aspose.com/slides/net/).
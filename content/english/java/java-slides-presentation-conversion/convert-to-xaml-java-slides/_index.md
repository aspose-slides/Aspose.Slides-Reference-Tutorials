---
title: Convert to XAML in Java Slides
linktitle: Convert to XAML in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 28
url: /java/java-slides-presentation-conversion/convert-to-xaml-java-slides/
---

## Complete Source Code
```java
        // Path to source presentation
        String presentationFileName = RunExamples.getDataDir_Conversion() + "XamlEtalon.pptx";
        Presentation pres = new Presentation(presentationFileName);
        try {
            // Create convertion options
            XamlOptions xamlOptions = new XamlOptions();
            xamlOptions.setExportHiddenSlides(true);
            // Define your own output-saving service
            NewXamlSaver newXamlSaver = new NewXamlSaver();
            xamlOptions.setOutputSaver(newXamlSaver);
            // Convert slides
            pres.save(xamlOptions);
            // Save XAML files to an output directory
            for (Map.Entry<String, String> pair : newXamlSaver.getResults().entrySet()) {
                FileWriter writer = new FileWriter(RunExamples.getOutPath() + pair.getKey(), true);
                writer.append(pair.getValue());
                writer.close();
            }
        } catch(IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
    /**
     * Represents an output saver implementation for transfer data to the external storage.
     */
    static class NewXamlSaver implements IXamlOutputSaver
    {
        private Map<String, String> m_result =  new HashMap<String, String>();
        public Map<String, String> getResults()
        {
            return m_result;
        }
        public void save(String path, byte[] data)
        {
            String name = new File(path).getName();
            m_result.put(name, new String(data, StandardCharsets.UTF_8));
        }
```

---
title: "Localisation d&#39;un Assistant dans plusieurs langues | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistants personnalisés, localiser"
  - "globalisation (C++), Assistants"
  - "localisation (C++), Assistants"
  - "Assistants (C++), localiser"
ms.assetid: 879885c2-fafd-44fd-8032-bf0c301f4f45
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Localisation d&#39;un Assistant dans plusieurs langues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer un Assistant dans toutes les langues prises en charge par Visual Studio.  Par défaut, lors de l'installation de Visual Studio, celui\-ci identifie les paramètres régionaux dans la base de registres et fournit les modèles appropriés pour ces paramètres régionaux.  
  
 Visual Studio utilise des ID de langue pour identifier la prise en charge de langues nécessaire à un Assistant.  Par défaut, l'ID de langue a la valeur décimale de l'entrée du Registre HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage.  Si l'Assistant ne trouve pas d'entrée correspondant à la langue, il utilise l'anglais par défaut \(1033\).  
  
> [!NOTE]
>  Pour obtenir la liste des valeurs décimales de langue, consultez [Prise en charge d'autres langues par l'Assistant](../ide/wizard-support-for-other-languages.md).  
  
 L'ID de langue est spécifié comme paramètre personnalisé dans le [fichier .vsz](../Topic/Configuring%20.Vsz%20Files%20to%20Start%20Wizards.md) et dans les chemins d'accès aux [fichiers HTML](../ide/html-files.md) et [fichiers modèles](../ide/template-files.md).  
  
 Vous devez spécifier des chemins d'accès pour chaque langue pour laquelle vous fournissez un fichier .htm.  
  
## Exemple  
 La définition des paramètres personnalisés suivants dans le fichier .vsz indique la fourniture de fichiers HTML en anglais \(1033\), japonais \(1041\) et allemand \(1031\) :  
  
```  
Param="START_PATH\HTML\1033"  
Param="START_PATH\HTML\1041"  
Param="START_PATH\HTML\1031"  
Param="START_PATH\Templates\1033"  
Param="START_PATH\Templates\1041"  
Param="START_PATH\Templates\1031"  
```  
  
 La définition des paramètres personnalisés ci\-dessus définit la structure de répertoire d'Assistant ci\-dessous :  
  
```  
MyWizard1  
   HTML  
      1033  
         default.htm  
         myEnglishHTML.htm  
      1041  
         default.htm  
         myJapaneseHTML.htm  
      1031  
         default.htm  
         myGermanHTML.htm  
   Templates  
      1033  
         stdafx.h  
         stdafx.cpp  
      1041  
         stdafx.h  
         stdafx.cpp  
      1031  
         stdafx.h  
         stdafx.cpp  
   Images  
      HtmlPage1.bmp  
      HtmlPage2.jpg  
   Scripts  
      Default.js  
```  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [Paramètres personnalisés dans le fichier .Vsz de l'Assistant](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)
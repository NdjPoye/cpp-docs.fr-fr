---
title: "SetCommonPchSettings | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetCommonPchSettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommonPchSettings (méthode)"
ms.assetid: 12f5524b-f654-4222-b979-8ee0d9f58c14
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SetCommonPchSettings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Établit les paramètres d'en\-tête précompilés du projet.  
  
## Syntaxe  
  
```  
  
      function SetCommonPchSettings(   
   oProj    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
## Notes  
 Appelez cette fonction pour définir les paramètres d'en\-tête précompilés du projet.  
  
 Cette fonction affecte à la propriété <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A> les valeurs suivantes :  
  
-   **pchUseUsingSpecific** Utilise le paramètre du compilateur [\/Yu \(Utiliser un en\-tête précompilé\)](../build/reference/yu-use-precompiled-header-file.md).  
  
-   **pchCreateUsingSpecific** Utilise le paramètre du compilateur [\/Yc \(Créer un en\-tête précompilé\)](../build/reference/yc-create-precompiled-header-file.md).  
  
## Exemple  
  
```  
if ((strAppType == "LIB" || ((strAppType == "CONSOLE") &&   
   wizard.FindSymbol(SUPPORT_MFC"))) && !Pch)  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetNoCommonPchSettings(selProj);  
   }  
else  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetcommonPchSettings(selProj);  
   }  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [SetNoPchSettings](../ide/setnopchsettings.md)   
 [AddCommonConfig](../ide/addcommonconfig.md)
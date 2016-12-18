---
title: "SetErrorInfo | Microsoft Docs"
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
  - "SetErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetErrorInfo (méthode)"
ms.assetid: 78bca763-3f90-4e04-b566-b4b7fe2431b1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SetErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette fonction est appelée par [OnWizFinish](../ide/onwizfinish.md) et [CanUseFileName](../ide/canusefilename.md) pour fournir des informations sur les erreurs courantes.  
  
## Syntaxe  
  
```  
  
      function SetErrorInfo(   
   oErrorObj   
);  
```  
  
#### Paramètres  
 *oErrorObj*  
 Objet d'erreur.  
  
## Notes  
 Cette fonction est appelée par [OnWizFinish](../ide/onwizfinish.md) et [CanUseFileName](../ide/canusefilename.md) pour fournir des informations sur les erreurs courantes.  Pour plus d'informations, consultez <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.SetErrorInfo%2A> dans la documentation sur le modèle de l'Assistant Visual C\+\+.  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)
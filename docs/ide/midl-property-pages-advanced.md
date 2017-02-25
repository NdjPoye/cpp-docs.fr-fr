---
title: "Pages de propri&#233;t&#233;s MIDL&#160;: Avanc&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCMidlTool.ErrorCheckBounds"
  - "VC.Project.VCMidlTool.ErrorCheckStubData"
  - "VC.Project.VCMidlTool.ErrorCheckAllocations"
  - "VC.Project.VCMidlTool.CPreprocessOptions"
  - "VC.Project.VCMidlTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCMidlTool.EnableErrorChecks"
  - "VC.Project.VCMidlTool.RedirectOutputAndErrors"
  - "VC.Project.VCMidlTool.ErrorCheckEnumRange"
  - "VC.Project.VCMidlTool.StructMemberAlignment"
  - "VC.Project.VCMidlTool.ErrorCheckRefPointers"
  - "VC.Project.VCMidlTool.ValidateParameters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MIDL, pages de propriétés"
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Pages de propri&#233;t&#233;s MIDL&#160;: Avanc&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La page de propriétés **Avancé** du dossier **MIDL** spécifie les options MIDL suivantes du compilateur MIDL :  
  
-   Activer la vérification des erreurs \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Vérifier les allocations \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Vérifier les limites \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Vérifier la plage d'énumération \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Vérifier les pointeurs de référence \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Vérifier les données stub \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Valider les paramètres \([\/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)\) \*  
  
-   Alignement des membres de struct \([\/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388)\)  
  
-   Rediriger la sortie \([\/o](http://msdn.microsoft.com/library/windows/desktop/aa367351)\)  
  
-   Options de préprocesseur C \([\/cpp\_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318)\)  
  
-   Définitions de prétraitement non définies \([\/U](http://msdn.microsoft.com/library/windows/desktop/aa367373)\)  
  
 \* \/robust est utilisable uniquement lors de la génération d'un ordinateur Windows 2000 ou version ultérieure.  Si vous générez un projet ATL et souhaitez utiliser \/robust, modifiez cette ligne dans le fichier dlldatax.c :  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Pour plus d'informations sur l'accès à la page de propriétés **Avancé** du dossier **MIDL**, consultez [Comment : spécifier des propriétés de projet avec des pages de propriétés](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
 Pour plus d'informations sur l'accès par programme aux options MIDL des projets C\+\+, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## Voir aussi  
 [Pages de propriétés MIDL](../ide/midl-property-pages.md)
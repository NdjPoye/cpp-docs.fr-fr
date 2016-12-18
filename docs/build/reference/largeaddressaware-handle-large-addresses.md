---
title: "/LARGEADDRESSAWARE (G&#233;rer les longues adresses) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.LargeAddressAware"
  - "/largeaddressaware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LARGEADDRESSAWARE (option de l'éditeur de liens)"
  - "LARGEADDRESSAWARE (option de l'éditeur de liens)"
  - "-LARGEADDRESSAWARE (option de l'éditeur de liens)"
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LARGEADDRESSAWARE (G&#233;rer les longues adresses)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## Notes  
 L'option \/LARGEADDRESSAWARE indique à l'Éditeur de liens que l'application gère les adresses de taille supérieure à 2 gigaoctets.  Dans les compilateurs 64 bits, cette option est activée par défaut.  Dans les ordinateurs 32 bits, l'option \/LARGEADDRESSAWARE:NO est activée, sauf si \/LARGEADDRESSAWARE est spécifiée autrement sur la ligne de l'éditeur de liens.  
  
 Si une application a été liée avec cette option, DUMPBIN [\/HEADERS](../../build/reference/headers.md) affichera des informations à cet effet.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Système**.  
  
4.  Modifiez la propriété **Activation des longues adresses**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)
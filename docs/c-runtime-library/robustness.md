---
title: "Robustesse | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "robustesse (CRT)"
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Robustesse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions suivantes de la bibliothèque Runtime C permettent d'améliorer la robustesse de votre programme.  
  
### Fonctions de robustesse à l'exécution  
  
|Fonction|Utilisez|Équivalent .NET Framework|  
|--------------|--------------|-------------------------------|  
|[\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md)|Transfère le contrôle à votre mécanisme de gestion des erreurs si l'opérateur `new` ne peut pas allouer de mémoire.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)|Gère les exceptions Win32 \(exceptions structurées par C\) en tant qu'exceptions typées C\+\+.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installe votre propre fonction d'arrêt qui doit être appelée par [terminate](../c-runtime-library/reference/terminate-crt.md).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installe votre propre fonction d'arrêt qui doit être appelée par [unexpeted](../c-runtime-library/reference/unexpected-crt.md).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)
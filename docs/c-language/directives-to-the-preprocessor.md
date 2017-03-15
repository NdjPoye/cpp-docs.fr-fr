---
title: "Directives vers le pr&#233;processeur | Microsoft Docs"
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
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Directives vers le pr&#233;processeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une « directive » demande au préprocesseur C d'exécuter une action spécifique sur le texte du programme avant la compilation.  Les [directives de préprocesseur](../preprocessor/preprocessor-directives.md) sont décrites en détail dans la section *Référence du préprocesseur*.  L'exemple suivant utilise la directive de préprocesseur `#define` :  
  
```  
#define MAX 100  
```  
  
 Cette instruction indique au compilateur de remplacer chaque occurrence de `MAX` par `100` avant la compilation.  Les directives de préprocesseur du compilateur C sont les suivantes :  
  
|\#define|\#endif|\#ifdef|\#line|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**\#ifndef**|**\#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## Voir aussi  
 [Fichiers sources et programmes sources](../c-language/source-files-and-source-programs.md)
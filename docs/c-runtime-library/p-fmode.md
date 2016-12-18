---
title: "__p__fmode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__p__fmode"
apilocation: 
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__p__fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__p__fmode"
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __p__fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Points à la variable globale `_fmode`, qui spécifie *le mode de traduction* de fichiers par défaut pour les opérations d'E\/S de fichier.  
  
## Syntaxe  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## Valeur de retour  
 Pointeur vers la variable globale `_fmode`.  
  
## Notes  
 La fonction `__p__fmode`est pour un usage interne uniquement, et ne doit pas être appelée à partir du code utilisateur.  
  
 Le fichier en mode de traduction spécifie `binary` ou de la traduction d'`text` pour [\_open](../c-runtime-library/reference/open-wopen.md) et les opérations d'E\/S de [\_pipe](../c-runtime-library/reference/pipe.md).  Pour plus d'informations, consultez [\_fmode](../c-runtime-library/fmode.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_\_p\_\_fmode|stdlib.h|
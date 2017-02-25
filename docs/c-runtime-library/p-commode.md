---
title: "__p__commode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__p__commode"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__p__commode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__p__commode"
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __p__commode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Points à la variable globale `_commode`, qui spécifie *le mode de validation* de fichiers par défaut pour les opérations d'E\/S de fichier.  
  
## Syntaxe  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## Valeur de retour  
 Pointeur vers la variable globale `_commode`.  
  
## Notes  
 La fonction `__p__commode`est pour un usage interne uniquement, et ne doit pas être appelée à partir du code utilisateur.  
  
 Le mode de validation de fichier indique si une donnée critique est écrite sur le disque.  Pour plus d'informations, consultez [fflush](../c-runtime-library/reference/fflush.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_\_p\_\_commode|internal.h|
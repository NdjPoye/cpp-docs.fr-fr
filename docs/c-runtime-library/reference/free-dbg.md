---
title: "_free_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_free_dbg"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_free_dbg"
  - "free_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "blocs de mémoire, désallouer"
  - "libérer de la mémoire"
  - "_free_dbg, fonction"
  - "free_dbg, fonction"
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère un bloc de mémoire dans le tas \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### Paramètres  
 `userData`  
 Pointeur du bloc de mémoire alloué à libérer.  
  
 `blockType`  
 Type de bloc de mémoire alloué à libérer : `_CLIENT_BLOCK`, `_NORMAL_BLOCK`, ou `_IGNORE_BLOCK`.  
  
## Notes  
 La fonction `_free_dbg` est une version Debug de la fonction \_[free](../../c-runtime-library/reference/free.md).  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_free_dbg` est réduit à un appel à `free`.  `free` et `_free_dbg` libèrent un bloc de mémoire dans le tas de base, mais `_free_dbg` s'adapte aux deux fonctionnalités de débogage : la capacité à conserver les blocs dans la liste liée du tas pour simuler des conditions de mémoire insuffisante et un paramètre de type de bloc pour libérer l'allocation spécifique types.  
  
 `_free_dbg` exécute un contrôle de validité sur tous les fichiers spécifiés et tous les emplacements de bloc avant d'exécuter l'opération libre.  L'application n'est pas destinée à fournir ces informations.  Lorsque un bloc de mémoire est libéré, le gestionnaire de tas de débogage vérifie automatiquement l'intégrité des mémoires tampons de chaque côté de la partie de l'utilisateur et envoie un rapport d'erreur si un remplacement a eu lieu.  Si le champ de bits `_CRTDBG_DELAY_FREE_MEM_DF` de l'indicateur [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) est défini, le bloc libéré est rempli avec la valeur 0xDD, assigné `_FREE_BLOCK` de bloc, et conservé dans la liste liée du tas de blocs de mémoire.  
  
 Si une erreur se produit en libérant la mémoire, `errno` est défini avec les informations du système d'exploitation sur la nature de l'échec.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour obtenir des informations sur les types de bloc d'allocation et leur utilisation, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour obtenir des informations sur les différences entre appeler une fonction standard du tas et sa version Debug dans une version debug d'une application, consultez [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Pour un exemple d'utilisation de `_free_dbg`, consultez [crt\_dbg2](http://msdn.microsoft.com/fr-fr/21e1346a-6a17-4f57-b275-c76813089167).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)
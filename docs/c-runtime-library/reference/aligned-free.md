---
title: "_aligned_free | Microsoft Docs"
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
  - "_aligned_free"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "aligned_free"
  - "_aligned_free"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_aligned_free (fonction)"
  - "aligned_free (fonction)"
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## Syntaxe  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### Paramètres  
 `memblock`  
 Pointeur vers le bloc de mémoire qui a été retourné à la fonction `_aligned_malloc` ou `_aligned_offset_malloc`.  
  
## Notes  
 `_aligned_free` est marqué comme`__declspec(noalias)`, ce qui signifie que la fonction est assurée de ne pas modifier les variables globales.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md).  
  
 Cette fonction ne valide pas son paramètre, contrairement aux autres fonctions CRT \_aligned.  Si `memblock` est un pointeur `NULL`, cette fonction n'effectue simplement aucune action.  Elle ne modifie pas `errno` et elle n'appelle pas le gestionnaire de paramètre non valide.  Si une erreur se produit dans la fonction en raison de l'utilisation de fonctions \_aligned pour allouer le bloc de mémoire ou qu'un mauvais alignement de la mémoiree advient à cause de problèmes non prévus, la fonction génère un rapport de débogage à partir de [\_RPT, \_RPTF, \_RPTW, \_RPTFW, macros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_free`|\<malloc.h\>|  
  
## Exemple  
 Pour plus d'informations, consultez [aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Alignement des données](../../c-runtime-library/data-alignment.md)
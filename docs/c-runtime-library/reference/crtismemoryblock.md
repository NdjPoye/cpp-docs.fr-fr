---
title: "_CrtIsMemoryBlock | Microsoft Docs"
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
  - "_CrtIsMemoryBlock"
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
  - "CrtlsMemoryBlock"
  - "_CrtIsMemoryBlock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtIsMemoryBlock (fonction)"
  - "CrtIsMemoryBlock (fonction)"
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtIsMemoryBlock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie qu'un bloc de mémoire spécifié est dans le tas local et qu'il possède un identificateur de bloc de tas de débogage valide \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### Paramètres  
 \[in\] `userData`  
 Pointeur du début du bloc de mémoire à vérifier.  
  
 \[in\] `size`  
 Taille des données spécifiées en octets ;  
  
 \[out\] `requestNumber`  
 Pointeur du numéro d'allocation du bloc ou `NULL`.  
  
 \[out\] `filename`  
 Le pointeur du nom du fichier source qui a demandé le block ou `NULL`.  
  
 \[out\] `linenumber`  
 Pointeur du numéro de ligne dans le fichier source ou `NULL`.  
  
## Valeur de retour  
 `_CrtIsMemoryBlock` retourne `TRUE` si le bloc de mémoire spécifié se trouve dans le tas local et possède un identificateur de bloc de tas de débogage valide ; sinon, la fonction retourne `FALSE`.  
  
## Notes  
 La fonction `_CrtIsMemoryBlock` vérifie qu'un bloc de mémoire spécifié se trouve dans le tas local de l'application et qu'il possède un identificateur de bloc valide.  Cette fonction peut également être utilisée pour obtenir le numéro de commande d'allocation d'objet et le nom du fichier source\/numéro de ligne où l'allocation de bloc de mémoire a été initialement demandée.  Passer des valeurs non null pour les paramètres`requestNumber`, `filename`, ou `_CrtIsMemoryBlock` implique que `linenumber` définit ces paramètres avec les valeurs dans l'en\-tête du débogage du bloc de mémoire s'il trouve le bloc dans le tas local.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, Les appels de `_CrtIsMemoryBlock` sont supprimés pendant le prétraitement.  
  
 Si `_CrtIsMemoryBlock` échoue, il retourne `FALSE` et les paramètres de sortie sont initialisés aux valeurs par défaut : `requestNumber` et `lineNumber` ont la valeur 0 et `filename` a la valeur `NULL`.  
  
 Puisque cette fonction retourne `TRUE` ou `FALSE`, elle peut être passée à l'une des macros [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) pour créer un mécanisme simple de gestion des erreurs de débogage  L'exemple suivant provoque un échec d'assertion si l'adresse spécifiée ne se trouve pas dans le tas local :  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 Pour plus d'informations sur la façon dont `_CrtIsMemoryBlock` peut être utilisé avec d'autres fonctions et des macros de débogage, consultez [Macros pour la création de rapports](../Topic/Macros%20for%20Reporting.md).  Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Consultez l'exemple pour le sujet [\_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
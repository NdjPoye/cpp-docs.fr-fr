---
title: "_CrtCheckMemory | Microsoft Docs"
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
  - "_CrtCheckMemory"
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
  - "CrtCheckMemory"
  - "_CrtCheckMemory"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtCheckMemory (fonction)"
  - "CrtCheckMemory (fonction)"
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtCheckMemory
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Confirme l'intégrité des blocs de mémoire alloués dans la pile de débogage \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## Valeur de retour  
 En cas de réussite, `_CrtCheckMemory` renvoie TRUE; sinon, la fonction renvoie FALSE.  
  
## Notes  
 La fonction `_CrtCheckMemory` valide la mémoire allouée par le gestionnaire de la pile de débogage en vérifiant la pile de base sous\-jacente et en examinant chaque bloc de mémoire.  Si une incohérence de mémoire ou une erreur se produit dans le tas de base sous\-jacent, les informations d'en\-tête de débogage, ou les mémoires tampons de remplacement, `_CrtCheckMemory` génère un rapport de débogage avec les informations décrivant la condition d'erreur.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, Les appels de `_CrtCheckMemory` sont supprimés pendant le prétraitement.  
  
 Le comportement de `_CrtCheckMemory` peut être contrôlé en définissant les champs de bits de l'indicateur [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) en utilisant la fonction [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md).  Tournant le champ de bits **\_CRTDBG\_CHECK\_ALWAYS\_DF** ON entraine que `_CrtCheckMemory` est appelé à chaque fois qu'une opération d'allocation de mémoire est demandée.  Bien que cette méthode ralentisse l'exécution, il est utile pour intercepter les erreurs rapidement.  Tournant le champ de bits **\_CRTDBG\_ALLOC\_MEM\_DF** OFF entraine `_CrtCheckMemory` de ne pas vérifier la pile et ne pas renvoyer immédiatement **VRAI**.  
  
 Cette fonction renvoie **VRAI** ou **FAUX**, elle peut être passée à une des macros [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) pour créer un mécanisme simple de gestion des erreurs d'erreur de débogage.  L'exemple suivant provoque un échec d'assertion si l'altération est détectée dans la pile:  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 Pour plus d'informations sur la façon dont `_CrtCheckMemory` peut être utilisé avec d'autres fonctions de débogage, consultez [Fonctions de création de rapports sur l'état du tas](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  Pour une présentation de gestion de la mémoire et de la pile de débogage, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtCheckMemory`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Pour un exemple d'utilisation de `_CrtCheckMemory`, consultez [crt\_dbg1](http://msdn.microsoft.com/fr-fr/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## Équivalent .NET Framework  
 [System::Diagnostics::PerformanceCounter](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)
---
title: "_CrtDbgBreak | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDbgBreak"
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
  - "_CrtDbgBreak"
  - "CrtDbgBreak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtDbgBreak (fonction)"
  - "CrtDbgBreak (fonction)"
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtDbgBreak
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un point d'arrêt sur une ligne de code spécifique. \(utilisé en mode débogage\)  
  
## Syntaxe  
  
```  
void _CrtDbgBreak( void );  
```  
  
## Valeur de retour  
 Aucune valeur de retour.  
  
## Notes  
 La fonction `_CrtDbgBreak` définit un point d'arrêt de débogage sur la ligne de code spécifique où la fonction réside.  Cette fonction est utilisée en mode débogage et dépend de `_DEBUG` défini précédemment.  
  
 Pour plus d'informations sur l'utilisation d'autres fonctions exécution raccordement et comment écrire vos propres fonctions de raccordement définies par le client, consultez [Écrire vos propres fonctions de raccordement de débogage](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtDbgBreak`|\<CRTDBG.h\>|  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_\_debugbreak](../../intrinsics/debugbreak.md)
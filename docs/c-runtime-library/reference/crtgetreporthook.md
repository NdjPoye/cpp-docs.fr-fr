---
title: "_CrtGetReportHook | Microsoft Docs"
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
  - "_CrtGetReportHook"
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
  - "CrtGetReportHook"
  - "_CrtGetReportHook"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtGetReportHook (fonction)"
  - "_CrtGetReportHook (fonction)"
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtGetReportHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la fonction de rapport définie par le client pour la connecter au moment de l'exécution C pour le processus de création de débogage \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
_CRT_REPORT_HOOK _CrtGetReportHook( void );  
```  
  
## Valeur de retour  
 Renvoie la fonction actuelle de rapport définie par le client précédent.  
  
## Notes  
 `_CrtGetReportHook` permet à une application de récupérer la fonction de rapport actuelle du processus de création de bibliothèque de débogage du runtime C.  
  
 Pour plus d'informations sur l'utilisation d'autres fonctions runtime raccordement\- capables et écrire vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtGetReportHook`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Pour un exemple d'utilisation de `_CrtSetReportHook`, consultez [rapport](http://msdn.microsoft.com/fr-fr/f6e08c30-6bd9-459a-830a-56deec0d2051).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)
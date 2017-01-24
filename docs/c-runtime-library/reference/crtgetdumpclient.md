---
title: "_CrtGetDumpClient | Microsoft Docs"
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
  - "_CrtGetDumpClient"
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
  - "CrtGetDumpClient"
  - "_CrtGetDumpClient"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtGetDumpClient (fonction)"
  - "CrtGetDumpClient (fonction)"
ms.assetid: 9051867f-341b-493b-b53d-45d2b454a3ad
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtGetDumpClient
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la fonction définie par l'application actuelle pour faire un dump des blocs mémoire de type `_CLIENT_BLOCK` \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
_CRT_DUMP_CLIENT _CrtGetDumpClient( void );  
```  
  
## Valeur de retour  
 Renvoie la routine de dump actuelle.  
  
## Notes  
 La fonction `_CrtGetDumpClient` récupère la fonction de raccordement actuelle pour faire un dump des objets stockés dans les blocs mémoire de `_CLIENT_BLOCK` pour le processus d'image mémoire de débogage du runtime C.  
  
 Pour plus d'informations sur l'utilisation d'autres fonctions runtime raccordement\- capables et écrire vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtGetDumpClient`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [\_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md)
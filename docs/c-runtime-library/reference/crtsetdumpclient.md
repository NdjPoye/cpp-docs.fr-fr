---
title: "_CrtSetDumpClient | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetDumpClient"
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
  - "_CrtSetDumpClient"
  - "CrtSetDumpClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetDumpClient (fonction)"
  - "CrtSetDumpClient (fonction)"
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtSetDumpClient
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installe une fonction définie par l'application pour faire un dump des blocs de mémoire de type `_CLIENT_BLOCK` \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### Paramètres  
 `dumpClient`  
 Nouvelle fonction définie par le client d'image mémoire à connecter dans le processus d'image mémoire de débogage du runtime C.  
  
## Valeur de retour  
 Retourne la fonction cliente de dump de bloc précédemment définie.  
  
## Notes  
 La fonction `_CrtSetDumpClient` permet à l'application de raccorder sa propre fonction pour faire un dump des objets stockés dans les blocs de mémoire de `_CLIENT_BLOCK` dans le processus d'image mémoire de débogage du runtime C.  En conséquence, chaque fois qu'une fonction de vidage du débogage comme [\_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) ou [\_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) fait un dump d'un bloc de mémoire `_CLIENT_BLOCK`, la fonction du dump de l'application est également appelée.  `_CrtSetDumpClient` fournit à une application une méthode simple de détection des fuites de mémoire et de validation ou de stockage du contenu des données stockées dans des blocs `_CLIENT_BLOCK`.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, Les appels de `_CrtSetDumpClient` sont supprimés pendant le prétraitement.  
  
 La fonction `_CrtSetDumpClient` installe la nouvelle fonction définie par l'application de dump spécifiée dans `dumpClient` et retourne la fonction définie précédemment de dump.  Un exemple d'une fonction cliente de dump de bloc est la suivante :  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 L'argument `userPortion` est un pointeur du début de la partie des données de l'utilisateur du bloc de mémoire et `blockSize` spécifie la taille du bloc de mémoire allouée en octets.  La fonction cliente de dump de bloc doit retourner `void`.  Le pointeur vers la fonction de dump cliente passé à `_CrtSetDumpClient` est du type `_CRT_DUMP_CLIENT`, comme défini dans Crtdbg.h:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 Pour plus d'informations sur les fonctions qui opèrent sur les blocs de mémoire de type `_CLIENT_BLOCK`, consultez [Fonctions de raccordement de bloc client](../Topic/Client%20Block%20Hook%20Functions.md).  La fonction [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md) peut être utilisée pour retourner des informations sur les types et des sous\-types de bloc.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [\_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)
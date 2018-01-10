---
title: _CrtSetDumpClient | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetDumpClient
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs: C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf64ca280998ac25adbb380ff8245a0b8eecf797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient
Installe une fonction définie par l’application pour vider des blocs de mémoire de type `_CLIENT_BLOCK` (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dumpClient`  
 Nouvelle fonction de vidage de mémoire définie par le client à raccorder au processus de vidage de mémoire de débogage du runtime C  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de vidage de bloc définie par le client.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtSetDumpClient` permet à l’application de raccorder sa propre fonction pour vider des objets stockés dans des blocs de mémoire `_CLIENT_BLOCK` dans le processus de vidage de mémoire de débogage du runtime C. Ainsi, chaque fois qu’une fonction de vidage de débogage, telle que [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) ou [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md), vide un bloc de mémoire `_CLIENT_BLOCK`, la fonction de vidage de l’application est également appelée. `_CrtSetDumpClient` fournit à une application une méthode simple pour détecter les fuites de mémoire et pour valider le contenu des données stockées dans des blocs `_CLIENT_BLOCK` ou pour créer des rapports à partir de ce contenu. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtSetDumpClient` sont supprimés durant le prétraitement.  
  
 La fonction `_CrtSetDumpClient` installe la nouvelle fonction de vidage définie par l’application spécifiée dans `dumpClient` et retourne la fonction de vidage définie. Voici un exemple de fonction de vidage de bloc client :  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 L’argument `userPortion` est un pointeur désignant le début de la partie des données utilisateur du bloc de mémoire et `blockSize` spécifie la taille du bloc de mémoire alloué en octets. La fonction de vidage de bloc client doit retourner `void`. Le pointeur désignant la fonction de vidage client passé à `_CrtSetDumpClient` est du type `_CRT_DUMP_CLIENT`, comme défini dans Crtdbg.h :  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 Pour plus d’informations sur les fonctions qui opèrent sur des blocs de mémoire de type `_CLIENT_BLOCK`, consultez [Fonctions de raccordement de bloc client](/visualstudio/debugger/client-block-hook-functions). La fonction [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md) peut être utilisée pour retourner des informations sur les types et sous-types de blocs.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)
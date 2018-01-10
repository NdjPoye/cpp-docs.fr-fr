---
title: _endthread, _endthreadex | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs: C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5abe2f0aa2f62048fefb2f79614e018fbdb51e08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex
Termine un thread ; `_endthread` termine un thread créé par `_beginthread` et  `_endthreadex` termine un thread créé par `_beginthreadex`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _endthread( void );  
void _endthreadex(   
   unsigned retval   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `retval`  
 Code de sortie de thread.  
  
## <a name="remarks"></a>Notes  
 Vous pouvez appeler `_endthread` ou `_endthreadex` explicitement pour terminer un thread ; cependant, `_endthread` ou `_endthreadex` est appelé automatiquement quand le thread retourne de la routine passée en tant que paramètre à `_beginthread` ou `_beginthreadex`. Terminer un thread avec un appel à `endthread` ou `_endthreadex` permet de garantir une récupération correcte des ressources allouées pour le thread.  
  
> [!NOTE]
>  Pour un fichier exécutable lié à Libcmt.lib, n’appelez pas l’API [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) Win32, car elle empêche le système runtime de récupérer les ressources allouées. `_endthread` et `_endthreadex` récupèrent les ressources de thread allouées, puis appellent `ExitThread`.  
  
 `_endthread` ferme automatiquement le handle du thread. (Ce comportement diffère de l'API Win32 `ExitThread`.) Ainsi, quand vous utilisez `_beginthread` et `_endthread`, ne fermez pas explicitement le handle du thread en appelant l’API [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) Win32.  
  
 Comme l’API Win32 `ExitThread` , `_endthreadex` ne ferme pas le handle du thread. Ainsi, quand vous utilisez `_beginthreadex` et `_endthreadex`, vous devez fermer le handle du thread en appelant l'API Win32 `CloseHandle`.  
  
> [!NOTE]
>  `_endthread` et `_endthreadex` empêchent l'appel des destructeurs C++ en attente dans le thread.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_endthread`|\<process.h>|  
|`_endthreadex`|\<process.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions multithread des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md) .  
  
## <a name="example"></a>Exemple  
 Voir l'exemple pour [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)
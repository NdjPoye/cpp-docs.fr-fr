---
title: set_terminate (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_terminate
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
f1_keywords: set_terminate
dev_langs: C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 099cb340f821f04c3a5f84ccef7e3e9649482cd6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="setterminate-crt"></a>set_terminate (CRT)
Installe votre propre routine d’arrêt que doit appeler `terminate`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `termFunction`  
 Pointeur désignant une fonction d’arrêt que vous écrivez.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers la précédente fonction inscrite par `set_terminate`, si bien qu’elle peut être restaurée ultérieurement. Si aucune fonction précédente n’a été définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être NULL.  
  
## <a name="remarks"></a>Notes  
 La fonction `set_terminate` installe `termFunction` comme fonction appelée par `terminate`. `set_terminate` est utilisée avec la gestion des exceptions C++ et peut être appelée à tout moment dans votre programme avant que l’exception soit levée. `terminate` appelle `abort` par défaut. Vous pouvez modifier ce comportement par défaut en écrivant votre propre fonction d’arrêt et en appelant `set_terminate` avec le nom de votre fonction comme argument. `terminate` appelle la dernière fonction donnée comme argument de `set_terminate`. Après avoir effectué les tâches de nettoyage souhaitées, `termFunction` doit fermer le programme. S’il ne se ferme pas (avec un retour vers l’appelant), la fonction `abort` est appelée.  
  
 Dans un environnement multithread, les fonctions d’arrêt sont gérées séparément pour chaque thread. Chaque nouveau thread doit installer sa propre fonction d’arrêt. Par conséquent, chaque thread est responsable de sa propre gestion des arrêts.  
  
 Le type `terminate_function` est défini dans EH.H comme pointeur désignant une fonction d’arrêt définie par l’utilisateur, `termFunction` qui retourne `void`. Votre fonction personnalisée `termFunction` ne peut prendre aucun argument et ne doit pas revenir à son appelant. Si c’est le cas, la fonction `abort` est appelée. Une exception ne peut pas être levée à partir de `termFunction`.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  La fonction `set_terminate` opère uniquement en dehors du débogueur.  
  
 Il existe un seul gestionnaire `set_terminate` pour l’ensemble des DLL ou EXE liés de manière dynamique ; même si vous appelez `set_terminate`, votre gestionnaire peut être remplacé par un autre ou vous pouvez remplacer un gestionnaire défini par une autre DLL ou un autre EXE.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`set_terminate`|\<eh.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [terminate](../../c-runtime-library/reference/terminate-crt.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de gestion des exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)
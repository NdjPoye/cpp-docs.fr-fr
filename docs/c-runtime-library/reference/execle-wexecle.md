---
title: _execle, _wexecle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execle
- _wexecle
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wexecle
- _execle
- _wexecle
dev_langs:
- C++
helpviewer_keywords:
- wexecle function
- execle function
- _wexecle function
- _execle function
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: a9bda57c9520b46c3c28b492cf9a7f32637dffd8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="execle-wexecle"></a>_execle, _wexecle
Charge et exécute les nouveaux processus enfant.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
intptr_t _execle(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexecle(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const char *const *envp   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `cmdname`  
 Chemin d’accès du fichier à exécuter.  
  
 `arg0, ... argn`  
 Liste des pointeurs désignant les paramètres.  
  
 `envp`  
 Tableau de pointeurs vers les paramètres d'environnement.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, ces fonctions ne retournent pas au processus appelant. Une valeur de retour de -1 indique une erreur, auquel cas la `errno` variable globale est définie.  
  
|Valeur `errno`|Description|  
|-------------------|-----------------|  
|`E2BIG`|L’espace nécessaire aux arguments et aux paramètres d’environnement dépasse 32 Ko.|  
|`EACCES`|Le fichier spécifié possède un verrou ou une violation de partage.|  
|`EINVAL`|Paramètre non valide.|  
|`EMFILE`|Trop de fichiers sont ouverts. (Le fichier spécifié doit être ouvert pour déterminer s'il est exécutable.)|  
|`ENOENT`|Fichier ou chemin d’accès introuvable.|  
|`ENOEXEC`|Le fichier spécifié n'est pas exécutable ou a un format de fichier exécutable non valide.|  
|`ENOMEM`|Mémoire insuffisante pour exécuter le nouveau processus ; la mémoire disponible est endommagée ; ou il existe un bloc non valide, ce qui indique que le processus appelant n'a pas été alloué correctement.|  
  
 Pour plus d’informations sur ces codes de retour, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions charge et exécute un nouveau processus, passe chaque argument de ligne de commande en tant que paramètre distinct et passe un tableau de pointeurs aux paramètres d’environnement.  
  
 Les fonctions `_execle` valident leurs paramètres. Si `cmdname` ou `arg0` est un pointeur null ou une chaîne vide, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent -1. Aucun nouveau processus n'est lancé.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|En-tête facultatif|  
|--------------|---------------------|---------------------|  
|`_execle`|\<process.h>|\<errno.h>|  
|`_wexecle`|\<process.h> ou \<wchar.h>|\<errno.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple dans [_exec, _wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)

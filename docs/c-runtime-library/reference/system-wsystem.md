---
title: system, _wsystem | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- system
- _wsystem
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
- _tsystem
- _wsystem
dev_langs: C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c470717d48836fd405e98f5fccca222e87a9c33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="system-wsystem"></a>system, _wsystem
Exécute une commande.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `command`  
 Commande à exécuter.  
  
## <a name="return-value"></a>Valeur de retour  
 Si `command` a la valeur `NULL` et que l'interpréteur de commande est trouvé, retourne une valeur différente de zéro. Si l'interpréteur de commande est introuvable, retourne 0 et attribue à `errno` la valeur `ENOENT`. Si `command` n'a pas la valeur `NULL`, `system` retourne la valeur retournée par l'interpréteur de commande. Elle retourne la valeur 0 uniquement si l'interpréteur de commande retourne la valeur 0. Une valeur de retour de - 1 indique une erreur et `errno` est définie à une des valeurs suivantes :  
  
 `E2BIG`  
 La liste d’arguments (qui est dépendante du système) est trop grande.  
  
 `ENOENT`  
 L'interpréteur de commande est introuvable.  
  
 `ENOEXEC`  
 Le fichier interpréteur de commande ne peut pas être exécuté, car le format n'est pas valide.  
  
 `ENOMEM`  
 Mémoire insuffisante pour exécuter la commande ; la mémoire disponible est endommagée ; ou il existe un bloc non valide, ce qui indique que le processus qui effectue l'appel n'a pas été alloué correctement.  
  
 Pour plus d’informations sur ces codes de retour, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `system` passe `command` à l'interpréteur de commande, qui exécute la chaîne en tant que commande du système d'exploitation. `system` utilise les variables d'environnement `COMSPEC` et `PATH` pour localiser le fichier interpréteur de commande CMD.exe. Si `command` a la valeur `NULL`, la fonction vérifie uniquement si l'interpréteur de commande existe.  
  
 Vous devez explicitement vider (à l'aide de `fflush` ou `_flushall`) ou fermer tout flux avant d'appeler `system`.  
  
 `_wsystem` est une version à caractères larges de `system` ; l'argument `command` de `_wsystem` est une chaîne à caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`system`|\<process.h> ou \<stdlib.h>|  
|`_wsystem`|\<process.h> ou \<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise `system` pour taper (type) un fichier texte.  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## <a name="input-crtsystemtxt"></a>Entrée : crt_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Sortie  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de processus et d’environnement](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_spawn, _wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)
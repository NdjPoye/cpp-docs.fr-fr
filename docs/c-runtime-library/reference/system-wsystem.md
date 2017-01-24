---
title: "system, _wsystem | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "system"
  - "_wsystem"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tsystem"
  - "_wsystem"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tsystem (fonction)"
  - "_wsystem (fonction)"
  - "interpréteur de commande"
  - "commandes, exécuter"
  - "system (fonction)"
  - "tsystem (fonction)"
  - "wsystem (fonction)"
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system, _wsystem
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Exécute une commande.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### Paramètres  
 `command`  
 Commande à exécuter.  
  
## Valeur de retour  
 Si `command` a la valeur `NULL` et que l'interpréteur de commande est trouvé, retourne une valeur différente de zéro.  Si l'interpréteur de commande est introuvable, retourne 0 et attribue à `errno` la valeur `ENOENT`.  Si `command` n'a pas la valeur `NULL`, `system` retourne la valeur retournée par l'interpréteur de commande.  Elle retourne la valeur 0 uniquement si l'interpréteur de commande retourne la valeur 0.  La valeur de retour \-1 indique une erreur et `errno` prend l'une des valeurs suivantes :  
  
 `E2BIG`  
 La liste d'arguments \(qui est dépendante du système\) est trop grande.  
  
 `ENOENT`  
 L'interpréteur de commande est introuvable.  
  
 `ENOEXEC`  
 Le fichier interpréteur de commande ne peut pas être exécuté, car le format n'est pas valide.  
  
 `ENOMEM`  
 Mémoire insuffisante pour exécuter la commande ; la mémoire disponible est endommagée ; ou il existe un bloc non valide, ce qui indique que le processus qui effectue l'appel n'a pas été alloué correctement.  
  
 Pour plus d'informations sur ces codes de retour, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `system` passe `command` à l'interpréteur de commande, qui exécute la chaîne en tant que commande du système d'exploitation.  `system` utilise les variables d'environnement `COMSPEC` et `PATH` pour localiser le fichier interpréteur de commande CMD.exe.  Si `command` a la valeur `NULL`, la fonction vérifie uniquement si l'interpréteur de commande existe.  
  
 Vous devez explicitement vider \(à l'aide de `fflush` ou `_flushall`\) ou fermer tout flux avant d'appeler `system`.  
  
 `_wsystem` est une version à caractères larges de `system` ; l'argument `command` de `_wsystem` est une chaîne à caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`system`|\<process.h\> ou \<stdlib.h\>|  
|`_wsystem`|\<process.h\>, \<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Cet exemple utilise `system` pour taper \(type\) un fichier texte.  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## Entrée : crt\_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### Sortie  
  
```  
Line one.  
Line two.  
```  
  
## Équivalent .NET Framework  
  
-   [Classe System::Diagnostics::ProcessStartInfo](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
-   [Classe System::Diagnostics::Process](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)
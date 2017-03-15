---
title: "_set_error_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_error_mode"
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
  - "set_error_mode"
  - "_set_error_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_error_mode (fonction)"
  - "set_error_mode (fonction)"
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _set_error_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie `__error_mode` pour déterminer un emplacement autre que celui utilisé par défaut dans lequel le Runtime C écrit un message d'erreur pour une erreur qui risque de mettre fin au programme.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _set_error_mode(  
   int modeval   
);  
```  
  
#### Paramètres  
 `modeval`  
 Destination des messages d'erreur.  
  
## Valeur de retour  
 Retourne l'ancien paramètre ou \-1 si une erreur se produit.  
  
## Notes  
 Contrôle l'intercepteur de sortie d'erreurs en définissant la valeur de `__error_mode`.  Par exemple, vous pouvez diriger la sortie vers une erreur standard ou utiliser l'API `MessageBox`.  
  
 Le paramètre `modeval` peut avoir l'une des valeurs suivantes.  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_OUT_TO_DEFAULT`|L'intercepteur d'erreurs est déterminé par `__app_type`.|  
|`_OUT_TO_STDERR`|L'intercepteur d'erreurs est une erreur standard.|  
|`_OUT_TO_MSGBOX`|L'intercepteur d'erreurs est une boîte de message.|  
|`_REPORT_ERRMODE`|Fait état de la valeur actuelle de `__error_mode`.|  
  
 Si la valeur transmise est différente de celles répertoriées, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `_set_error_mode` affecte à `errno` la valeur `EINVAL` et retourne \-1.  
  
 Quand il est utilisé avec [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md), `_set_error_mode` affiche l'instruction en échec dans la boîte de dialogue et vous donne la possibilité de choisir le bouton `Ignore` pour permettre la poursuite de l'exécution du programme.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_error_mode`|\<stdlib.h\>|  
  
## Exemple  
  
```  
// crt_set_error_mode.c  
// compile with: /c  
#include <stdlib.h>  
#include <assert.h>  
  
int main()  
{  
   _set_error_mode(_OUT_TO_STDERR);  
   assert(2+2==5);  
}  
```  
  
  **Assertion failed: 2\+2\=\=5, file crt\_set\_error\_mode.c, line 8**  
**This application has requested the Runtime to terminate it in an unusual way.  Please contact the application's support team for more information.**    
## Voir aussi  
 [assert \(macro\), \_assert, \_wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)
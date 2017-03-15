---
title: "_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
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
  - "set_invalid_parameter_handler"
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "gestionnaire de paramètre non valide"
  - "set_invalid_parameter_handler (fonction)"
  - "_set_invalid_parameter_handler (fonction)"
  - "_set_thread_local_invalid_parameter_handler (fonction)"
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit une fonction à appeler lorsque la bibliothèque CRT détecte un argument non valide.  
  
## Syntaxe  
  
```  
_invalid_parameter_handler _set_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
```  
  
#### Paramètres  
 \[in\] `pNew`  
 Le pointeur de fonction pour le nouveau gestionnaire de paramètre non valide.  
  
## Valeur de retour  
 Pointeur vers le Gestionnaire de paramètre non valide avant l’appel.  
  
## Notes  
 Plusieurs fonctions de runtime C vérifient la validité d’arguments passés à eux. Si un argument non valide est passé, la fonction peut définir le `errno` retournent un code d’erreur ou le numéro d’erreur. Dans ce cas, le Gestionnaire de paramètre non valide est également appelé. Le runtime C fournit un gestionnaire de globale de paramètres non valides par défaut qui termine le programme et affiche un message d’erreur d’exécution. Vous pouvez utiliser la `_set_invalid_parameter_handler` pour définir votre propre fonction en tant que le Gestionnaire de paramètre non valide global. La bibliothèque C runtime prend également en charge un gestionnaire de paramètre non valide de thread local. Si un gestionnaire de paramètre de thread local est défini dans un thread à l’aide de `_set_thread_local_invalid_parameter_handler`, les fonctions runtime C appelées depuis le thread utilisent ce gestionnaire au lieu du gestionnaire global. Une seule fonction peut être spécifiée comme gestionnaire global argument non valide à la fois. Une seule fonction peut être spécifiée en tant que le Gestionnaire d’argument non valide locales de thread par thread, mais différents threads peuvent avoir différents gestionnaires de thread local. Cela vous permet de modifier le gestionnaire utilisé dans une partie de votre code sans affecter le comportement des autres threads.  
  
 Lorsque le runtime appelle la fonction de paramètre non valide, cela signifie généralement qu’une erreur non récupérable s’est produite. La fonction de gestionnaire de paramètre non valide que vous fournissez doit enregistrer toutes les données qu’il peut, puis abandonner. Il ne doit pas renvoyer contrôle à la fonction main, sauf si vous êtes certain que l’erreur est récupérable.  
  
 La fonction de gestionnaire de paramètre non valide doit avoir le prototype suivant :  
  
```c  
void _invalid_parameter(  
   const wchar_t * expression,  
   const wchar_t * function,   
   const wchar_t * file,   
   unsigned int line,  
   uintptr_t pReserved  
);  
```  
  
 Le `expression` argument est une représentation de chaîne étendue de l’expression d’argument qui a généré l’erreur. Le `function` argument correspond au nom de la fonction CRT qui a reçu l’argument non valide. Le `file` argument est le nom du fichier source CRT qui contient la fonction. Le `line` argument est le numéro de ligne dans le fichier. Le dernier argument est réservé. Tous les paramètres ont la valeur `NULL` sauf si une version debug de la bibliothèque CRT est utilisée.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_invalid_parameter_handler`, `_set_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C\+\+ : \< cstdlib \> ou \< stdlib.h \>|  
  
 Le `_set_invalid_parameter_handler` et `_set_thread_local_invalid_parameter_handler` les fonctions sont spécifiques de Microsoft. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Dans l’exemple suivant, un gestionnaire d’erreurs de paramètre non valide est utilisé pour imprimer la fonction qui a reçu le paramètre non valide et le fichier et ligne dans les sources de CRT. Lors de l’utilisation de la bibliothèque de débogage CRT, les erreurs de paramètre non valide également déclenchent une assertion, qui est désactivée dans cet exemple à l’aide de [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md).  
  
```c  
// crt_set_invalid_parameter_handler.c  
// compile with: /Zi /MTd  
#include <stdio.h>  
#include <stdlib.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
  
void myInvalidParameterHandler(const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter detected in function %s."  
            L" File: %s Line: %d\n", function, file, line);  
   wprintf(L"Expression: %s\n", expression);  
   abort();  
}  
  
int main( )  
{  
   char* formatString;  
  
   _invalid_parameter_handler oldHandler, newHandler;  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   // Call printf_s with invalid parameters.  
  
   formatString = NULL;  
   printf(formatString);  
}  
```  
  
```Output  
Paramètre non valide détectée dans la fonction common_vfprintf. Fichier : minkernel\crts\ucrt\src\appcrt\stdio\output.cpp ligne : Expression 32 : format ! = nullptr  
```  
  
## Voir aussi  
 [\_get\_invalid\_parameter\_handler, \_get\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)   
 [Versions à la sécurité améliorée des fonctions CRT](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)   
 [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)
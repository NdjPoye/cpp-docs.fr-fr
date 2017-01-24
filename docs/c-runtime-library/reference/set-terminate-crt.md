---
title: "set_terminate (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "set_terminate"
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
  - "set_terminate"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "gestion des exceptions, arrêt"
  - "set_terminate (fonction)"
  - "terminate (fonction)"
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# set_terminate (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installe votre propre routine d'arrêt pour être appelé par `terminate`  
  
## Syntaxe  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### Paramètres  
 `termFunction`  
 Pointeur vers une fonction de fin que vous spécifiez.  
  
## Valeur de retour  
 Retourne un pointeur vers la fonction de traduction précédente indiquée par `set_terminate` afin que la fonction précédente puisse être restaurée plus tard.  Si aucune fonction n'est définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être NULL.  
  
## Notes  
 La fonction `set_terminate` installe `termFunction` comme la fonction appelée par `terminate`.  `set_terminate` est utilisé dans la gestion des exceptions C\+\+ et peut être appelée à tout moment dans votre programme avant que l'exception ne soit levée.  Par défaut, `terminate` appelle `abort`.  Vous pouvez modifier ce comportement par défaut en écrivant votre propre fonction d'arrêt et en appelant `set_terminate` avec le nom de votre fonction comme son argument.  La routine `terminate`appelle toujours la dernière fonction donnée comme argument à `set_terminate`.  Après avoir effectué les tâches de nettoyage souhaitées, `termFunction` doit quitter le programme.  S'il ne se termine pas \(si elle revient à son appelant\), `abort` est appelé.  
  
 Dans un environnement multithread, les fonctions de traduction qui terminent sont contenues séparément pour chaque thread.  Chacun des nouveaux threads a beson d'installer sa propre fonctionde traduction qui termine.  Par conséquent, chaque thread est responsable de sa propre gestion de traduction qui termine.  
  
 Le type `terminate_function` est défini dans EH.H en tant que pointeur vers une fonction inattendue définie par l'utilisateur et qui termine, `termFunction` qui retourne `void`.  La fonction personnalisée `termFunction` peut ne prendre aucun argument et ne doit pas retourner à l'appelant.  Si il le fait, `abort` est appellé.  Une exception ne peut être relevée depuis `termFunction`.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  La fonction `set_terminate` fonctionne uniquement hors du débogueur.  
  
 Il existe un seul gestionnaire `set_terminate` pour toutes les DLL ou EXEs dynamiquement liés ; même si vous appelez `set_terminate` votre gestionnaire peut être remplacé par un autre ou que vous remplacez un set de gestionnaire par une DLL ou un fichier EXE différent.  
  
 Cette fonctionnalité n'est pas prise en charge sous **\/clr:pure**.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`set_terminate`|\<EH.H\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Voir l'example pour [terminaison](../../c-runtime-library/reference/terminate-crt.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de la gestion d'exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [inattendu](../../c-runtime-library/reference/unexpected-crt.md)
---
title: "set_unexpected (CRT) | Microsoft Docs"
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
  - "set_unexpected"
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
  - "set_unexpected"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "gestion des exceptions, arrêt"
  - "set_unexpected (fonction)"
  - "fonction inattendue"
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# set_unexpected (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installe votre propre fonction d'arrêt pour etre appelée par `unexpected`.  
  
## Syntaxe  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### Paramètres  
 `unexpFunction`  
 Pointeur vers une fonction que vous écrirez pour remplacer la fonction `unexpected`.  
  
## Valeur de retour  
 Retourne un pointeur vers la fonction précédente d'arrêt indiquée par `_set_unexpected` afin que la fonction précédente puisse être restaurée plus tard.  Si aucune fonction n'est définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être NULL.  
  
## Notes  
 La fonction `set_unexpected` installe `unexpFunction` comme la fonction appelée par `unexpected`.  `unexpected` n'est pas utilisé dans l'implémentation actuelle de gestion des exceptions C\+\+.  Le type `unexpected_function` est défini dans EH.H en tant que pointeur vers une fonction inattendu définie par l'utilisateur, `unexpFunction` qui retourne `void`.  Votre fonction personnalisée `unexpFunction` ne devrait pas retourner à l'appelant.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 Par défaut, `unexpected` appelle `terminate`.  Vous pouvez modifier ce comportement par défaut en écrivant votre propre fonction d'arrêt et en appelant `set_unexpected` avec le nom de votre fonction comme son argument.  La routine `unexpected`appelle toujours la dernière fonction donnée comme argument à `set_unexpected`.  
  
 Contrairement à la fonction personnalisée d'arrêt installée par un appel à `set_terminate`, une exception peut être levée à partir de `unexpFunction`.  
  
 Dans un environnement multithread, les fonctions inattendues sont contenues séparément pour chaque thread.  Chacun des nouveaux threads a beson d'installer sa propre fonction inattendue.  Par conséquent, chaque thread est responsable de sa propre gestion inattendue.  
  
 Dans l'implémentation Microsoft actuelle de la gestion des exceptions C\+\+, `unexpected` appelle `terminate` par défaut et n'est jamais appelé par la bibliothèque run\-time de gestion des exceptions.  Il n'existe aucun avantage particulier à appeler `unexpected` plutôt que `terminate`.  
  
 Il existe un seul gestionnaire `set_unexpected` pour toutes les DLL ou EXEs dynamiquement liés ; même si vous appelez `set_unexpected` votre gestionnaire peut être remplacé par un autre ou que vous remplacez un set de gestionnaire par une DLL ou un fichier EXE différent.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`set_unexpected`|\<EH.H\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de la gestion d'exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [inattendu](../../c-runtime-library/reference/unexpected-crt.md)
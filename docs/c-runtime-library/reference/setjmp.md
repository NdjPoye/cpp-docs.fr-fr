---
title: "setjmp | Microsoft Docs"
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
  - "setjmp"
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
  - "setjmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "programmes [C++], enregistrer des états"
  - "état actuel"
  - "setjmp (fonction)"
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enregistre l'état actuel du programme.  
  
## Syntaxe  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### Paramètres  
 `env`  
 Variable dans laquelle l'environnement est enregistré.  
  
## Valeur de retour  
 Retourne 0 après avoir enregistré l'environnement de pile.  Si `setjmp` renvoie comme résultat d'un appel de `longjmp`, il retourne l'argument `value` de `longjmp`, ou si l'argument `value` d' `longjmp` est 0, `setjmp` retourne 1.  Aucun retour d'erreur.  
  
## Notes  
 La fonction `setjmp` enregistre un environnement de pile, que vous pouvez restaurer par la suite, à l'aide de `longjmp`.  Lorsque `setjmp` et `longjmp` sont utilisés conjointement, ils fournissent un moyen d'exécuter un `goto` non local.  Ils sont généralement utilisés pour passer le contrôle d'exécution au code de gestion des erreurs ou le code récupération dans une routine appelée précédemment sans utiliser l'appel normal ou les conventions de retour.  
  
 Un appel à `setjmp` enregistre l'environnement actuel de pile dans `env`.  Un appel suivant à `longjmp` restaure l'environnement enregistré et retourne le contrôle au point juste après l'appel correspondant `setjmp`.  Toutes les variables \(à l'exception de les variables de registre\) accessibles au contrôle récepteur de routine contiennent les valeurs qu'elles avaient lorsque `longjmp` a été appelé.  
  
 Il est impossible d'utiliser `setjmp` pour aller du code natif au code managé.  
  
 **Remarque** `setjmp` et `longjmp` ne prennent pas en charge la sémantique de l'objet C\+\+.  Dans les applications C\+\+, utilisez le mécanisme de gestion des exceptions C\+\+.  
  
 Pour plus d'informations, consultez [Using setjmp and longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`setjmp`|\<setjmp.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [\_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [\_setjmp3](../../c-runtime-library/setjmp3.md)
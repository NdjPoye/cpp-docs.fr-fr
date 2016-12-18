---
title: "longjmp | Microsoft Docs"
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
  - "longjmp"
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
  - "longjmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "longjmp (fonction)"
  - "restaurer l'environnement de la pile et les paramètres régionaux d'exécution"
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# longjmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

restaure l'environnement de la pile et les paramètres régionaux d'exécution  
  
## Syntaxe  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### Paramètres  
 `env`  
 Variable dans laquelle l'environnement est enregistré.  
  
 *correspondante*  
 Valeur à retourner à l'appel de `setjmp`.  
  
## Notes  
 La fonction `longjmp` restaure les paramètres régionaux d'environnement et de pile précédemment enregistrés dans `env` par `setjmp`.  `setjmp` et `longjmp` donne un moçyen d'exécuter un `goto` non local; Ils sont généralement utilisés pour passer le contrôle d'exécution au code de gestion des erreurs ou le code récupération dans une routine appelée précédemment sans utiliser l'appel standard ou les conventions de retour.  
  
 Un appel à entraîne `setjmp` l'environnement actuel de pile à stocker dans `env`.  Un appel suivant à `longjmp` restaure l'environnement enregistré et retourne le contrôle au point juste après l'appel correspondant `setjmp`.  Résumés d'exécution que si a *la valeur* vient d'être retournée par l'appel de `setjmp`.  Les valeurs des variables \(à l'exception des variables de registre\) accessibles au contrôle récepteur de routine contiennent les valeurs qu'elles avaient lorsque `longjmp` a été appelé.  Les valeurs des variables de registre sont imprévisibles.  La valeur retournée par `setjmp` doit être différente de zéro.  Si *la valeur* est passée comme 0, la valeur 1 est remplacée dans le retour réel.  
  
 Appelez `longjmp` avant que la fonction retourne `setjmp` appelé ; sinon les résultats sont imprévisibles.  
  
 Observez les restrictions suivantes lors de l'utilisation `longjmp`:  
  
-   Ne voulez pas que les valeurs des variables de registre reste inchangé.  Les valeurs des variables de registre dans `setjmp` appelant actuel ne peuvent être restaurées les valeurs correctes lorsqu' `longjmp` exécuté.  
  
-   N'utilisez pas `longjmp` au contrôle de migration depuis une routine d'interruption\- gestion sauf si l'interruption soit provoquée par une exception à virgule flottante.  Dans ce cas, un programme peut retourner d'un gestionnaire d'interruptions via `longjmp` s'il réinitialise tout d'abord le progiciel arithmétique à virgule flottante en appelant `_fpreset`.  
  
     **Remarque** Fasse prudent lorsque vous utilisez `setjmp` et `longjmp` dans les applications C\+\+.  Comme ces fonctions ne prennent pas en charge la sémantique de l'objet C\+\+, il est plus sécurisé pour utiliser le mécanisme de gestion des exceptions C\+\+.  
  
 Pour plus d'informations, consultez [Using setjmp and longjmp](../../cpp/using-setjmp-longjmp.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`longjmp`|\<setjmp.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Consultez l'exemple de [\_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)
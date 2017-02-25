---
title: "_CrtSetAllocHook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetAllocHook"
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
  - "_CrtSetAllocHook"
  - "CrtSetAllocHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetAllocHook (fonction)"
  - "CrtSetAllocHook (fonction)"
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _CrtSetAllocHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installe une fonction d'allocation définie par le client en l'accrochant dans le processus d'allocation mémoire de débogage du runtime C \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
_CRT_ALLOC_HOOK _CrtSetAllocHook(  
   _CRT_ALLOC_HOOK allocHook   
);  
```  
  
#### Paramètres  
 `allocHook`  
 Nouvelle fonction d'allocation définie par le client pour connecter dans le processus d'allocation mémoire du débogage du runtime C.  
  
## Valeur de retour  
 Renvoie la fonction définie précédemment de raccordement d'allocation, ou `NULL` si `allocHook` est `NULL`.  
  
## Notes  
 `_CrtSetAllocHook` permet à une application de raccorder sa propre fonction d'allocation dans le processus d'allocation de mémoire de bibliothèque de débogage du runtime C.  En conséquence, chaque appel à une fonction d'allocation de débogage pour allouer, réallouer, ou supprimer un bloc de mémoire déclenche un appel à la fonction de raccordement de l'application.  `_CrtSetAllocHook` fournit une application avec une méthode simple pour vérifier comment l'application gère les situations de mémoire insuffisante, la capacité d'examiner les modèles d'allocation, et la possibilité d'enregistrer les informations d'allocations pour l'analyse ultérieure.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, Les appels de `_CrtSetAllocHook` sont supprimés pendant le prétraitement.  
  
 La fonction `_CrtSetAllocHook` installe la nouvelle fonction définie par le client d'allocation spécifiée dans `allocHook` et renvoie la fonction définie précédemment de raccordement.  L'exemple suivant montre comment une allocation définie par le client doit être prototypé:  
  
```  
int YourAllocHook( int allocType, void *userData, size_t size, int   
blockType, long requestNumber, const unsigned char *filename, int   
lineNumber);  
```  
  
 L'argument `allocType` spécifie le type d'opération d'allocation, `(_HOOK_ALLOC`, `_HOOK_REALLOC`et `_HOOK_FREE`\) qui a déclenché l'appel à la fonction de raccordement d'allocation.  Lorsque le type de déclenchement d'allocation est `_HOOK_FREE`, `userData` est un pointeur vers la section des données utilisateur du bloc de mémoire qui va être libéré.  Toutefois, lorsque le type de déclenchement d'allocation est `_HOOK_ALLOC` ou `_HOOK_REALLOC`, `userData` est `NULL` car le bloc de mémoire n'a pas encore été alloué.  
  
 `size` spécifie la taille du bloc de mémoire en octets, `blockType` indique le type du bloc de mémoire, `requestNumber` est le numéro de commande d'allocation d'objet du bloc de mémoire, et, si disponible, `filename` et `lineNumber` spécifiez le nom du fichier et le numéro de ligne source où l'opération de déclenchement d'allocation a été initialisée.  
  
 Une fois que la fonction de raccordement a terminé le traitement, elle doit retourner une valeur booléenne, qui indique au processus d'allocation principal du runtime C comment continuer.  Lorsque la fonction de raccordement souhaite que le processus d'allocation principal continue comme si la fonction de raccordement n'a jamais été appelée, la fonction de raccordement doit renvoyer `TRUE`.  Cela provoque l'opération de déclenchement d'origine d'allocation à être exécuté.  En utilisant cette implémentation, la fonction de raccordement peut rassembler et enregistrer des informations d'allocation pour l'analyse ultérieure, sans interférer avec l'opération d'allocation ou l'état actuel de la pile de débogage.  
  
 Lorsque la fonction de raccordement souhaite le processus d'allocation principal pour continuer comme si l'opération de déclenchement d'allocation a été appelée et il a échoué, la fonction de raccordement doit retourner `FALSE`.  En utilisant cette implémentation, la fonction de raccordement peut simuler une large gamme d'états de mémoire et des états du tas de débogage pour tester comment l'application gère chaque situation.  
  
 Pour désactiver la fonction de raccordement, exécutez `NULL` à `_CrtSetAllocHook`.  
  
 Pour plus d'informations sur la façon dont `_CrtSetAllocHook` peut être utilisé avec d'autres fonctions de gestion de la mémoire ou comment écrire vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
> [!NOTE]
>  `_CrtSetAllocHook` n'est pas pris en charge sous `/clr:pure`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtSetAllocHook`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Pour un exemple d'utilisation de `_CrtSetAllocHook`, consultez [crt\_dbg2](http://msdn.microsoft.com/fr-fr/21e1346a-6a17-4f57-b275-c76813089167).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtGetAllocHook](../../c-runtime-library/reference/crtgetallochook.md)
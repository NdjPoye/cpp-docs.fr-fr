---
title: "Allocation de m&#233;moire | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.memory"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "allocation de mémoire, routines"
  - "mémoire, allocation"
  - "mémoire, gérer"
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Allocation de m&#233;moire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez ces routines pour allouer, libérer et réallouer de la mémoire.  
  
### Routines d'allocation de mémoire  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|-----------------|-------------------------------|  
|[\_alloca](../c-runtime-library/reference/alloca.md), [\_malloca](../c-runtime-library/reference/malloca.md)|Allouer de la mémoire à partir de la pile|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[calloc](../c-runtime-library/reference/calloc.md)|Allouer le stockage pour le tableau, en initialisant chaque octet dans le bloc alloué à 0|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_calloc\_dbg](../c-runtime-library/reference/calloc-dbg.md)|Version de débogage de `calloc` ; disponible uniquement dans les versions de débogage des bibliothèques Runtime|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[operator delete](../c-runtime-library/operator-delete-crt.md)|Libérer le bloc alloué|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|Libérer le bloc alloué|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_expand](../c-runtime-library/reference/expand.md)|Développer ou réduire le bloc de mémoire sans le déplacer|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_expand\_dbg](../c-runtime-library/reference/expand-dbg.md)|Version de débogage de `_expand` ; disponible uniquement dans les versions de débogage des bibliothèques Runtime|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[free](../c-runtime-library/reference/free.md)|Libérer le bloc alloué|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_free\_dbg](../c-runtime-library/reference/free-dbg.md)|Version de débogage de `free` ; disponible uniquement dans les versions de débogage des bibliothèques Runtime|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_freea](../c-runtime-library/reference/freea.md)|Libérer le bloc alloué de la pile|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_get\_heap\_handle](../c-runtime-library/reference/get-heap-handle.md)|Obtenir le HANDLE Win32 du tas CRT|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_heapadd](../c-runtime-library/heapadd.md)|Ajouter de la mémoire au tas|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_heapchk](../c-runtime-library/reference/heapchk.md)|Vérifier la cohérence du tas|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_heapmin](../c-runtime-library/reference/heapmin.md)|Libérer la mémoire inutilisée dans le tas|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_heapset](../c-runtime-library/heapset.md)|Renseigner les entrées du tas libres avec la valeur spécifiée|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_heapwalk](../c-runtime-library/reference/heapwalk.md)|Retourner des informations sur chaque entrée dans le tas|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[malloc](../c-runtime-library/reference/malloc.md)|Allouer un bloc de mémoire à partir du tas|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)|Version de débogage de `malloc` ; disponible uniquement dans les versions de débogage des bibliothèques Runtime|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_msize](../c-runtime-library/reference/msize.md)|Retourner la taille du bloc alloué|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_msize\_dbg](../c-runtime-library/reference/msize-dbg.md)|Version de débogage de `_msize` ; disponible uniquement dans les versions de débogage des bibliothèques Runtime|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[new](../c-runtime-library/operator-new-crt.md)|Allouer un bloc de mémoire à partir du tas|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Allouer un bloc de mémoire à partir du tas|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_query\_new\_handler](../c-runtime-library/reference/query-new-handler.md)|Retourner l'adresse de la routine actuelle du nouveau gestionnaire telle qu'elle est définie par `_set_new_handler`|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_query\_new\_mode](../c-runtime-library/reference/query-new-mode.md)|Retourner l'entier indiquant le mode du nouveau gestionnaire défini par `_set_new_mode`  pour `malloc`|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[realloc](../c-runtime-library/reference/realloc.md)|Réallouer un bloc à une nouvelle taille|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_realloc\_dbg](../c-runtime-library/reference/realloc-dbg.md)|Version de débogage de `realloc` ; disponible uniquement dans les versions de débogage des bibliothèques Runtime|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md)|Activer le mécanisme de gestion des erreurs quand l'opérateur `new` échoue \(pour l'allocation de mémoire\) et permettre la compilation des bibliothèques de modèles standard \(STL\)|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_set\_new\_mode](../c-runtime-library/reference/set-new-mode.md)|Définir le mode du nouveau gestionnaire pour `malloc`|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
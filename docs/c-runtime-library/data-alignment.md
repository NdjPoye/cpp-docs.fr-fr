---
title: "Alignement des donn&#233;es | Microsoft Docs"
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
  - "data.alignment"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "alignement de données (C++)"
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Alignement des donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions runtime C prennent en charge l'inscription de données.  
  
### Routines d'alignement de données.  
  
|Routine|Utilisez|Équivalent de .NET Framework|  
|-------------|--------------|----------------------------------|  
|[\_aligned\_free](../c-runtime-library/reference/aligned-free.md)|Libère un bloc de mémoire qui a été allouée à [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_free\_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|Libère un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) \(débogage uniquement\).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)|Alloue la mémoire sur une limite d'alignement spécifiée.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_malloc\_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Alloue la mémoire sur une limite d'alignement spécifiée avec davantage d'espace pour un en\-tête de débogage et les mémoires tampons de remplacement \(version de débogage uniquement\).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_msize](../c-runtime-library/reference/aligned-msize.md)|Retourne la taille d'un bloc de mémoire allouée dans le segment.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_msize\_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Retourne la taille d'un bloc de mémoire alloué dans le tas \(version Debug uniquement\).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Alloue la mémoire sur une limite d'alignement spécifiée.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_malloc\_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Alloue de la mémoire sur une limite d'alignement spécifiée \(version Debug uniquement\).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_realloc\_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)\(version debug uniquement\).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) et initialise la mémoire à 0.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_recalloc\_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) et initialise la mémoire à 0 \(uniquement pour la version debug\)|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_realloc](../c-runtime-library/reference/aligned-realloc.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_realloc\_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)\(version debug uniquement\).|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) et initialise la mémoire à 0.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_recalloc\_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|Modifie la taille d'un bloc de mémoire qui a été allouée avec [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) ou [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) et initialise la mémoire à 0 \(uniquement pour la version debug\)|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
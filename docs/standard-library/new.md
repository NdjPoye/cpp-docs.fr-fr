---
title: "&lt;new&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<new>"
  - "<new>"
  - "std.<new>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nouvel en-tête"
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;new&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs types et fonctions qui contrôlent l'allocation et la libération de stockage sous contrôle du programme.  Définit également des composants pour la création de rapports sur les erreurs de gestion de stockage.  
  
## Syntaxe  
  
```  
  
#include <new>  
  
```  
  
## Notes  
 Certaines des fonctions déclarées dans cet en\-tête sont remplaçables.  L'implémentation fournit une version par défaut, dont le comportement est décrit dans ce document.  Un programme peut toutefois définir une fonction avec la même signature pour remplacer la version par défaut au moment de la liaison.  La version de remplacement doit satisfaire aux spécifications décrites dans ce document.  
  
### Objets  
  
|||  
|-|-|  
|[nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md)|Fournit un objet à utiliser comme argument pour les versions `nothrow` de **new** et **delete**.|  
  
### Typedefs  
  
|||  
|-|-|  
|[new\_handler](../Topic/new_handler.md)|Type qui pointe vers une fonction pouvant être utilisée comme nouveau gestionnaire.|  
  
### Fonctions  
  
|||  
|-|-|  
|[set\_new\_handler](../Topic/set_new_handler.md)|Installe une fonction utilisateur appelée quand new échoue dans sa tentative d'allocation de mémoire.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md)|Fonction appelée par une expression delete pour libérer le stockage pour des objets distincts.|  
|[operator delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md)|Fonction appelée par une expression delete pour libérer le stockage pour un tableau d'objets.|  
|[operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md)|Fonction appelée par une expression new pour allouer le stockage pour des objets distincts.|  
|[operator new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md)|Fonction appelée par une expression new pour allouer le stockage pour un tableau d'objets.|  
  
### Classes  
  
|||  
|-|-|  
|[bad\_alloc, classe](../standard-library/bad-alloc-class.md)|La classe décrit une exception levée pour indiquer qu'une demande d'allocation n'a pas réussi.|  
|[nothrow\_t, classe](../standard-library/nothrow-t-structure.md)|La classe est utilisée comme paramètre de fonction de l'opérateur new pour indiquer que la fonction doit retourner un pointeur null pour signaler un échec d'allocation, au lieu de lever une exception.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)
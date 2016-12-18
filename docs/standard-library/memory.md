---
title: "&lt;memory&gt; | Microsoft Docs"
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
  - "memory/std::<memory>"
  - "std.<memory>"
  - "<memory>"
  - "std::<memory>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memory (en-tête)"
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;memory&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit une classe, un opérateur et plusieurs modèles qui aident à allouer et libérer des objets.  
  
## Syntaxe  
  
```  
  
#include <memory>  
  
```  
  
## Membres  
  
### Fonctions  
  
|||  
|-|-|  
|[addressof](../Topic/addressof.md)|Obtient l'adresse exacte d'un objet.|  
|[align](../Topic/align.md)|Retourne un pointeur vers une plage d'une taille donnée, en fonction de l'alignement et de l'adresse de départ.|  
|[allocate\_shared](../Topic/allocate_shared.md)|Crée un `shared_ptr` pour les objets qui sont alloués et construits pour un type donné avec un allocateur spécifié.|  
|[checked\_uninitialized\_copy](../misc/checked-uninitialized-copy.md)|Identique à `uninitialized_copy`, mais applique l'utilisation d'un itérateur vérifié comme itérateur de sortie.|  
|[checked\_uninitialized\_fill\_n](../misc/checked-uninitialized-fill-n.md)|Identique à `uninitialized_fill_n`, mais applique l'utilisation d'un itérateur vérifié comme itérateur de sortie.|  
|[const\_pointer\_cast](../Topic/const_pointer_cast.md)|Cast de type const vers `shared_ptr`.|  
|[declare\_no\_pointers](../Topic/declare_no_pointers.md)|Informe un récupérateur de mémoire que les caractères à partir d'une adresse spécifiée et compris dans la taille de bloc indiquée ne contiennent aucun pointeur traçable.|  
|[declare\_reachable](../Topic/declare_reachable.md)|Informe une opération garbage collection que l'adresse indiquée est dédiée au stockage alloué et est accessible.|  
|[default\_delete](../Topic/default_delete.md)|Supprime les objets alloués avec `operator new`.  Fonction pouvant être utilisée avec `unique_ptr`.|  
|[dynamic\_pointer\_cast](../Topic/dynamic_pointer_cast.md)|Cast dynamique vers `shared_ptr`.|  
|[get\_deleter](../Topic/get_deleter%20Function.md)|Obtient une suppression à partir de `shared_ptr`.|  
|[get\_pointer\_safety](../Topic/get_pointer_safety.md)|Retourne le type de sécurité de pointeur supposé par tout récupérateur de mémoire.|  
|[get\_temporary\_buffer](../Topic/get_temporary_buffer.md)|Alloue un stockage temporaire pour une séquence d'éléments qui ne dépasse pas un nombre spécifié d'éléments.|  
|[make\_shared](../Topic/make_shared%20\(%3Cmemory%3E\).md)|Crée et retourne un objet `shared_ptr` qui pointe vers l'objet alloué construit de zéro ou de plusieurs arguments à l'aide de l'allocateur par défaut.|  
|[make\_unique](../Topic/make_unique.md)|Crée et retourne un objet [unique\_ptr](../standard-library/unique-ptr-class.md) qui pointe vers l'objet alloué construit de zéro ou de plusieurs arguments.|  
|[owner\_less](../Topic/owner_less.md)|Permet des comparaisons mixtes basées sur la propriété de pointeurs partagés et faibles.|  
|[pointer\_safety](../Topic/pointer_safety%20Enumeration.md)|Énumération de toutes les valeurs de retour possibles pour `get_pointer_safety`.|  
|[return\_temporary\_buffer](../Topic/return_temporary_buffer.md)|Libère la mémoire temporaire allouée à l'aide de la fonction de modèle `get_temporary_buffer`.|  
|[static\_pointer\_cast](../Topic/static_pointer_cast.md)|Cast statique vers `shared_ptr`.|  
|[échange](../Topic/swap%20\(C++%20Standard%20Library\).md)|Permutez deux objets `shared_ptr` ou `weak_ptr`.|  
|[unchecked\_uninitialized\_copy](../misc/unchecked-uninitialized-copy.md)|Identique à `uninitialized_copy`, mais permet l'utilisation d'un itérateur non vérifié comme itérateur de sortie lorsque \_SECURE\_SCL\=1 est défini.|  
|[unchecked\_uninitialized\_fill\_n](../misc/unchecked-uninitialized-fill-n.md)|Identique à `uninitialized_fill_n`, mais permet l'utilisation d'un itérateur non vérifié comme itérateur de sortie lorsque \_SECURE\_SCL\=1 est défini.|  
|[undeclare\_no\_pointers](../Topic/undeclare_no_pointers.md)|Informe un récupérateur de mémoire que les caractères dans le bloc de mémoire défini par un pointeur d'adresse de base et une taille de bloc peuvent maintenant contenir des pointeurs traçables.|  
|[undeclare\_reachable](../Topic/undeclare_reachable.md)|Informe un objet `garbage_collector` qu'un emplacement de mémoire spécifié n'est pas accessible.|  
|[uninitialized\_copy](../Topic/uninitialized_copy.md)|Copie les objets à partir d'une plage d'entrée spécifiée dans une plage de destination non initialisée.|  
|[uninitialized\_copy\_n](../Topic/uninitialized_copy_n.md)|Crée une copie d'un nombre spécifié d'éléments à partir d'un itérateur d'entrée.  Les copies sont placées dans un itérateur forward.|  
|[uninitialized\_fill](../Topic/uninitialized_fill.md)|Copie les objets d'une valeur spécifiée dans une plage de destination non initialisée.|  
|[uninitialized\_fill\_n](../Topic/uninitialized_fill_n.md)|Copie les objets d'une valeur spécifiée dans un nombre spécifié d'éléments d'une plage de destination non initialisée.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[\!\=, opérateur](../Topic/operator!=%20\(%3Cmemory%3E\).md)|Vérifie l'inégalité entre les objets allocateurs d'une classe spécifiée.|  
|[operator\=\=](../Topic/operator==%20\(%3Cmemory%3E\).md)|Vérifie l'égalité entre les objets allocateurs d'une classe spécifiée.|  
|[\>\= \(opérateur\)](../Topic/operator%3E=%20\(%3Cmemory%3E\).md)|Vérifie si un objet allocateur est supérieur ou égal à un second objet allocateur d'une classe donnée.|  
|[\< \(opérateur\)](../Topic/operator%3C%20\(%3Cmemory%3E\).md)|Vérifie si un objet est inférieur à un second objet d'une classe donnée.|  
|[\<\= \(opérateur\)](../Topic/operator%3C=%20\(%3Cmemory%3E\).md)|Vérifie si un objet est inférieur ou égal à un second objet d'une classe donnée.|  
|[\> \(opérateur\)](../Topic/operator%3E%20\(%3Cmemory%3E\).md)|Vérifie si un objet est supérieur à un second objet d'une classe donnée.|  
|[\<\<, opérateur](../Topic/operator%3C%3C%20\(%3Cmemory%3E\).md)|Outil d'insertion `shared_ptr`.|  
  
### Classes  
  
|||  
|-|-|  
|[allocator](../standard-library/allocator-class.md)|Cette classe de modèle décrit un objet qui gère l'allocation et la libération de stockage pour des tableaux d'objets de type **Type**.|  
|[allocator\_traits](../standard-library/allocator-traits-class.md)|Décrit un objet qui détermine toutes les informations qui sont requises par un conteneur activé par allocateur.|  
|[auto\_ptr](../standard-library/auto-ptr-class.md)|Cette classe de modèle décrit un objet qui stocke un pointeur dans un objet alloué du type **Type \*** qui garantit que l'objet vers lequel il pointe sera supprimé lorsque son auto\_ptr englobant sera détruit.|  
|[bad\_weak\_ptr](../standard-library/bad-weak-ptr-class.md)|Signale une exception weak\_ptr incorrecte.|  
|[enabled\_shared\_from\_this](../standard-library/enable-shared-from-this-class.md)|Aide à générer un `shared_ptr`.|  
|[pointer\_traits](../standard-library/pointer-traits-struct.md)|Fournit les informations requises par un objet de la classe de modèle `allocator_traits` pour décrire un allocateur avec le type pointeur `Ptr`.|  
|[raw\_storage\_iterator](../standard-library/raw-storage-iterator-class.md)|Classe d'adaptateur fournie pour permettre aux algorithmes de stocker leurs résultats dans la mémoire non initialisée.|  
|[shared\_ptr](../standard-library/shared-ptr-class.md)|Encapsule un pointeur intelligent contenant des références autour d'un objet alloué dynamiquement.|  
|[unique\_ptr](../standard-library/unique-ptr-class.md)|Stocke un pointeur vers un objet détenu.  Le pointeur n'est détenu par aucun autre `unique_ptr`.  L'objet `unique_ptr` est détruit lorsque le propriétaire est détruit.|  
|[weak\_ptr](../standard-library/weak-ptr-class.md)|Encapsule un pointeur faiblement lié.|  
  
### Spécialisations  
  
|||  
|-|-|  
|[allocator\<void\>](../standard-library/allocator-void-class.md)|Spécialisation de l'allocateur de classe de modèle en type void, définissant les seuls types de membres qui sont pertinents dans ce contexte spécialisé.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)
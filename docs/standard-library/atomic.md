---
title: "&lt;atomic&gt; | Microsoft Docs"
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
  - "<atomic>"
  - "atomic/std::atomic_int_least32_t"
  - "atomic/std::atomic_ullong"
  - "atomic/std::atomic_ptrdiff_t"
  - "atomic/std::atomic_char16_t"
  - "atomic/std::atomic_schar"
  - "atomic/std::atomic_ulong"
  - "atomic/std::atomic_uint_fast32_t"
  - "atomic/std::atomic_uint8_t"
  - "atomic/std::atomic_int32_t"
  - "atomic/std::atomic_uint_fast64_t"
  - "atomic/std::atomic_uint32_t"
  - "atomic/std::atomic_int16_t"
  - "atomic/std::atomic_uintmax_t"
  - "atomic/std::atomic_intmax_t"
  - "atomic/std::atomic_long"
  - "atomic/std::atomic_int"
  - "atomic/std::atomic_uint_least8_t"
  - "atomic/std::atomic_size_t"
  - "atomic/std::atomic_uint_fast16_t"
  - "atomic/std::atomic_wchar_t"
  - "atomic/std::atomic_int_fast64_t"
  - "atomic/std::atomic_uint_fast8_t"
  - "atomic/std::atomic_int_fast8_t"
  - "atomic/std::atomic_intptr_t"
  - "atomic/std::atomic_uint"
  - "atomic/std::atomic_uint16_t"
  - "atomic/std::atomic_char32_t"
  - "atomic/std::atomic_uint64_t"
  - "atomic/std::atomic_ushort"
  - "atomic/std::atomic_int_least16_t"
  - "atomic/std::atomic_char"
  - "atomic/std::atomic_uint_least32_t"
  - "atomic/std::atomic_uintptr_t"
  - "atomic/std::atomic_short"
  - "atomic/std::atomic_llong"
  - "atomic/std::atomic_uint_least16_t"
  - "atomic/std::atomic_int_fast16_t"
  - "atomic/std::atomic_int_least8_t"
  - "atomic/std::atomic_int_least64_t"
  - "atomic/std::atomic_int_fast32_t"
  - "atomic/std::atomic_uchar"
  - "atomic/std::atomic_int8_t"
  - "atomic/std::atomic_int64_t"
  - "atomic/std::atomic_uint_least64_t"
dev_langs: 
  - "C++"
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
caps.latest.revision: 22
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;atomic&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les classes et les classes de modèle à utiliser pour créer des types qui prennent en charge les opérations atomiques.  
  
## Syntaxe  
  
```cpp  
#include <atomic>  
```  
  
## Notes  
  
> [!NOTE]
>  Dans le code qui est compilé à l'aide de **\/clr** ou d'**\/clr:pure**, cet en\-tête est bloqué.  
  
 Une opération atomique deux propriétés de clé qui vous permettent de plusieurs threads d'utilisation à manipuler correctement un objet sans utiliser de verrous d'exclusion mutuelle \(mutex\).  
  
-   Étant donné qu'une opération atomique est indivisible, la seconde opération atomique sur le même objet d'un thread distinct peut obtenir l'état de l'objet uniquement avant ou après la première opération atomique.  
  
-   En fonction de son argument [memory\_order](../Topic/memory_order%20Enum.md), une opération atomique établit l'ordre des conditions requises pour la visibilité des effets d'autres opérations atomiques dans le même thread.  Par conséquent, il inhibe les optimisations du compilateur non conformes aux spécifications classantes.  
  
 Sur les plateformes, il n'est pas possible d'appliquer efficacement les opérations atomiques pour certains types sans utiliser de verrous d'`mutex`.  Un type atomique est *verrou\-disponible* si opération atomique sur cette utilisation de type n'est pas les verrous.  
  
 La classe [atomic\_flag](../standard-library/atomic-flag-structure.md) contient un type atomique minimal contenant un indicateur de `bool`.  Les opérations sont toujours verrou\- disponibles.  
  
 La classe de modèle `atomic<Ty>` enregistre un objet de type d'argument `Ty` et fournit un accès atomique à cette valeur stockée.  Vous pouvez l'instanciation en utilisant n'importe quel type qui peut être copié en utilisant [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) et être testé l'égalité à l'aide de [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md).  En particulier, vous pouvez utiliser avec les types définis par l'utilisateur qui répondent à ces critères et, dans de nombreux cas, avec les types à virgule flottante.  
  
 Le modèle a également un ensemble de spécialisations pour les types intégraux et une spécialisation partielle pour les pointeurs.  Ces spécialisations fournissent des opérations supplémentaires qui ne sont pas disponibles via le modèle primaire.  
  
## Spécialisations du pointeur  
 Les spécialisations partielles d'`atomic<Ty *>` s'appliquent à tous les types pointeurs.  Ils offrent des méthodes pour les opérations arithmétiques sur les pointeurs.  
  
## Spécialisations intégrales  
 Les spécialisations d'`atomic<integral>` s'appliquent à tous les types intégraux.  Ils offrent les opérations supplémentaires qui ne sont pas disponibles via le modèle primaire.  
  
 Chaque type d'`atomic<integral>` une macro correspondante que vous pouvez utiliser dans `if directive` pour déterminer le moment de la compilation si les événements de ce type sont verrou\- disponibles.  Si la valeur de la macro est zéro, les opérations sur le type ne sont pas verrou\- disponibles.  Si la valeur est 1, les opérations peuvent être verrou\- disponibles, ainsi qu'un contrôle d'exécution est requis.  Si la valeur est 2, les opérations sont verrou\- disponibles.  Vous pouvez utiliser la fonction `atomic_is_lock_free` pour déterminer à l'exécution si des opérations sur le type verrou\- sont disponibles.  
  
 Pour les types intégraux, un type atomique correspondant nommé qui gère un objet de ce type intégral.  Chaque type d'`atomic_integral` a le même ensemble de fonctions membres que l'instanciation de correspondance d'`atomic<Ty>` et peut être transmis aux fonctions atomiques non élément de circuit l'un des.  
  
|Type de `atomic_integral`|Type intégral|macro d'`atomic_is_lock_free`|  
|-------------------------------|-------------------|-----------------------------------|  
|`atomic_char`|`char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_schar`|`signed char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_uchar`|`unsigned char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_char16_t`|`char16_t`|`ATOMIC_CHAR16_T_LOCK_FREE`|  
|`atomic_char32_t`|`char32_t`|`ATOMIC_CHAR32_T_LOCK_FREE`|  
|`atomic_wchar_t`|`wchar_t`|`ATOMIC_WCHAR_T_LOCK_FREE`|  
|`atomic_short`|`short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_ushort`|`unsigned short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_int`|`int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_uint`|`unsigned int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_long`|`long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_ulong`|`unsigned long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_llong`|`long long`|`ATOMIC_LLONG_LOCK_FREE`|  
|`atomic_ullong`|`unsigned long long`|`ATOMIC_LLONG_LOCK_FREE`|  
  
 Les noms de typedef existent pour les spécialisations du modèle atomique pour certains types définis dans l'en\-tête \<inttypes.h.\>  
  
|Type atomique|Nom de typedef|  
|-------------------|--------------------|  
|`atomic_int8_t`|`atomic<int8_t>`|  
|`atomic_uint8_t`|`atomic<uint8_t>`|  
|`atomic_int16_t`|`atomic<int16_t>`|  
|`atomic_uint16_t`|`atomic<uint16_t>`|  
|`atomic_int32_t`|`atomic<int32_t>`|  
|`atomic_uint32_t`|`atomic<uint32_t>`|  
|`atomic_int64_t`|`atomic<int64_t>`|  
|`atomic_uint64_t`|`atomic<uint64_t>`|  
|`atomic_int_least8_t`|`atomic<int_least8_t>`|  
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|  
|`atomic_int_least16_t`|`atomic<int_least16_t>`|  
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|  
|`atomic_int_least32_t`|`atomic<int_least32_t>`|  
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|  
|`atomic_int_least64_t`|`atomic<int_least64_t>`|  
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|  
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|  
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|  
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|  
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|  
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|  
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|  
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|  
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|  
|`atomic_intptr_t`|`atomic<intptr_t>`|  
|`atomic_uintptr_t`|`atomic<uintptr_t>`|  
|`atomic_size_t`|`atomic<size_t>`|  
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|  
|`atomic_intmax_t`|`atomic<intmax_t>`|  
|`atomic_uintmax_t`|`atomic<uintmax_t>`|  
  
## Structures  
  
|Nom|Description|  
|---------|-----------------|  
|[atomic, structure](../standard-library/atomic-structure.md)|Décrit un objet qui effectue les opérations atomiques sur une valeur stockée.|  
|[atomic\_flag, structure](../standard-library/atomic-flag-structure.md)|Décrit un objet qui définit et désactive atomiquement un indicateur `bool`.|  
  
## Enums  
  
|Nom|Description|  
|---------|-----------------|  
|[memory\_order, énum](../Topic/memory_order%20Enum.md)|Fournit des noms symboliques pour les opérations de synchronisation sur les emplacements de mémoire.  Ces opérations affectent la façon dont les assignations dans un thread sont visibles dans un autre.|  
  
## Fonctions  
 Dans la liste suivante, les fonctions qui ne se terminent pas dans `_explicit` ont la sémantique d'`_explicit`correspondant, sauf qu'elles ont les arguments implicites d'[memory\_order](../Topic/memory_order%20Enum.md) d'`memory_order_seq_cst`.  
  
|Nom|Description|  
|---------|-----------------|  
|[atomic\_compare\_exchange\_strong, fonction](../Topic/atomic_compare_exchange_strong%20Function.md)|Effectue une *opération atomique de comparaison et d'échange*.|  
|[atomic\_compare\_exchange\_strong\_explicit, fonction](../Topic/atomic_compare_exchange_strong_explicit%20Function.md)|Effectue une *opération atomique de comparaison et d'échange*.|  
|[atomic\_compare\_exchange\_weak, fonction](../Topic/atomic_compare_exchange_weak%20Function.md)|Effectue une opération *atomique faible de comparaison et d'échange* .|  
|[atomic\_compare\_exchange\_weak\_explicit, fonction](../Topic/atomic_compare_exchange_weak_explicit%20Function.md)|Effectue une opération *atomique faible de comparaison et d'échange* .|  
|[atomic\_exchange, fonction](../Topic/atomic_exchange%20Function.md)|Remplace la valeur stockée.|  
|[atomic\_exchange\_explicit, fonction](../Topic/atomic_exchange_explicit%20Function.md)|Remplace la valeur stockée.|  
|[atomic\_fetch\_add, fonction](../Topic/atomic_fetch_add%20Function.md)|Ajoute une valeur spécifiée en une valeur stockée existante.|  
|[atomic\_fetch\_add\_explicit, fonction](../Topic/atomic_fetch_add_explicit%20Function.md)|Ajoute une valeur spécifiée en une valeur stockée existante.|  
|[atomic\_fetch\_and, fonction](../Topic/atomic_fetch_and%20Function.md)|Effectue `and` au niveau de le bit sur une valeur spécifiée et une valeur stockée existante.|  
|[atomic\_fetch\_and\_explicit, fonction](../Topic/atomic_fetch_and_explicit%20Function.md)|Effectue `and` au niveau de le bit sur une valeur spécifiée et une valeur stockée existante.|  
|[atomic\_fetch\_or, fonction](../Topic/atomic_fetch_or%20Function.md)|Effectue `or` au niveau de le bit sur une valeur spécifiée et une valeur stockée existante.|  
|[atomic\_fetch\_or\_explicit, fonction](../Topic/atomic_fetch_or_explicit%20Function.md)|Effectue `or` au niveau de le bit sur une valeur spécifiée et une valeur stockée existante.|  
|[atomic\_fetch\_sub, fonction](../Topic/atomic_fetch_sub%20Function.md)|Soustrait la valeur spécifiée d'une valeur stockée existante.|  
|[atomic\_fetch\_sub\_explicit, fonction](../Topic/atomic_fetch_sub_explicit%20Function.md)|Soustrait la valeur spécifiée d'une valeur stockée existante.|  
|[atomic\_fetch\_xor, fonction](../Topic/atomic_fetch_xor%20Function.md)|Effectue `exclusive or` au niveau de le bit sur une valeur spécifiée et une valeur stockée existante.|  
|[atomic\_fetch\_xor\_explicit, fonction](../Topic/atomic_fetch_xor_explicit%20Function.md)|Effectue `exclusive or` au niveau de le bit sur une valeur spécifiée et une valeur stockée existante.|  
|[atomic\_flag\_clear, fonction](../Topic/atomic_flag_clear%20Function.md)|Définit l'indicateur dans un objet d'`atomic_flag` à `false`.|  
|[atomic\_flag\_clear\_explicit, fonction](../Topic/atomic_flag_clear_explicit%20Function.md)|Définit l'indicateur dans un objet d'`atomic_flag` à `false`.|  
|[atomic\_flag::test\_and\_set, fonction](../Topic/atomic_flag_test_and_set%20Function.md)|Définit l'indicateur dans un objet d'`atomic_flag` à `true`.|  
|[atomic\_flag\_test\_and\_set\_explicit, fonction](../Topic/atomic_flag_test_and_set_explicit%20Function.md)|Définit l'indicateur dans un objet d'`atomic_flag` à `true`.|  
|[atomic\_init, fonction](../Topic/atomic_init%20Function.md)|Définit la valeur stockée dans un objet d'`atomic`.|  
|[Fonction atomic\_is\_lock\_free](../Topic/atomic_is_lock_free%20Function.md)|Spécifie si les opérations atomiques sur un objet spécifié sont verrou\- disponibles.|  
|[atomic\_load, fonction](../Topic/atomic_load%20Function.md)|Récupère une valeur atomique.|  
|[atomic\_load\_explicit, fonction](../Topic/atomic_load_explicit%20Function.md)|Récupère une valeur atomique.|  
|[atomic\_signal\_fence, fonction](../Topic/atomic_signal_fence%20Function.md)|Agit comme une *frontière de sécurité* qui génère la mémoire organisation des conditions requises entre les frontières de sécurité dans un thread appelant qui a des gestionnaires de signal exécutés dans le même thread.|  
|[atomic\_store, fonction](../Topic/atomic_store%20Function.md)|Stocke une valeur atomique.|  
|[atomic\_store\_explicit, fonction](../Topic/atomic_store_explicit%20Function.md)|Stocke une valeur atomique.|  
|[atomic\_thread\_fence, fonction](../Topic/atomic_thread_fence%20Function.md)|Agit comme une *frontière de sécurité* qui génère la mémoire organisation des exigences en ce qui concerne les autres frontières de sécurité.|  
|[kill\_dependency, fonction](../Topic/kill_dependency%20Function.md)|Arrête une chaîne possible de dépendance.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)
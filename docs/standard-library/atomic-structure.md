---
title: "atomic, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "atomic/std::atomic"
dev_langs: 
  - "C++"
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# atomic, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui effectue des opérations atomiques sur une valeur stockée de type `Ty`.  
  
## Syntaxe  
  
```  
template <class Ty>  
struct atomic;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[atomic::atomic, constructeur](../Topic/atomic::atomic%20Constructor.md)|Construit un objet atomique.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[atomic::operator Ty, opérateur](../Topic/atomic::operator%20Ty%20Operator.md)|Lit et retourne la valeur stockée. \([atomic::load, méthode](../Topic/atomic::load%20Method.md)\)|  
|[atomic::operator\=, opérateur](../Topic/atomic::operator=%20Operator.md)|Utilise une valeur spécifiée pour remplacer la valeur stockée. \([atomic::store, méthode](../Topic/atomic::store%20Method.md)\)|  
|||  
|[atomic::operator\+\+, opérateur](../Topic/atomic::operator++%20Operator.md)|Incrémente la valeur stockée.  Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator\+\=, opérateur](../Topic/atomic::operator+=%20Operator.md)|Ajoute une valeur spécifiée à la durée stockée.  Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator\-\-, opérateur](../Topic/atomic::operator--%20Operator.md)|Décrémente la valeur stockée.  Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator\-\=, opérateur](../Topic/atomic::operator-=%20Operator.md)|Soustrait une valeur spécifiée de la valeur stockée.  Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator&\=, opérateur](../Topic/atomic::operator&=%20Operator.md)|Effectue une opération de bits `and` sur une valeur spécifiée et la valeur stockée.  Utilisé uniquement par les spécialisations intégrales.|  
|[atomic::operator&#124;\=, opérateur](../Topic/atomic::operator%7C=%20Operator.md)|Effectue une opération de bits `or` sur une valeur spécifiée et la valeur stockée.  Utilisé uniquement par les spécialisations intégrales.|  
|[atomic::operator^\=, opérateur](../Topic/atomic::operator%5E=%20Operator.md)|Effectue une opération de bits `exclusive or` sur une valeur spécifiée et la valeur stockée.  Utilisé uniquement par les spécialisations intégrales.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[atomic::compare\_exchange\_strong, méthode](../Topic/atomic::compare_exchange_strong%20Method.md)|Effectue une opération de `atomic_compare_and_exchange` sur  `this` et retourne le résultat.|  
|[atomic::compare\_exchange\_weak, méthode](../Topic/atomic::compare_exchange_weak%20Method.md)|Effectue une opération de `weak_atomic_compare_and_exchange` sur  `this` et retourne le résultat.|  
|[atomic::fetch\_add, méthode](../Topic/atomic::fetch_add%20Method.md)|Ajoute une valeur spécifiée à la durée stockée.|  
|[atomic::fetch\_and, méthode](../Topic/atomic::fetch_and%20Method.md)|Effectue une opération de bits `and` sur une valeur spécifiée et la valeur stockée.|  
|[atomic\_fetch\_or, méthode](../Topic/atomic::fetch_or%20Method.md)|Effectue une opération de bits `or` sur une valeur spécifiée et la valeur stockée.|  
|[atomic\_fetch\_sub, méthode](../Topic/atomic::fetch_sub%20Method.md)|Soustrait une valeur spécifiée de la valeur stockée.|  
|[atomic::fetch\_xor, méthode](../Topic/atomic::fetch_xor%20Method.md)|Effectue une opération de bits `exclusive or` sur une valeur spécifiée et la valeur stockée.|  
|[atomic::is\_lock\_free, méthode](../Topic/atomic::is_lock_free%20Method.md)|Spécifie si les opérations atomiques sur `this` sont *sans verrouillage*.  Un type atomique est *sans verrouillage* si aucune opération atomique sur ce types n'utilise de verrou.|  
|[atomic::load, méthode](../Topic/atomic::load%20Method.md)|Lit et retourne la valeur stockée.|  
|[atomic::store, méthode](../Topic/atomic::store%20Method.md)|Utilise une valeur spécifiée pour remplacer la valeur stockée.|  
  
## Notes  
 Le type `Ty` doit être *simplement copyable*.  Autrement dit, l'utilisation de [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) pour copier ses octets doit créer un objet `Ty` valide qui compare une valeur égale à l'objet d'origine.  Les fonctions membres `compare_exchange_weak` et `compare_exchange_strong` utilisent des [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) pour déterminer si deux valeurs de `Ty` sont identiques.  Ces fonctions n'utiliseront pas `Ty`\- `operator==`défini.  Les fonctions membres de `atomic` utilisent `memcpy` pour copier des valeurs de type `Ty`.  
  
 Une spécialisation partielle, `atomic<Ty *>`, existe pour tous les types de pointeur.  La spécialisation permet l'ajout d'un décalage à la valeur de pointeur managée ou la soustraction d'un décalage à celle\-ci.  Les opérations arithmétiques prennent un argument de type `ptrdiff_t` et ajustent cet argument à celle d'un `Ty` pour être compatibles avec l'arithmétique d'adresse ordinaire.  
  
 Une spécialisation existe pour chaque type intégral sauf `bool`.  Chaque spécialisation fournit un ensemble de méthodes pour les opérations arithmétiques et logiques atomiques.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 Les spécialisations intégrales sont dérivées des types`integral` d'`atomic_` correspondants.  Par exemple, `atomic<unsigned int>` dérive de `atomic_uint`.  
  
## Configuration requise  
 **En\-tête :** atomique  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<atomic\>](../standard-library/atomic.md)   
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)
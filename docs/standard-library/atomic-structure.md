---
title: atomic, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic/std::atomic
dev_langs: C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5525953e5f4ba68fdf1b84b02046d9ab4679abe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="atomic-structure"></a>atomic, structure
Décrit un objet qui effectue des opérations atomiques sur une valeur stockée de type `Ty`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
struct atomic;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[atomic](http://msdn.microsoft.com/Library/a538c43f-4d48-4308-ae1b-bab1839bccb8)|Construit un objet atomique.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[atomic::operator Ty, opérateur](http://msdn.microsoft.com/Library/a366c700-c7a0-4bcb-8eb4-4b57dfaea065)|Lit et retourne la valeur stockée. ([atomic::load](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1))|  
|[atomic::operator=, opérateur](http://msdn.microsoft.com/Library/fe161d57-47ae-4bad-92bf-ce32ac8d5953)|Utilise une valeur spécifiée pour remplacer la valeur stockée. ([atomic::store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b))|  
|[atomic::operator++, opérateur](http://msdn.microsoft.com/Library/492959e9-1ea8-4e02-a031-82b1b92e91a0)|Incrémente la valeur stockée. Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator+=, opérateur](http://msdn.microsoft.com/Library/9ec97aa2-c9d7-436b-943d-2989eb2617dd)|Ajoute une valeur spécifiée à la valeur stockée. Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator--, opérateur](http://msdn.microsoft.com/Library/ad7c1ea7-1f6d-4a54-bf26-07630f749864)|Décrémente la valeur stockée. Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator-=, opérateur](http://msdn.microsoft.com/Library/902d0d9f-88fd-4500-aa2d-1e50f443e77c)|Soustrait une valeur spécifiée de la valeur stockée. Utilisé uniquement par les spécialisations intégrales et de pointeur.|  
|[atomic::operator&=, opérateur](http://msdn.microsoft.com/Library/90e730ac-12e1-4abb-98f5-4eadd6861a89)|Effectue une opération `and` au niveau du bit sur une valeur spécifiée et la valeur stockée. Utilisé uniquement par les spécialisations intégrales.|  
|[atomic::operator&#124;=, opérateur](http://msdn.microsoft.com/Library/f105eacc-31a6-4906-abba-f1cf013599b2)|Effectue une opération `or` au niveau du bit sur une valeur spécifiée et la valeur stockée. Utilisé uniquement par les spécialisations intégrales.|  
|[atomic::operator^=, opérateur](http://msdn.microsoft.com/Library/f2a4da9d-67e8-4249-9161-9998e72a33c2)|Effectue une opération `exclusive or` au niveau du bit sur une valeur spécifiée et la valeur stockée. Utilisé uniquement par les spécialisations intégrales.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[compare_exchange_strong](http://msdn.microsoft.com/Library/47bbf894-b28c-4ece-959e-67b3863cf4ed)|Effectue une opération `atomic_compare_and_exchange` sur `this` et retourne le résultat.|  
|[compare_exchange_weak](http://msdn.microsoft.com/Library/e15e421a-f7a3-4272-993a-f487d2242e4f)|Effectue une opération `weak_atomic_compare_and_exchange` sur `this` et retourne le résultat.|  
|[fetch_add](http://msdn.microsoft.com/Library/c68b91f2-6e8a-4ffa-8991-6bb6d466e1f3)|Ajoute une valeur spécifiée à la valeur stockée.|  
|[fetch_and](http://msdn.microsoft.com/Library/a9c83001-b72c-4085-9640-f63f866714b9)|Effectue une opération `and` au niveau du bit sur une valeur spécifiée et la valeur stockée.|  
|[fetch_or](http://msdn.microsoft.com/Library/4c532f7f-80c5-432a-b34b-48feacab8dca)|Effectue une opération `or` au niveau du bit sur une valeur spécifiée et la valeur stockée.|  
|[fetch_sub](http://msdn.microsoft.com/Library/8cc80d4b-0942-45a3-9db8-bbf339a903e4)|Soustrait une valeur spécifiée de la valeur stockée.|  
|[fetch_xor](http://msdn.microsoft.com/Library/92bbaff8-ee29-4a1e-aee4-d9d405285bfe)|Effectue une opération `exclusive or` au niveau du bit sur une valeur spécifiée et la valeur stockée.|  
|[is_lock_free](http://msdn.microsoft.com/Library/b99d5130-cdda-40a2-b14c-152b13a8ba45)|Spécifie si les opérations atomiques sur `this` sont *sans verrou*. Un type atomique est *sans verrou* si aucune opération atomique sur ce type utilise un verrou.|  
|[charge](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1)|Lit et retourne la valeur stockée.|  
|[store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b)|Utilise une valeur spécifiée pour remplacer la valeur stockée.|  
  
## <a name="remarks"></a>Notes  
 Le type `Ty` doit être *copiable de manière triviale*. Autrement dit, l’utilisation de [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) pour copier ses octets doit produire un objet `Ty` valide dont la valeur est égale à celle de l’objet d’origine. Les fonctions membres `compare_exchange_weak` et `compare_exchange_strong` utilisent [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) pour déterminer si deux valeurs `Ty` sont égales. Ces fonctions n’utilisent pas d’opérateur `operator==` défini sur `Ty`. Les fonctions membres de `atomic` utilisent `memcpy` pour copier les valeurs de type `Ty`.  
  
 Une spécialisation partielle, `atomic<Ty *>`, existe pour tous les types de pointeur. La spécialisation permet d’ajouter un décalage à la valeur de pointeur gérée ou de lui soustraire un décalage. Les opérations arithmétiques prennent un argument de type `ptrdiff_t` et ajustent cet argument en fonction de la taille de `Ty` pour être cohérent avec l’arithmétique d’adresse ordinaire.  
  
 Une spécialisation existe pour chaque type intégral sauf `bool`. Chaque spécialisation fournit un ensemble complet de méthodes pour les opérations atomiques arithmétiques et logiques.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 Les spécialisations intégrales sont dérivées des types `atomic_integral` correspondants. Par exemple, `atomic<unsigned int>` est dérivé de `atomic_uint`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<atomique >  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<atomic>](../standard-library/atomic.md)   
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)




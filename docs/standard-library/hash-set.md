---
title: '&lt;hash_set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_set>
- std.<hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: cd8ab51b229f1c62cd6f3dd1862920d683834975
ms.lasthandoff: 02/24/2017

---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;
> [!NOTE]
>  Cet en-tête est obsolète. L’alternative est [<unordered_set>](../standard-library/unordered-set.md).  
  
 Définit les classes de modèle de conteneur hash_set et hash_multiset et leurs modèles de prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <hash_set>  
  
```  
  
## <a name="remarks"></a>Notes  
  
### <a name="operators"></a>Opérateurs  
  
|Version de hash_set|Version de hash_multiset|Description|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_set)](../standard-library/hash-set-operators.md#operator_neq)|[operator!= (hash_multiset)](../standard-library/hash-set-operators.md#operator_neq__hash_multiset_)|Teste si l’objet hash_set ou hash_multiset situé à gauche de l’opérateur n’est pas égal à l’objet hash_set ou hash_multiset situé à droite.|  
|[operator== (hash_set)](http://msdn.microsoft.com/en-us/791b95bd-f917-4716-aea6-add50badbfac)|[operator== (hash_multiset)](http://msdn.microsoft.com/en-us/cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|Teste si l’objet hash_set ou hash_multiset situé à gauche de l’opérateur est égal à l’objet hash_set ou hash_multiset situé à droite.|  
  
### <a name="specialized-template-functions"></a>Fonctions avec modèle spécialisé  
  
|Version de hash_set|Version de hash_multiset|Description|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap__hash_multiset_)|Échange les éléments de deux objets hash_set ou hash_multiset.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[hash_compare, classe](../standard-library/hash-compare-class.md)|Décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash_map, hash_multimap, hash_set ou hash_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu’ils contiennent.|  
|[hash_set, classe](../standard-library/hash-set-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés.|  
|[hash_multiset, classe](../standard-library/hash-multiset-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)





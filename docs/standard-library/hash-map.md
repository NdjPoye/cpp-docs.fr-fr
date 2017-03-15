---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<hash_map>
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 3f9a4705d946831ddee15116676fde9e433288f7
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  Cet en-tête est obsolète. L’alternative est [<unordered_map>](../standard-library/unordered-map.md).  
  
 Définit les classes de modèle de conteneur hash_map et hash_multimap et leurs modèles de prise en charge.  
  
 Dans Visual C++ .NET 2003, les membres des fichiers d’en-tête <hash_map> et <hash_set> ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d’informations, consultez [The stdext Namespace (L’espace de noms stdext)](../standard-library/stdext-namespace.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>Opérateurs  
  
|Version de hash_map|Version de hash_multimap|Description|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](../standard-library/hash-map-operators.md#operator_neq__hash_map_)|[operator!= (hash_multimap)](../standard-library/hash-map-operators.md#operator_neq)|Teste si l’objet hash_map ou hash_multimap situé à gauche de l’opérateur n’est pas égal à l’objet hash_map ou hash_multimap situé à droite.|  
|[operator== (hash_map)](http://msdn.microsoft.com/en-us/f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[operator== (hash_multimap)](http://msdn.microsoft.com/en-us/3fa378b1-0250-4e3f-a130-dc14103fc5e9)|Teste si l’objet hash_map ou hash_multimap situé à gauche de l’opérateur est égal à l’objet hash_map ou hash_multimap situé à droite.|  
  
### <a name="specialized-template-functions"></a>Fonctions avec modèle spécialisé  
  
|Version de hash_map|Version de hash_multimap|Description|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](../standard-library/hash-map-class.md#hash_map__swap)|[swap (hash_multimap)](../standard-library/hash-multimap-class.md#hash_multimap__swap)|Échange les éléments de deux objets hash_maps ou hash_multimaps.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[hash_compare, classe](../standard-library/hash-compare-class.md)|Décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash_map, hash_multimap, hash_set ou hash_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu’ils contiennent.|  
|[value_compare, classe](../standard-library/value-compare-class.md)|Fournit un objet de fonction qui peut comparer les éléments d’un hash_map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans le hash_map.|  
|[hash_map, classe](../standard-library/hash-map-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur est unique et une valeur de données associée.|  
|[hash_multimap, classe](../standard-library/hash-multimap-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur ne doit pas nécessairement être unique et une valeur de données associée.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<hash_map>  
  
 **Espace de noms :** stdext  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)





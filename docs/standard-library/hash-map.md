---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 09/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs: C++
helpviewer_keywords: hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a996142e128f4113fb9d1057cd061155dae251f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  Cet en-tête est obsolète. L’alternative est [ \<unordered_map >](unordered-map.md).  
  
 Définit les classes de modèle de conteneur hash_map et hash_multimap et leurs modèles de prise en charge.  
 
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>Opérateurs  
  
|Version de hash_map|Version de hash_multimap|Description|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Teste si l’objet hash_map ou hash_multimap situé à gauche de l’opérateur n’est pas égal à l’objet hash_map ou hash_multimap situé à droite.|  
|[operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[opérateur == (hash_multimap)] ((hachage-map-operators.md #op_eq_eq_mm)|Teste si l’objet hash_map ou hash_multimap situé à gauche de l’opérateur est égal à l’objet hash_map ou hash_multimap situé à droite.|  
  
### <a name="specialized-template-functions"></a>Fonctions avec modèle spécialisé  
  
|Version de hash_map|Version de hash_multimap|Description|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Échange les éléments de deux objets hash_maps ou hash_multimaps.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[hash_compare, classe](hash-compare-class.md)|Décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash_map, hash_multimap, hash_set ou hash_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu’ils contiennent.|  
|[value_compare, classe](value-compare-class.md)|Fournit un objet de fonction qui peut comparer les éléments d’un hash_map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans le hash_map.|  
|[hash_map, classe](hash-map-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur est unique et une valeur de données associée.|  
|[hash_multimap, classe](hash-multimap-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur ne doit pas nécessairement être unique et une valeur de données associée.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<hash_map>  
  
 **Espace de noms :** stdext  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](cpp-standard-library-reference.md)




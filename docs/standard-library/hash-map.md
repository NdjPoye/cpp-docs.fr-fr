---
title: "&lt;hash_map&gt; | Microsoft Docs"
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
  - "std.<hash_map>"
  - "<hash_map>"
  - "std::<hash_map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map (en-tête)"
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;hash_map&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cet en\-tête est obsolète. L’alternative est [\<unordered\_map\>](../standard-library/unordered-map.md).  
  
 Définit les classes de modèle de conteneur hash\_map et hash\_multimap et leurs modèles de prise en charge.  
  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d’en\-tête [\<hash\_map\>](#vclrfhash_map_header_file) et [\<hash\_set\>](../standard-library/hash-set.md) ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d'informations, voir [Espace de noms stdext](../standard-library/stdext-namespace.md).  
  
## Syntaxe  
  
```  
  
#include <hash_map>  
  
```  
  
### Opérateurs  
  
|Version de hash\_map|Version de hash\_multimap|Description|  
|--------------------------|-------------------------------|-----------------|  
|[operator\!\= \(hash\_map\)](../Topic/operator!=%20\(hash_map\).md)|[operator\!\= \(hash\_multimap\)](../Topic/operator!=%20\(hash_multimap\).md)|Teste si l’objet hash\_map ou hash\_multimap situé à gauche de l’opérateur n’est pas égal à l’objet hash\_map ou hash\_multimap situé à droite.|  
|[operator\=\= \(hash\_map\)](http://msdn.microsoft.com/fr-fr/f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[operator\=\= \(hash\_multimap\)](http://msdn.microsoft.com/fr-fr/3fa378b1-0250-4e3f-a130-dc14103fc5e9)|Teste si l’objet hash\_map ou hash\_multimap situé à gauche de l’opérateur est égal à l’objet hash\_map ou hash\_multimap situé à droite.|  
  
### Fonctions avec modèle spécialisé  
  
|Version de hash\_map|Version de hash\_multimap|Description|  
|--------------------------|-------------------------------|-----------------|  
|[swap \(hash\_map\)](../Topic/hash_map::swap.md)|[swap \(hash\_multimap\)](../Topic/hash_multimap::swap.md)|Échange les éléments de deux objets hash\_maps ou hash\_multimaps.|  
  
### Classes  
  
|||  
|-|-|  
|[hash\_compare, classe](../standard-library/hash-compare-class.md)|Décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash\_map, hash\_multimap, hash\_set ou hash\_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu’ils contiennent.|  
|[value\_compare, classe](../standard-library/value-compare-class.md)|Fournit un objet de fonction qui peut comparer les éléments d’un hash\_map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans le hash\_map.|  
|[hash\_map, classe](../standard-library/hash-map-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur est unique et une valeur de données associée.|  
|[hash\_multimap, classe](../standard-library/hash-multimap-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle chaque élément est une paire qui a une clé de tri dont la valeur ne doit pas nécessairement être unique et une valeur de données associée.|  
  
## Configuration requise  
 **En\-tête :** \<hash\_map\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)
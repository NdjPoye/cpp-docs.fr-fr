---
title: "&lt;hash_set&gt; | Microsoft Docs"
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
  - "<hash_set>"
  - "std.<hash_set>"
  - "std::<hash_set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set (en-tête)"
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;hash_set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cet en\-tête est obsolète. L’alternative est [\<unordered\_set\>](../standard-library/unordered-set.md).  
  
 Définit les classes de modèle de conteneur hash\_set et hash\_multiset et leurs modèles de prise en charge.  
  
## Syntaxe  
  
```  
  
#include <hash_set>  
  
```  
  
## Notes  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d'en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et [\<hash\_set\>](#vclrfhash_set_header_file) ne sont plus dans l'espace de noms std. Ils ont été transférés dans l'espace de noms stdext. Pour plus d'informations, consultez [The stdext Namespace](../standard-library/stdext-namespace.md).  
  
### Opérateurs  
  
|Version de hash\_set|Version de hash\_multiset|Description|  
|--------------------------|-------------------------------|-----------------|  
|[operator\!\= \(hash\_set\)](../Topic/operator!=%20\(hash_set\).md)|[operator\!\= \(hash\_multiset\)](../Topic/operator!=%20\(hash_multiset\).md)|Teste si l’objet hash\_set ou hash\_multiset situé à gauche de l’opérateur n’est pas égal à l’objet hash\_set ou hash\_multiset situé à droite.|  
|[operator\=\= \(hash\_set\)](http://msdn.microsoft.com/fr-fr/791b95bd-f917-4716-aea6-add50badbfac)|[operator\=\= \(hash\_multiset\)](http://msdn.microsoft.com/fr-fr/cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|Teste si l’objet hash\_set ou hash\_multiset situé à gauche de l’opérateur est égal à l’objet hash\_set ou hash\_multiset situé à droite.|  
  
### Fonctions avec modèle spécialisé  
  
|Version de hash\_set|Version de hash\_multiset|Description|  
|--------------------------|-------------------------------|-----------------|  
|[swap \(hash\_set\)](../Topic/swap%20\(hash_set\).md)|[swap \(hash\_multiset\)](../Topic/swap%20\(hash_multiset\).md)|Échange les éléments de deux objets hash\_set ou hash\_multiset.|  
  
### Classes  
  
|||  
|-|-|  
|[hash\_compare, classe](../standard-library/hash-compare-class.md)|Décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash\_map, hash\_multimap, hash\_set ou hash\_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu’ils contiennent.|  
|[hash\_set, classe](../standard-library/hash-set-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés.|  
|[hash\_multiset, classe](../standard-library/hash-multiset-class.md)|Sert au stockage et à la récupération rapide des données d’une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)
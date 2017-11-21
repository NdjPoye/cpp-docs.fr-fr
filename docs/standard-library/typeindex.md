---
title: '&lt;typeindex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <typeindex>
dev_langs: C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9103141b1e1d7ed01dbb1b4a746f0beaf535efbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;
Incluez l’en-tête standard \<typeindex> pour définir une classe et une fonction qui prennent en charge l’indexation des objets de la classe [type_info](../cpp/type-info-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
#include <typeindex>  
```  
  
## <a name="remarks"></a>Notes  
 La [structure hash](../standard-library/hash-structure.md) définit une `hash function` appropriée pour mapper des valeurs de type [type_index](../standard-library/type-index-class.md) à une distribution de valeurs d’index.  
  
 La classe `type_index` encapsule un pointeur vers un objet `type_info` pour faciliter l’indexation.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




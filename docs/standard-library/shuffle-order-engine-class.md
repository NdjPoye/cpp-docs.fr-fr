---
title: shuffle_order_engine, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
dev_langs: C++
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43de5df2afa0aca7e1634eac0338ae1b49ea9372
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine, classe
Génère une séquence aléatoire en réordonnançant les valeurs retournées à partir de son moteur de base.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Engine, size_t K>  
class shuffle_order_engine;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Engine`  
 Type de moteur de base.  
  
 `K`  
 **Taille de table**. Nombre d'éléments dans la mémoire tampon (table). **Condition préalable** : `0 < K`  
  
## <a name="members"></a>Membres  
  
||||  
|-|-|-|  
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|  
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle décrit un *adaptateur de moteur* qui produit des valeurs en réordonnançant les valeurs retournées par son moteur de base. Chaque constructeur remplit la table interne avec `K` valeurs retournées par le moteur de base et un élément aléatoire est sélectionné à partir de la table quand une valeur est demandée.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<random>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<random>](../standard-library/random.md)


---
title: independent_bits_engine, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: random/std::independent_bits_engine
dev_langs: C++
helpviewer_keywords: independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ec9a4b9beac581df0060f239916c06b8b6191de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="independentbitsengine-class"></a>independent_bits_engine, classe
Génère une séquence aléatoire de nombres avec un nombre spécifié de bits en recompressant les bits des valeurs retournées par son moteur de base.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Engine, size_t W, class UIntType>  
class independent_bits_engine;  
```  
  
### <a name="parameters"></a>Paramètres  
 `Engine`  
 Type de moteur de base.  
  
 `W`  
 **Taille de mot**. Taille, en bits, de chaque nombre généré. **Condition préalable** : `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 Type des résultats entiers non signés. Pour plus d’informations sur les types possibles, consultez [\<random>](../standard-library/random.md).  
  
## <a name="members"></a>Membres  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle décrit un *adaptateur de moteur* qui produit des valeurs en recompressant les bits à partir des valeurs retournées par son moteur de base, ce qui produit des valeurs de `W` bits.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<random>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<random>](../standard-library/random.md)


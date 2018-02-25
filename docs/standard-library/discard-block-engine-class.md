---
title: "discard_block_engine, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89cfd599f1f51c70f2e4ac108b32ccbe8bc6ae68
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="discardblockengine-class"></a>discard_block_engine, classe
Génère une séquence aléatoire en ignorant les valeurs retournées par son moteur de base.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Engine, size_t P, size_t R>  
class discard_block_engine;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Engine`  
 Type de moteur de base.  
  
 `P`  
 **Taille de bloc**. Nombre de valeurs dans chaque bloc.  
  
 `R`  
 **Bloc utilisé**. Nombre de valeurs dans chaque bloc qui sont utilisées. Les autres sont ignorées ( `P` - `R`). **Condition préalable** : `0 < R ≤ P`  
  
## <a name="members"></a>Membres  
  
||||  
|-|-|-|  
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|  
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle décrit un adaptateur de moteur qui produit des valeurs en écartant certaines des valeurs retournées par son moteur de base.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<random>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<random>](../standard-library/random.md)


---
title: "discard_block_engine, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: random/std::discard_block_engine
dev_langs: C++
helpviewer_keywords: discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ca21ef820c4dfe713a5a9b0c969ac0b14e3efe01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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


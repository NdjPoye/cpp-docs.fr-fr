---
title: treat_as_floating_point, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: chrono/std::chrono::treat_as_floating_point
dev_langs: C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8bfdda5bab6db19a1cf6d123f141f87249b62478
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point, structure
Spécifie si `Rep` peut être traité comme un type à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## <a name="remarks"></a>Notes  
 `Rep` peut être traité comme un type à virgule flottante uniquement lorsque la spécialisation `treat_as_floating_point<Rep>` est dérivée de [true_type](../standard-library/type-traits-typedefs.md#true_type). La classe de modèle peut être spécialisée pour un type défini par l’utilisateur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<chrono >  
  
 **Espace de noms :** std::chrono  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


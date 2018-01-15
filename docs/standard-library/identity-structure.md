---
title: identity, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: utility/std::identity
dev_langs: C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9166383cbe79835cc3790826fc2e617eca22484
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="identity-structure"></a>identity, structure
Struct qui fournit une définition de type comme paramètre de modèle.  
  
## <a name="syntax"></a>Syntaxe  
```  
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };  
```  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Valeur à identifier.|  
  
## <a name="remarks"></a>Notes  
 La classe contient la définition de type public `type`, qui est la même que le paramètre de modèle Type. Elle est utilisée conjointement avec la fonction de modèle [forward](../standard-library/utility-functions.md#forward) pour s’assurer qu’un paramètre de fonction a le type souhaité.  
  
 Pour la compatibilité avec le code plus ancien, la classe définit également la fonction d’identité `operator()` qui retourne son argument `left`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<utility>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\<utility>](../standard-library/utility.md)




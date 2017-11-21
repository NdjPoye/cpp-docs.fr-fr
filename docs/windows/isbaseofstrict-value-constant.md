---
title: Isbaseofstrict::value, constante | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs: C++
helpviewer_keywords: value constant
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c63781976fadf4b90bfb4ad8f7687b13d7439bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="isbaseofstrictvalue-constant"></a>IsBaseOfStrict::value, constante
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
static const bool value = __is_base_of(Base, Derived);  
```  
  
## <a name="remarks"></a>Remarques  
 Indique si un type est la base d’un autre.  
  
 `value`est `true` si type `Base` est une classe de base du type `Derived`, sinon il est `false`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** internal.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [IsBaseOfStrict (Structure)](../windows/isbaseofstrict-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)
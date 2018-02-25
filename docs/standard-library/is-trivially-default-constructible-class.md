---
title: is_trivially_default_constructible, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd0b63b1f088eadf2ba2a253083d0f2878c2b751
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible, classe
Teste si le type a un constructeur par défaut trivial.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
struct is_trivially_default_constructible;
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un constructeur trivial. Sinon, sa valeur est false.  
  
 Un constructeur par défaut pour une classe `Ty` est trivial si :  
  
-   il s'agit d'un constructeur par défaut déclaré implicitement ;  
  
-   la classe `Ty` n'a aucune fonction virtuelle ;  
  
-   la classe `Ty` n'a aucune base virtuelle ;  
  
-   toutes les bases directes de la classe `Ty` ont des constructeurs triviaux ;  
  
-   les classes de tous les membres de données non statiques de type de classe ont des constructeurs triviaux ;  
  
-   les classes de tous les membres de données non statiques de type tableau de classe ont des constructeurs triviaux.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




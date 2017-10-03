---
title: time_base, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c1c7c6c708087827c853234dcbd4519c79fba2bf
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="timebase-class"></a>time_base, classe
La classe sert de classe de base pour les facettes de la classe de modèle time_get, définissant simplement le type énuméré **dateorder** et plusieurs constantes de ce type.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```  
  
## <a name="remarks"></a>Notes  
 Chaque constante caractérise une manière différente d’ordonner les composants d’une date. Les constantes sont :  
  
- **no_order** ne spécifie aucun ordre particulier.  
  
- **dmy** spécifie l’ordre jour, mois, année, comme dans 2 décembre 1979.  
  
- **mdy** spécifie l’ordre mois, jour, année, comme dans décembre 2, 1979.  
  
- **ymd** spécifie l’ordre année, mois, jour, comme dans 1979/12/2.  
  
- **ydm** spécifie l’ordre année, jour, mois, comme dans 1979: 2 déc.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)





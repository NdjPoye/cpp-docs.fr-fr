---
title: time_base, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: locale/std::time_base
dev_langs: C++
helpviewer_keywords: time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a91d10a1705e14663443c1471397478aad85b68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




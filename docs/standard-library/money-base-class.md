---
title: money_base, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: b9c41737288a4d323057b42f809dcbf4a3f2ff2c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="moneybase-class"></a>money_base, classe
Cette classe décrit une énumération et une structure communes à toutes les spécialisations de la classe de modèle [moneypunct](../standard-library/moneypunct-class.md).  
  
## <a name="syntax"></a>Syntaxe  
```    
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};  
```  
## <a name="remarks"></a>Remarques  
 L’énumération **part** décrit les valeurs possibles dans les éléments du champ de tableau dans le modèle de structure. Les valeurs de **part** sont les suivantes :  
  
- **none** pour faire correspondre zéro, un ou plusieurs espaces ou pour ne rien générer.  
  
- **sign** pour faire correspondre ou générer un signe positif ou négatif.  
  
- **space** pour faire correspondre zéro, un ou plusieurs espaces ou pour générer un espace.  
  
- **symbol** pour faire correspondre ou générer un symbole monétaire.  
  
- **value** pour faire correspondre ou générer une valeur monétaire.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)





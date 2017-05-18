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
- locale/std::money_base
- money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4af0f51a820fc0011285b6c5a690f496e8fd4afe
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

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





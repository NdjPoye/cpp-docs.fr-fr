---
title: unchecked_array_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unchecked_array_iterator
- stdext::unchecked_array_iterator
dev_langs:
- C++
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 850f1eced3ef5354a382d392c83b8180a18b4dfb
ms.lasthandoff: 02/24/2017

---
# <a name="uncheckedarrayiterator-class"></a>unchecked_array_iterator, classe
La classe `unchecked_array_iterator` vous permet d'encapsuler un tableau ou un pointeur dans un itérateur non vérifié. Utilisez cette classe comme wrapper (à l’aide de la fonction [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)) pour les tableaux ou pointeurs bruts en tant que moyen ciblé de gérer les avertissements de pointeur non vérifiés au lieu de désactiver globalement ces avertissements. Si possible, préférez la version vérifiée de cette classe, [checked_array_iterator](../standard-library/checked-array-iterator-class.md).  
  
> [!NOTE]
>  Cette classe est une extension Microsoft de la bibliothèque standard C++. Le code implémenté à l’aide de cette fonction ne peut pas être utilisé dans les environnements de build C++ standard qui ne prennent pas en charge cette extension Microsoft.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Iterator>  
class unchecked_array_iterator;
```  
  
## <a name="remarks"></a>Notes  
 Cette classe est définie dans l’espace de noms [stdext](../standard-library/stdext-namespace.md).  
  
 Il s’agit de la version non vérifiée de la [classe checked_array_iterator](../standard-library/checked-array-iterator-class.md) qui prend en charge les mêmes surcharges et les mêmes membres. Pour plus d’informations sur la fonctionnalité d’itérateur vérifié et obtenir des exemples de code, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** stdext  
  
## <a name="see-also"></a>Voir aussi  
 [\<iterator>](../standard-library/iterator.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)





---
title: bad_exception, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.bad_exception
- bad_exception
- std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7870c00b019718188b80a64e0102638deb76f588
ms.lasthandoff: 02/24/2017

---
# <a name="badexception-class"></a>bad_exception, classe
La classe décrit une exception pouvant être levée à partir d’un gestionnaire d’exceptions inattendues.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Notes  
 [unexpected](../standard-library/exception-functions.md#unexpected) lève un `bad_exception` au lieu de terminer ou d’appeler une autre fonction spécifiée par [set_unexpected](../standard-library/exception-functions.md#set_unexpected) si `bad_exception` est inclus dans la liste d’exceptions levées d’une fonction.  
  
 La valeur retournée par **what** est une chaîne C définie par l’implémentation. Aucune des fonctions membres ne lève d'exception.  
  
 Pour obtenir la liste des membres hérités par la classe `bad_exception`, consultez [exception, classe](../standard-library/exception-class.md).  
  
## <a name="example"></a>Exemple  
 Consultez [set_unexpected](../standard-library/exception-functions.md#set_unexpected) pour obtenir un exemple d’utilisation de la fonction [unexpected](../standard-library/exception-functions.md#unexpected) levant un `bad_exception`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<exception>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
[exception, classe](../standard-library/exception-class.md)
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)


---
title: bad_exception, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception/std::bad_exception
dev_langs: C++
helpviewer_keywords: bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5b91f3019a46aa011f95ae26434456d1e41de08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<exception>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
[exception, classe](../standard-library/exception-class.md) [sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)


---
title: "bad_exception, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.bad_exception"
  - "bad_exception"
  - "std::bad_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_exception (classe)"
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bad_exception, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe décrit une exception qui peut être levée à partir d’un gestionnaire d’exceptions inattendue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Remarques  
 [inattendue](../Topic/%3Cexception%3E%20functions.md#unexpected) lèvera une `bad_exception` au lieu de mettre fin ou au lieu d’appeler une autre fonction spécifiée avec [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) Si `bad_exception` est inclus dans la liste de la levée d’une fonction.  
  
 La valeur retournée par **que** est une chaîne définie par l’implémentation de C. Aucune des fonctions membres ne lève d'exception.  
  
 Pour obtenir la liste des membres hérités par les `bad_exception` de classe, consultez la page [exception, classe](../standard-library/exception-class1.md).  
  
## <a name="example"></a>Exemple  
 Consultez la page [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) pour obtenir un exemple d’utilisation de [inattendue](../Topic/%3Cexception%3E%20functions.md#unexpected) lever un `bad_exception`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< exception>  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
[exception, classe](../standard-library/exception-class1.md)
 [sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)


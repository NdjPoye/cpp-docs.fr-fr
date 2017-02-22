---
title: "unchecked_array_iterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unchecked_array_iterator"
  - "stdext::unchecked_array_iterator"
dev_langs: 
  - "C++"
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# unchecked_array_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe `unchecked_array_iterator` vous permet d'encapsuler un tableau ou un pointeur dans un itérateur non vérifié.  Utilisez cette classe comme wrapper \(à l'aide de la fonction [make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md)\) pour les pointeurs ou tableaux bruts en tant que moyen ciblé de gérer les avertissements de pointeur non vérifiés au lieu de désactiver globalement ces avertissements.  Si possible, préférez la version activée de cette classe, [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md).  
  
> [!NOTE]
>  Cette classe est une extension Microsoft de la bibliothèque C\+\+ standard.  Le code implémenté à l'aide de cette fonction ne peut pas être utilisé dans les environnements de build C\+\+ standard qui ne prennent pas en charge cette extension Microsoft.  
  
## Syntaxe  
  
```  
template <class Iterator>  
    class unchecked_array_iterator;  
```  
  
## Notes  
 Cette classe est définie dans l'espace de noms [stdext](../standard-library/stdext-namespace.md).  
  
 Il s'agit de la version non contrôlée de la [classe checked\_array\_iterator](../standard-library/checked-array-iterator-class.md) qui prend en charge les mêmes surcharges et les mêmes membres.  Pour plus d'informations sur la fonctionnalité d'itérateur vérifié et obtenir des exemples de code, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)
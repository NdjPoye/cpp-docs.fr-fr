---
title: "Vector::First (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::First (méthode)"
ms.assetid: ca6b7b55-dd49-4346-bfa4-d8010b228d44
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::First (m&#233;thode)
Retourne un itérateur qui pointe vers le premier élément du Vector.  
  
## Syntaxe  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^   
   First();  
```  
  
## Valeur de retour  
 Itérateur qui pointe vers le premier élément du Vector.  
  
## Notes  
 Un moyen pratique de contenir l'itérateur retourné par First\(\) est d'assigner la valeur de retour à une variable déclarée avec le mot clé de déduction de type [auto](~/cpp/auto-cpp.md). Par exemple, `auto x = myVector->First();`. Cet itérateur connaît la longueur de la collection.  
  
 Quand vous avez besoin d'une paire d'itérateurs à passer à une fonction STL, utilisez les fonctions libres [Windows::Foundation::Collections::begin](../cppcx/begin-function.md) et [Windows::Foundation::Collections::end](../cppcx/end-function.md)  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)   
 [Collections](../cppcx/collections-c-cx.md)
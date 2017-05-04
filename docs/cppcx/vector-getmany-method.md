---
title: "Vector::GetMany (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetMany (méthode)"
ms.assetid: e2d5ccf4-101a-47e5-a0d8-56f65a7ff28d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetMany (m&#233;thode)
Récupère une séquence d'éléments du Vector actif en commençant à l'index spécifié et les copie dans le tableau alloué par l'appelant.  
  
## Syntaxe  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
#### Paramètres  
 `startIndex`  
 L'index de base zéro du début des éléments à récupérer.  
  
 `dest`  
 Un tableau alloué par l'appelant des éléments qui commencent à l'élément spécifié par `startIndex` et se terminent au dernier élément du Vector.  
  
## Valeur de retour  
 Le nombre d'éléments à récupérer.  
  
## Notes  
 Cette fonction n'est pas destinée à être utilisée directement par le code client. Elle est utilisée en interne dans la [fonction to\_vector](../cppcx/to-vector-function.md) pour permettre la conversion des instances Platform::Vector en instances std::vector.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)
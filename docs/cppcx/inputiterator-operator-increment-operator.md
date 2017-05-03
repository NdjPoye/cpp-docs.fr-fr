---
title: "InputIterator::operator++ (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator++ (opérateur)"
ms.assetid: 50781585-7a12-4f02-bff8-68fe0adf0693
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator++ (op&#233;rateur)
Incrémente l'objet InputIterator actuel.  
  
## Syntaxe  
  
```  
  
InputIterator& operator++();  
  
InputIterator operator++(  
   int  
);  
```  
  
## Valeur de retour  
 La première syntaxe incrémente l'objet InputIterator actuel puis le retourne. La deuxième syntaxe retourne une copie de l'objet InputIterator actuel, puis incrémente l'objet InputIterator actuel.  
  
## Notes  
 La première syntaxe InputIterator préincrémente l'objet InputIterator actuel.  
  
 La deuxième syntaxe postincrémente l'objet InputIterator actuel. Le type `int` dans la deuxième syntaxe n'indique pas un opérande entier réel mais une post\-incrémentation.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::InputIterator, classe](../cppcx/platform-collections-inputiterator-class.md)
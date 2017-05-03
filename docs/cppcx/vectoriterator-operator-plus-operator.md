---
title: "VectorIterator::operator+ (op&#233;rateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator+ (opérateur)"
ms.assetid: 5e907537-7d10-4766-a412-e7ea08b3456a
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator+ (op&#233;rateur)
Retourne un VectorIterator qui référence l'élément spécifié au décalage spécifié à partir du VectorIterator spécifié.  
  
## Syntaxe  
  
```  
  
VectorIterator operator+(  
   difference_type n) ;  
  
template <  
   typename T  
>  
inline VectorIterator<T> operator+(  
   ptrdiff_t n,  
   const VectorIterator<T>& i  
);  
  
```  
  
#### Paramètres  
 `T`  
 Dans la deuxième syntaxe, typename du VectorIterator.  
  
 `n`  
 Déplacement d'un entier.  
  
 `i`  
 Dans la deuxième syntaxe, un VectorIterator.  
  
## Valeur de retour  
 Dans la première syntaxe, VectorIterator qui référence l'élément spécifié au décalage spécifié à partir du VectorIterator actuel.  
  
 Dans la deuxième syntaxe, VectorIterator qui référence l'élément au décalage spécifié à partir du début du paramètre `i`.  
  
## Notes  
 Exemple pour la première syntaxe  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)
---
title: "Vector::IndexOf (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::IndexOf (méthode)"
ms.assetid: 4a965992-3858-4e3f-992a-b94c0580b2f7
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::IndexOf (m&#233;thode)
Recherche l'élément spécifié dans l'objet Vector actuel, et s'il existe, retourne l'index de l'élément.  
  
## Syntaxe  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
#### Paramètres  
 `value`  
 Élément à rechercher.  
  
 `index`  
 Index de base zéro de l'élément si le paramètre `value` est détecté ; sinon, 0.  
  
 Le paramètre `index` est égal à 0 si l'élément est le premier élément du vecteur ou que l'élément est introuvable. Si la valeur de retour est `true`, l'élément est trouvé et représente le premier élément ; sinon, l'élément est introuvable.  
  
## Valeur de retour  
 `true` si l'élément spécifié est trouvé ; sinon, `false`.  
  
## Notes  
 IndexOf uses std::find\_if pour trouver l'élément. Les types d'élément personnalisés doivent surcharger les opérateurs \=\= et \!\= afin d'autoriser les comparaisons d'égalité requises par find\_if.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)
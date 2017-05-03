---
title: "VectorView::IndexOf (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::IndexOf (méthode)"
ms.assetid: 848117ec-ad4a-4a0b-9c1e-9076e5188869
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::IndexOf (m&#233;thode)
Recherche l'élément spécifié dans l'objet VectorView actuel, et s'il existe, retourne l'index de l'élément.  
  
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
  
 Le paramètre `index` est égal à 0 si l'élément est le premier élément du VectorView ou que l'élément est introuvable. Si la valeur de retour est `true`, l'élément est trouvé et représente le premier élément ; sinon, l'élément est introuvable.  
  
## Valeur de retour  
 `true` si l'élément spécifié est trouvé ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [VectorView Class](http://msdn.microsoft.com/fr-fr/79697692-ae58-40e0-958f-cf1be6347994)
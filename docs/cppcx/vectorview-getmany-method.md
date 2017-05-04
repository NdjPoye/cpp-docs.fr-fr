---
title: "VectorView::GetMany (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetMany (méthode)"
ms.assetid: 67d9348f-66fe-417e-9e25-5de0a3cd306c
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetMany (m&#233;thode)
Récupère une séquence d'éléments du VectorView actif en commençant à l'index spécifié.  
  
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
 Quand cette opération se termine, un tableau d’éléments qui commencent à l’élément spécifié par `startIndex` et se terminent au dernier élément du VectorView.  
  
## Valeur de retour  
 Le nombre d'éléments à récupérer.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [VectorView Class](http://msdn.microsoft.com/fr-fr/79697692-ae58-40e0-958f-cf1be6347994)
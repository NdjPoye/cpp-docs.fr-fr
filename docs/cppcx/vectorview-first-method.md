---
title: "VectorView::First (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::First (méthode)"
ms.assetid: 543a5c5b-8ce3-4be3-9fad-726928de7855
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::First (m&#233;thode)
Retourne un itérateur qui spécifie le premier élément du VectorView.  
  
## Syntaxe  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
## Valeur de retour  
 Itérateur qui spécifie le premier élément de l'objet VectorView.  
  
## Notes  
 Un moyen pratique de contenir l'itérateur retourné par First\(\) est d'assigner la valeur de retour à une variable déclarée avec le mot clé de déduction de type [auto](../Topic/auto%20\(C++\).md). Par exemple, `auto x = myVectorView->First();`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [VectorView Class](http://msdn.microsoft.com/fr-fr/79697692-ae58-40e0-958f-cf1be6347994)
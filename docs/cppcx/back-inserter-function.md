---
title: "back_inserter (fonction) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::back_inserter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_inserter (fonction)"
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# back_inserter (fonction)
Retourne un itérateur qui est utilisé pour insérer des éléments à la fin de la collection spécifiée.  
  
## Syntaxe  
  
```  
  
template <  
   typename T  
   >  
   ::Platform::BackInsertIterator<T>   
    back_inserter(  
                  IVector<T>^ v  
                 );  
  
template <  
   typename T  
   >  
   ::Platform::BackInsertIterator<T>   
   back_inserter(  
                IObservableVector<T>^ v  
                );  
```  
  
#### Paramètres  
 `T`  
 Paramètre de type de modèle.  
  
 `v`  
 Pointeur d'interface qui permet d'accéder à la collection sous\-jacente.  
  
## Valeur de retour  
 Itérateur.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Windows::Foundation::Collections  
  
## Voir aussi  
 [Windows::Foundation::Collections, espace de noms](../cppcx/windows-foundation-collections-namespace-c-cx.md)
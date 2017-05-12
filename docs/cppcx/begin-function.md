---
title: "begin (fonction) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin (fonction)"
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# begin (fonction)
Retourne un itérateur qui pointe vers le début d'une collection accessible par le paramètre d'interface spécifié.  
  
## Syntaxe  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### Paramètres  
 `T`  
 Paramètre de type de modèle.  
  
 `v`  
 Collection d'objets Vector\<T\> ou VectorView\<T\> accessibles par une interface IVector\<T\> ou IVectorView\<T\>.  
  
 `i`  
 Collection d'objets [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] arbitraires accessibles par une interface IIterable\<T\> .  
  
## Valeur de retour  
 Itérateur qui pointe vers le début de la collection.  
  
## Notes  
 Les deux premières fonctions de modèle retournent des itérateurs et la troisième fonction de modèle retourne un itérateur d'entrée.  
  
 L'objet VectorIterator retourné par begin est un itérateur de proxy qui stocke des éléments de type VectorProxy\<T\>. Toutefois, l'objet proxy n'est presque jamais visible par le code utilisateur. Pour plus d'informations, consultez [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Windows::Foundation::Collections  
  
## Voir aussi  
 [Windows::Foundation::Collections, espace de noms](../cppcx/windows-foundation-collections-namespace-c-cx.md)
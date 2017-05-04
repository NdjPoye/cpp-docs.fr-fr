---
title: "end (fonction) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end (fonction)"
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# end (fonction)
Retourne un itérateur qui pointe au\-delà de la fin d'une collection accessible par le paramètre d'interface spécifié.  
  
## Syntaxe  
  
```  
  
template <typename T>  
    ::Platform::Collections::VectorIterator<T>   
    end(  
        IVector<T>^ v       );  
  
template <typename T>  
    ::Platform::Collections::VectorViewIterator<T>   
    end(  
        IVectorView<T>^ v  
       );  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    end(  
        IIterable<T>^ i  
       );  
  
```  
  
#### Paramètres  
 `T`  
 Paramètre de type de modèle.  
  
 `v`  
 Collection d'objets Vector\<T\> ou VectorView\<T\> accessibles par une interface IVector\<T\> ou IVectorView\<T\>.  
  
 `i`  
 Collection d'objets [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] arbitraires accessibles par une interface IIterable\<T\> .  
  
## Valeur de retour  
 Itérateur qui pointe au\-delà de la fin de la collection.  
  
## Notes  
 Les deux premières fonctions de modèle retournent des itérateurs et la troisième fonction de modèle retourne un itérateur d'entrée.  
  
 L'objet [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) retourné par `end` est un itérateur de proxy qui stocke des éléments de type `VectorProxy<T>`. Toutefois, l'objet proxy n'est presque jamais visible par le code utilisateur. Pour plus d'informations, consultez [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Windows::Foundation::Collections  
  
## Voir aussi  
 [Windows::Foundation::Collections, espace de noms](../cppcx/windows-foundation-collections-namespace-c-cx.md)
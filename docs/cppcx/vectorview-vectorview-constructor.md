---
title: "VectorView::VectorView (constructeur) | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::VectorView (constructeur)"
ms.assetid: 5ec14dbc-5f6f-44b6-8fc4-f5a31053eb5f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::VectorView (constructeur)
Initialise une nouvelle instance de la classe VectorView.  
  
## Syntaxe  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
#### Paramètres  
 `InIt`  
 Type d'une collection d'objets utilisée pour initialiser le VectorView actif.  
  
 il  
 [std::initializer\_list](../standard-library/initializer-list-class.md) dont les éléments sont utilisés pour initialiser le VectorView.  
  
 `N`  
 Nombre d'éléments d'une collection d'objets utilisée pour initialiser le VectorView actif.  
  
 `size`  
 Nombre d'éléments du VectorView.  
  
 `value`  
 Valeur utilisée pour initialiser chaque élément du VectorView actif.  
  
 `v`  
 [Lvalues et Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) à un [::std::vector](../Topic/vector%20Class%201.md) utilisé pour initialiser le VectorView actif.  
  
 `ptr`  
 Pointeur vers un `std::vector` utilisé pour initialiser le VectorView actif.  
  
 `arr`  
 Objet [Platform::Array](../cppcx/platform-array-class.md) utilisé pour initialiser le VectorView actif.  
  
 `a`  
 Objet [std::array](../Topic/vector%20Class%201.md) utilisé pour initialiser le VectorView actif.  
  
 `first`  
 Premier élément d'une séquence d'objets utilisée pour initialiser le VectorView actif. Le type `first` est passé au moyen du *transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence Rvalue : &&](~/cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Dernier élément d'une séquence d'objets utilisée pour initialiser le VectorView actif. Le type `last` est passé au moyen du *transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence Rvalue : &&](~/cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)
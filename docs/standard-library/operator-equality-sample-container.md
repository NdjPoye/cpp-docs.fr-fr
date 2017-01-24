---
title: "operator== (&lt;sample container&gt;) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.=="
  - "std::=="
  - "operator=="
  - "std.operator=="
  - "std::operator=="
  - "=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "== (opérateur), avec des objets C++ standard spécifiques"
  - "opérateur ==, conteneurs"
  - "== (opérateur), conteneurs"
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator== (&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple fonctionnel de conteneurs utilisés dans la bibliothèque C\+\+ standard.  Pour plus d'informations, consultez l'[Conteneurs STL de](../standard-library/stl-containers.md).  
  
 Surcharge `operator==` pour comparer deux objets de classe de modèle [Conteneur](../standard-library/sample-container-class.md).  
  
## Syntaxe  
  
```  
  
   template<class Ty>  
bool operator==(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Valeur de retour  
 Retourne `_Left`**.**[taille](../standard-library/container-class-size.md) **\=\=** `_Right`**.size && equal**\(\_*Left***.**[begin](../standard-library/container-class-begin.md), `_Left`.  [end](../standard-library/container-class-end.md)*, \_Right***.begin**\).  
  
## Voir aussi  
 [\<sample container\>](../standard-library/sample-container.md)
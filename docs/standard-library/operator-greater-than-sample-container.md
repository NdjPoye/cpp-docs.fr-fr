---
title: "operator&gt; (&lt;sample container&gt;) | Microsoft Docs"
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
  - "std::operator>"
  - "std.>"
  - "std.operator>"
  - "operator>"
  - "std::>"
  - ">"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "> (opérateur), comparer des objets spécifiques"
  - "opérateur >"
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator&gt; (&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique figure dans la documentation Visual C\+\+ comme exemple non fonctionnel de conteneurs utilisés dans la Libraire C\+\+ Standard.  Pour plus d'informations, consultez [Conteneurs STL](../standard-library/stl-containers.md).  
  
 Surcharge l' **opérateur\>\=** pour comparer deux objets de classe de modèle [Conteneur](../standard-library/sample-container-class.md).  
  
## Syntaxe  
  
```  
  
   template<class Ty>  
bool operator*gt;(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Valeur de retour  
 Retourne \_*Right* \< \_*Left*.  
  
## Voir aussi  
 [\<sample container\>](../standard-library/sample-container.md)
---
title: "operator&lt; (&lt;sample container&gt;) | Microsoft Docs"
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
  - "std::operator<"
  - "operator<"
  - "std.<"
  - "<"
  - "std.operator<"
  - "std::<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "< (opérateur)"
  - "< (opérateur), comparer des objets spécifiques"
  - "< (opérateur), valarrays"
  - "< (opérateur), valarrays"
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator&lt; (&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C\+\+ comme exemple non fonctionnel de conteneurs utilisés dans la Libraire C\+\+ Standard.  Pour plus d'informations, consultez [STL Conteneurs](../standard-library/stl-containers.md).  
  
 Surcharge l' **opérateur\<\=** pour comparer deux objets de classe de modèle [Conteneur](../standard-library/sample-container-class.md).  
  
## Syntaxe  
  
```  
  
   template<class Ty>  
bool operator<(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Valeur de retour  
 Retourne `lexicographical_compare`\(\_*Gauche*.  [démarrer](../standard-library/container-class-begin.md), \_*gauche*.  [fin](../standard-library/container-class-end.md), \_*Droite***.démarrer**, \_*Droite*.**fin**\).  
  
## Voir aussi  
 [\<sample container\>](../standard-library/sample-container.md)
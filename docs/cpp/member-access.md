---
title: "Acc&#232;s aux membres | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accès aux membres, opérateurs surchargés"
  - "opérateurs de sélection de membres"
  - "surcharge d'opérateur, opérateurs d'accès au membre"
  - "pointeurs, intelligents"
  - "pointeurs intelligents"
  - "pointeurs intelligents, définition"
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s aux membres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'accès au membre de classe peut être contrôlé en surchargeant l'opérateur d'accès au membre \(**–\>**\).  Cet opérateur est considéré comme un opérateur unaire dans cette utilisation, et la fonction surchargée d'opérateur doit être une fonction membre de classe.  Par conséquent, la déclaration pour une telle fonction est :  
  
## Syntaxe  
  
```  
  
class-type *operator–>()  
```  
  
## Notes  
 où *class\-type* représente le nom de la classe à laquelle cet opérateur appartient.  La fonction opérateur d'accès au membre doit être une fonction membre non statique.  
  
 Cet opérateur est utilisé \(souvent avec l'opérateur pointer\-dereference\) pour implémenter des « pointeurs intelligents » qui valident les pointeurs avant de déréférencer ou de compter l'utilisation.  
  
 L'opérateur d'accès au membre **.** ne peut pas être surchargé.  
  
## Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)
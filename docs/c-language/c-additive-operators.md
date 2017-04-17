---
title: "Op&#233;rateurs additifs C | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "+ (opérateur), opérateurs additifs"
  - "opérateurs additifs"
  - "opérateurs arithmétiques (C++), opérateurs additifs"
  - "opérateurs (C), addition"
  - "conversions arithmétiques courantes"
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs additifs C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs additifs exécutent une addition \(**\+**\) et une soustraction \(**–**\).  
  
## Syntaxe  
 *additive\-expression* :  
 *multiplicative\-expression*  
  
 *additive\-expression*  **\+**  *multiplicative\-expression*  
  
 *additive\-expression*  **–**  *multiplicative\-expression*  
  
> [!NOTE]
>  Bien que la syntaxe de l'élément *additive\-expression* inclue *multiplicative\-expression*, cela n'implique pas l'obligation d'utiliser des expressions avec multiplication.  Consultez la syntaxe dans [Résumé de syntaxe du langage C](../c-language/c-language-syntax-summary.md), pour les éléments *multiplicative\-expression*, *cast\-expression* et *unary\-expression*.  
  
 Les opérandes peuvent être des valeurs intégrales ou flottantes.  Certaines opérations additives peuvent également être exécutées sur des valeurs de pointeur, comme l'indique la description de chaque opérateur.  
  
 Les opérateurs additifs exécutent les conversions arithmétiques habituelles sur les opérandes de type entier et flottant.  Le type du résultat est le type des opérandes après conversion.  Étant donné que les conversions exécutées par les opérateurs additifs ne fournissent pas de conditions de dépassement de capacité positif ou de dépassement de capacité négatif, les informations risquent d'être perdues si le résultat d'une opération additive ne peut pas être représenté dans le type des opérandes après conversion.  
  
## Voir aussi  
 [Opérateurs additifs : \+ et \-](../cpp/additive-operators-plus-and.md)
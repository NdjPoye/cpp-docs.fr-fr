---
title: "Avertissement du compilateur (niveau 1) C4407 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4407"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4407"
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Avertissement du compilateur (niveau 1) C4407
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cast entre différentes représentations du pointeur en membre, le compilateur peut générer du code incorrect  
  
 Un cast de type incorrect a été détecté.  
  
 L'erreur C4407 peut être due à la mise en conformité du compilateur pour Visual C\+\+ 2005.  Le pointeur de membre nécessite désormais un nom qualifié et un opérateur d'adresse \(&\).  
  
 L'erreur C4407 peut se produire si vous effectuez un cast entre un pointeur de membre à héritage multiple et un pointeur de membre à héritage unique.  Cela ne fonctionne pas toujours, car la représentation du pointeur de membre à héritage unique ne contient pas d'informations suffisantes.  La compilation à l'aide de **\/vmm** peut être utile \(pour plus d'informations, consultez [\/vmm, \/vms, \/vmv \(Représentation à but général\)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)\).  Vous pouvez également essayer de réorganiser vos classes de base ; le compilateur détecte une perte d'informations lors de la conversion parce qu'une classe de base se situe à un offset différent de zéro de la classe dérivée.  
  
 L'exemple suivant génère l'erreur C4407 :  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```
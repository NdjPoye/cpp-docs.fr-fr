---
title: Compilateur avertissement (niveau 1) C4407 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4407
dev_langs: C++
helpviewer_keywords: C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e536695670e8b5443a56425e098f6e6a6e97c45a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4407"></a>Avertissement du compilateur (niveau 1) C4407
cast entre différentes représentations du pointeur en membre, le compilateur peut générer du code incorrect  
  
 Un cast incorrect a été détecté.  
  
 L’erreur C4407 peut être généré en conformité du compilateur pour Visual C++ 2005. Pointeur vers membre requiert désormais un nom qualifié et l’opérateur d’adresse (&).  
  
 L’erreur C4407 peut se produire si vous effectuez un cast entre un héritage plusieurs pointeur vers membre à un héritage simple pointeur vers membre. Parfois, cette solution puisse fonctionner, mais parfois, il ne peut pas, car la représentation sous forme de pointeur vers membre de l’héritage unique ne contient pas suffisamment d’informations. La compilation avec le **/VMM** peut vous aider (pour plus d’informations, consultez [/VMM, / VMS, /vmv (représentation à but général)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). Vous pouvez également essayer de réorganiser vos classes de base ; le compilateur détecte une perte d’informations dans la conversion, car une classe de base est à un offset différent de zéro à partir de la liste dérivée.  
  
 L’exemple suivant génère l’erreur C4407 :  
  
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
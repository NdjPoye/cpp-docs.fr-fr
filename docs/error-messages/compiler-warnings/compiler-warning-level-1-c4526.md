---
title: Compilateur avertissement (niveau 1) C4526 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4526
dev_langs: C++
helpviewer_keywords: C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 00ffa9e20781d8d5d1405d6bf5546b47a6530b88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4526"></a>Avertissement du compilateur (niveau 1) C4526
'fonction' : fonction membre statique ne peut pas substituer la fonction virtuelle ' substitution ignorée, fonction virtual sera masquée  
  
 La fonction membre statique correspondant aux critères pour remplacer la fonction virtuelle, ce qui rend la fonction membre virtuelle et statique.  
  
 Le code suivant génère C4526 :  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Solutions possibles sont les suivantes :  
  
-   Si la fonction était destinée à remplacer la fonction virtuelle de classe de base, supprimez le spécificateur statique.  
  
-   Si la fonction était destinée à être une fonction membre statique, renommez-la afin qu’il n’entre en conflit avec la fonction virtuelle de classe de base.
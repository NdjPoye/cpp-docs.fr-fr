---
title: "Transferts de contrôle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a604c95bb21ad0098a3d4563738971791fc94a07
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="transfers-of-control"></a>Transferts de contrôle
Vous pouvez utiliser la `goto` instruction ou un **cas** étiquette dans un `switch` pour spécifier un programme branche après un initialiseur d’instruction. Ce code est conforme sauf si la déclaration qui contient l'initialiseur figure dans un bloc se trouvant lui-même dans le bloc dans lequel l'instruction de saut s'exécute.  
  
 L'exemple suivant montre une boucle qui déclare et initialise les objets `total`, `ch` et `i`. Il comporte également une instruction `goto` erronée qui transfère le contrôle après un initialiseur.  
  
```  
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 Dans l'exemple précédent, l'instruction `goto` tente de transférer le contrôle après l'initialisation de `i`. Toutefois, si `i` était déclaré mais non initialisé, le transfert serait conforme.  
  
 Les objets `total` et `ch`, déclarés dans le bloc qui sert le *instruction* de la `while` instruction, sont détruits lors de la sortie de ce bloc à l’aide de la `break` instruction.  
  


---
title: Transferts de contrôle | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ee906061c7b51ade818b164c1d371a88ef3d462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
  

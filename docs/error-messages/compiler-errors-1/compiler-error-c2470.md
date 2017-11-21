---
title: Erreur du compilateur C2470 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2470
dev_langs: C++
helpviewer_keywords: C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b55813f0945bc1445cf956b153a2f72f09b35ba2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2470"></a>Erreur du compilateur C2470
'fonction' : similaire à une définition de fonction, mais il n’existe aucune liste de paramètres ; corps apparent ignoré  
  
 Il manque sa liste d’arguments dans une définition de fonction.  
  
 L’exemple suivant génère l’erreur C2470 :  
  
```  
// C2470.cpp  
int MyFunc {};  // C2470  
void MyFunc2() {};  //OK  
  
int main(){  
   MyFunc();  
   MyFunc2();  
}  
```
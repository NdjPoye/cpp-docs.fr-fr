---
title: Erreur du compilateur C3417 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3417
dev_langs: C++
helpviewer_keywords: C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e25adc1b699998235c1cfa16edbb50c2b774f983
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3417"></a>Erreur du compilateur C3417
'membre' : les types valeur ne peut pas contenir les fonctions membres spéciales définies par l’utilisateur  
  
 Types valeur ne peut pas contenir de fonctions telles que d’un constructeur d’instance par défaut, un destructeur ou un constructeur de copie.  
  
 L’exemple suivant génère l’erreur C3517 :  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```
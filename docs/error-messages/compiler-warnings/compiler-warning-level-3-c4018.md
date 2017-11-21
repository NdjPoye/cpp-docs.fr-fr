---
title: "Du compilateur (niveau 3) d’avertissement C4018 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4018
dev_langs: C++
helpviewer_keywords: C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f409075947d6151c643f477513986b6dee50ee65
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4018"></a>Du compilateur (niveau 3) d’avertissement C4018
'expression' : incompatibilité signed/unsigned  
  
 Comparaison d’un nombre signé et non signé requiert que le compilateur pour convertir la valeur de signé en non signé.  
  
 Cet avertissement peut être résolu si vous transformez un des deux types lors du test des types signés et non signés.  
  
 L’exemple suivant génère l’erreur C4018 :  
  
```  
// C4018.cpp  
// compile with: /W3  
int main() {  
   unsigned int uc = 0;  
   int c = 0;  
   unsigned int c2 = 0;  
  
   if (uc < c) uc = 0;   // C4018  
  
   // OK  
   if (uc == c2) uc = 0;  
}  
```
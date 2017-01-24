---
title: "Erreur irr&#233;cup&#233;rable C1094 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1094"
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\-Zmval1' : option de ligne de commande non cohérente avec la valeur utilisée pour générer l'en\-tête précompilé \('\-Zmval2'\)  
  
 La valeur passée à [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) doit être identique à celle passée à [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) \(les valeurs **\/Zm** doivent être identiques dans toutes les compilations qui utilisent ou créent le même fichier d'en\-tête précompilé\).  
  
 L'exemple suivant génère l'erreur C1094 :  
  
```  
// C1094.h  
int func1();  
```  
  
 Ensuite,  
  
```  
// C1094.cpp  
// compile with: /Yc"C1094.h" /Zm200  
int u;  
int main() {  
   int sd = 32;  
}  
#include "C1094.h"  
```  
  
 Ensuite,  
  
```  
// C1094b.cpp  
// compile with: /Yu"C1094.h" /Zm300 /c  
#include "C1094.h"   // C1094 compile with /Zm200  
void Test() {}  
```
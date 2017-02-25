---
title: "Avertissement du compilateur (niveau 1) C4508 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4508"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4508"
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4508
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la fonction doit retourner une valeur ; type de retour 'void' pris par défaut  
  
 La fonction n'a pas de type de retour spécifié.  Dans ce cas, l'erreur C4430 devrait également se déclencher et le compilateur implémente le correctif signalé par l'erreur C4430 \(la valeur par défaut est int\).  
  
 Pour résoudre cet avertissement, déclarez explicitement le type de retour des fonctions.  
  
 L'exemple suivant génère l'erreur C4508 :  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```
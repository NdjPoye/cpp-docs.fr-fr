---
title: "Erreur du compilateur C2491 | Microsoft Docs"
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
  - "C2491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2491"
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : définition de la fonction dllimport non autorisée  
  
 Données, données membres static et fonctions peuvent être déclarées comme `dllimport` mais pas définies comme `dllimport`.  
  
 Pour résoudre ce problème, supprimez le spécificateur `__declspec(dllimport)` de la définition de la fonction.  
  
 L'exemple suivant génère l'erreur C2491 :  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```
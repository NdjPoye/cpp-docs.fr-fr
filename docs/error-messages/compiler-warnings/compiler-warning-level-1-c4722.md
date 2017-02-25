---
title: "Avertissement du compilateur (niveau&#160;1) C4722 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4722"
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : aucun retour du destructeur, fuite de mémoire possible  
  
 Le flux de contrôle se termine dans un destructeur. Le thread ou la totalité du programme va se terminer et les ressources allouées risquent de ne pas être libérées.  En outre, si un destructeur est appelé pour le déroulement de pile pendant le traitement de l’exception, le comportement du fichier exécutable est indéfini.  
  
 Pour résoudre ce problème, supprimez l’appel de fonction qui provoque le non\-retour du destructeur.  
  
## Exemple  
 L’exemple suivant génère l’erreur C4722 :  
  
```  
// C4722.cpp // compile with: /O1 /W1 /c #include <stdlib.h> class C { public: C(); ~C() { exit(1); };   // C4722 }; extern void func (C*); void Test(){ C x; func(&x); // control will not leave Test because destructor will exit }  
```
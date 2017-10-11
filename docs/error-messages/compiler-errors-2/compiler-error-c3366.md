---
title: Erreur du compilateur C3366 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b862e606b86eca0a7eb7f2ad1e91f2776c8c0b23
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3366"></a>Erreur du compilateur C3366
'variable' : données membres static des gérés ou WinRTtypes doit être défini dans la définition de classe  
  
 Vous avez tenté de référencer un membre statique d'une interface ou d'une classe WinRT ou .NET à l'extérieur de la définition de cette classe ou interface.  
  
 Le compilateur doit connaître la définition complète de la classe (pour émettre les métadonnées après une passe) et exige l'initialisation des membres de données statiques dans la classe.  
  
 Par exemple, l'exemple suivant génère l'erreur C3366 et montre comment la corriger :  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  


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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d94d3a18c02cfe81f6c3ee96635c9388f54308d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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

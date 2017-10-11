---
title: Erreur du compilateur C3246 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 262dc8bde5dcb4c12909c69bce3fa867685245eb
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3246"></a>Erreur du compilateur C3246
'classe' : ne peut pas hériter de 'type', car il a été déclaré comme 'sealed'  
  
Une classe marquée [sealed](../../windows/sealed-cpp-component-extensions.md) ne peut pas être la classe de base d’autres classes.  
  
L’exemple suivant génère l’erreur C3246 :  
  
```  
// C3246_2.cpp  
// compile with: /clr /LD  
ref class X sealed {};  
  
ref class Y : public X {}; // C3246  
```  


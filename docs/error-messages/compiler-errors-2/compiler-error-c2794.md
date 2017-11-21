---
title: Erreur du compilateur C2794 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2794
dev_langs: C++
helpviewer_keywords: C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b25829804bf8cb375507550f339022d09951d35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2794"></a>Erreur du compilateur C2794
'fonction' : n’est pas un membre de n’importe quelle classe de base directe ou indirecte de 'classe'  
  
 Vous avez essayé d’utiliser [super](../../cpp/super.md) pour appeler une fonction membre qui n’existe pas.  
  
 L’exemple suivant génère C2794  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```
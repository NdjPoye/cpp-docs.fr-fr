---
title: Erreur du compilateur C2351 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2351
dev_langs: C++
helpviewer_keywords: C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 954b610ede6d00e1f9f4d0b3630c67566534355a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2351"></a>Erreur du compilateur C2351
syntaxe obsolète d’initialisation constructeur C++  
  
 Dans une liste d’initialisation de nouveau style pour un constructeur, vous devez nommer explicitement chaque classe de base directe, même si elle est la seule classe de base.  
  
 L’exemple suivant génère l’erreur C2351 :  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```
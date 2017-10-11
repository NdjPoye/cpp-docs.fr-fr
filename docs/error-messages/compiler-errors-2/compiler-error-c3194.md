---
title: Erreur du compilateur C3194 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3194
dev_langs:
- C++
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4ddfc0c87f4f58850eec595dcf35436590177283
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3194"></a>Erreur du compilateur C3194
'membre' : un type valeur ne peut pas avoir un opérateur d’assignation  
  
 Fonctions membres spéciales qui exigent un appel automatique par le compilateur, tel qu’un constructeur de copie ou un opérateur d’assignation de copie ne sont pas pris en charge dans une classe value.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3194.  
  
```  
// C3194.cpp  
// compile with: /clr /c  
value struct MyStruct {  
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194  
};  
  
ref struct MyStruct2 {  
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK  
};  
```

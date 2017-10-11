---
title: Erreur du compilateur C3816 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3816
dev_langs:
- C++
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 866a12639507488d8b9c34ab13ea72cf2239b5fb
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3816"></a>Erreur du compilateur C3816
'déclaration' a été précédemment déclarée ou définie avec un autre gérés ou WinRTmodifier  
  
 Une déclaration anticipée et une déclaration réelle nécessitent qu'il n'y ait aucun conflit ni incohérence dans la déclaration des attributs.  
  
 L'exemple suivant génère l'erreur C3816 et montre comment la corriger :  
  
```  
// C3816a.cpp  
// compile with: /clr /c  
class C1;  
// try the following line instead  
// ref class C1;  
  
ref class C1{  // C3816, forward declaration does not use ref  
};  
```

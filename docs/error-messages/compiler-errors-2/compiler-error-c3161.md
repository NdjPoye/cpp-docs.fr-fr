---
title: Erreur du compilateur C3161 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0cdbbd9364435ebcfad114331b6ba7289cb8010
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3161"></a>Erreur du compilateur C3161
'interface' : classe d’imbrication, le struct, union ou interface dans une interface non conforme ; imbrication d’une interface dans une classe, struct ou une union est non conforme  
  
 Un [__interface](../../cpp/interface.md) ne peut apparaître que dans une portée globale ou au sein d’un espace de noms. Une classe, struct ou union ne peut pas apparaître dans une interface.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3161.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```
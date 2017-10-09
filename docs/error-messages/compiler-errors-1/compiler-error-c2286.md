---
title: Erreur du compilateur C2286 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e1fca7ee629c35c083f6852a914e2ab62b4d5590
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2286"></a>Erreur du compilateur C2286
pointeurs vers des membres de la représentation sous forme de 'identificateur' est déjà définie à 'héritage' - déclaration ignorée  
  
 Il existe deux représentations différentes de pointeurs vers membres pour la classe.  
  
 Pour plus d’informations, consultez [mots clés d’héritage](../../cpp/inheritance-keywords.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2286 :  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```

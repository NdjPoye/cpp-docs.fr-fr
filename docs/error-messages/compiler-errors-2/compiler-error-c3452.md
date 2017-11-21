---
title: Erreur du compilateur C3452 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3452
dev_langs: C++
helpviewer_keywords: C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0ff18842af11d82d28819b01cb7798a4ae49eff1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3452"></a>Erreur du compilateur C3452
le membre argument de la liste n'est pas une constante  
  
 Un argument a été passé à un attribut qui attendait une constante, valeur qui peut être évaluée au moment de la compilation.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3452.  
  
```  
// C3452.cpp  
// compile with: /c  
int i;  
[module( name="mod", type=dll, custom={i} ) ];   // C3452  
// try the following line instead  
// [module( name="mod", type=dll, custom={"a"} ) ];  
```
---
title: Erreur du compilateur C3163 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 95fb254036d2883b6efe6b81bda54864d533c2a8
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3163"></a>Erreur du compilateur C3163
'construct' : attributs non cohérents avec la déclaration précédente  
  
 L’ou les attributs qui sont appliqué à une définition en conflit avec l’ou les attributs qui sont appliqué à une déclaration.  
  
 Une résolution C3163 consiste à éliminer les attributs de la déclaration anticipée. Tous les attributs d’une déclaration anticipée doivent être inférieure aux attributs de la définition ou, au maximum, égal aux uns aux autres.  
  
 Des causes possibles de l’erreur C3163 implique le langage Microsoft source code annotation (SAL). Les macros SAL ne développez pas sauf si vous compilez votre projet à l’aide de la **/ analyze** indicateur. Un programme qui se compile correctement sans /ANALYZE peut lever l’exception C3163 si vous tentez de le recompiler avec l’option /Analyze. Pour plus d’informations sur SAL, consultez [Annotations SAL](../../c-runtime-library/sal-annotations.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3163.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Annotations SAL](../../c-runtime-library/sal-annotations.md)

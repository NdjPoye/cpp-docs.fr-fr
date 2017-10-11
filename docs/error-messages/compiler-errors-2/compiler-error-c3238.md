---
title: Erreur du compilateur C3238 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3238
dev_langs:
- C++
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 51af2859cec319678f6b13caf7231a8f62a6177c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3238"></a>Erreur du compilateur C3238
'type' : un type portant ce nom a déjà été transféré à l’assembly 'assembly'  
  
 Un type a été défini dans une application cliente qui est aussi définie, via la syntaxe de transfert de type, dans un assembly référencé. Les deux types ne peuvent pas être définis dans l’étendue de l’application.  
  
 Consultez [transfert de Type (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un assembly qui contient un type qui a été transféré à partir d’un autre assembly.  
  
```  
// C3238.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un assembly qui contenait la définition du type, mais qui ne contient maintenant que la syntaxe de transfert de type.  
  
```  
// C3238_b.cpp  
// compile with: /clr /LD  
#using "C3238.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3238 :  
  
```  
// C3238_c.cpp  
// compile with: /clr /c  
// C3238 expected  
// Delete the following line to resolve.  
#using "C3238_b.dll"  
public ref class R {};  
```

---
title: Erreur du compilateur C3381 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3381
dev_langs:
- C++
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6b1a56658874eb5a62db7d272b40612e34bfc94a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3381"></a>Erreur du compilateur C3381
'assembly' : les spécificateurs d’accès assembly ne sont disponibles dans le code compilé avec l’option /clr  
  
 Les types natifs peuvent être visibles à l’extérieur de l’assembly, mais vous pouvez spécifier uniquement l’accès à l’assembly pour les types natifs dans un **/CLR** compilation.  
  
 Pour plus d’informations, consultez [visibilité de Type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) et [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3381.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```

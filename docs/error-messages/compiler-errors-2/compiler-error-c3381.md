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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af632ae602cacb5204f1fac1088bef8a6cd20168
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
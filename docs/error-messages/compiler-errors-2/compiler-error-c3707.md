---
title: Erreur du compilateur C3707 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3c61c23c093106267b4854109a8cfeb699bda78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3707"></a>Erreur du compilateur C3707
'fonction' : la méthode dispinterface doit avoir un dispid  
  
 Si vous utilisez un `dispinterface` (méthode), vous devez lui assigner un `dispid`. Pour corriger cette erreur, vous devez affecter un `dispid` à la `dispinterface` méthode, par exemple, en supprimant commentaires le `id` attribut sur la méthode dans l’exemple ci-dessous. Pour plus d’informations, consultez les attributs [dispinterface](../../windows/dispinterface.md) et [id](../../windows/id.md).  
  
 L’exemple suivant génère l’erreur C3707 :  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```
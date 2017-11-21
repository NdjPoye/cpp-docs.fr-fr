---
title: Erreur du compilateur C3763 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3763
dev_langs: C++
helpviewer_keywords: C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 51810524b36a714404ce45a51186bc635dacebd3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3763"></a>Erreur du compilateur C3763
'type' : 'retval' et 'out' ne peut apparaître que sur un type de pointeur de données  
  
 Le [hors](../../windows/out-cpp.md) ou [retval](../../windows/retval.md) attributs peuvent apparaître uniquement sur les paramètres de type pointeur. Supprimez l’attribut ou modifier le paramètre de type pointeur.  
  
 L’exemple suivant génère l’erreur C3763 :  
  
```  
// C3763.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atlcom.h>  
  
[ module(name=test) ];  
  
[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IF84 : IDispatch  
{  
   [id(0x00000002)]HRESULT m2([out]unsigned char);  
};  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]  
class CF84 : public IF84  
{   // C3763  
public:  
   HRESULT __stdcall m2(unsigned char i)  
   {  
      return S_OK;  
   }  
};  
  
int main()  
{  
}  
```
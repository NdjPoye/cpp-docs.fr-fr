---
title: "Lock::operator ! = | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
dev_langs: C++
helpviewer_keywords: lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 090d461a8f11d47d25119f5949f9f570093244fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="lockoperator"></a>lock::operator!=
Opérateur d’inégalité.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class T> bool operator!=(  
   T t  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `t`  
 Objet à comparer en termes d’inégalité.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `true` si `t` diffère objet du verrou, `false` dans le cas contraire.  
  
## <a name="example"></a>Exemple  
  
```  
// msl_lock_op_ineq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   Object^ o2 = gcnew Object;  
   lock l1(o1);  
   if (l1 != o2) {  
      Console::WriteLine("Inequal!");  
   }  
}  
```  
  
```Output  
Inequal!  
```  
  
## <a name="requirements"></a>Spécifications  
 **Fichier d’en-tête** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Voir aussi  
 [Lock, membres](../dotnet/lock-members.md)   
 [lock::operator==](../dotnet/lock-operator-equality.md)
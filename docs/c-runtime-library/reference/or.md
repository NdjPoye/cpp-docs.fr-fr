---
title: or | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- std::or
- std.or
- Or
dev_langs:
- C++
helpviewer_keywords:
- or function
ms.assetid: 6523b3ac-0a18-44ec-9e9a-b9bab8525ead
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 14c41f89fe5897479811aefd1ca8ce56bc626710
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="or"></a>or
Alternative à l’opérateur &#124;&#124;.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
#define or ||  
  
```  
  
## <a name="remarks"></a>Notes  
 La macro génère l’opérateur &#124;&#124;.  
  
## <a name="example"></a>Exemple  
  
```  
// iso646_or.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   bool a = true, b = false, result;  
  
   boolalpha(cout);  
  
   result= a || b;  
   cout << result << endl;  
  
   result= a or b;  
   cout << result << endl;  
}  
```  
  
```Output  
true  
true  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<iso646.h>
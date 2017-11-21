---
title: __stosq | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __stosq
dev_langs: C++
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6195632e6f0c395b225325ec7546a254b90cbf3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="stosq"></a>__stosq
**Section spécifique à Microsoft**  
  
 Génère une instruction de chaîne magasin (`rep stosq`).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __stosb(   
   unsigned __int64* Dest,   
   unsigned __int64 Data,   
   size_t Count   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `Dest`  
 La destination de l’opération.  
  
 [in] `Data`  
 Les données à stocker.  
  
 [in] `Count`  
 La longueur du bloc de mots quadruples à écrire.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__stosq`|AMD64|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
## <a name="remarks"></a>Remarques  
 Le résultat est que le mot quadruple `Data` est écrit dans un bloc de `Count` mots quadruples dans le `Dest` chaîne.  
  
 Cette routine est disponible uniquement en tant qu'intrinsèque.  
  
## <a name="example"></a>Exemple  
  
```  
// stosq.c  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosq)  
  
int main()  
{  
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;  
   unsigned __int64 a[10];  
   memset(a, 0, sizeof(a));  
   __stosq(a+1, val, 2);  
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);   
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
0 ffffffffffff ffffffffffff 0  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [compilateur, fonctions intrinsèques](../intrinsics/compiler-intrinsics.md)
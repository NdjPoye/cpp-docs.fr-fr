---
title: __writedr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __writedr
dev_langs: C++
helpviewer_keywords: __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e5a87f7339481378c3a7fb6af7201dd13a3ede59
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="writedr"></a>__writedr
Écrit la valeur spécifiée dans le Registre de débogage spécifiés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __writedr(unsigned DebugRegister, unsigned DebugValue);  
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `DebugRegister`  
 Inscription d’un nombre compris entre 0 et 7 identifiant le débogage.  
  
 [in] `DebugValue`  
 Inscription d’une valeur à écrire dans le débogage.  
  
## <a name="remarks"></a>Remarques  
 Ces fonctions intrinsèques sont disponibles uniquement en mode noyau, et les routines sont disponibles seulement comme fonctions intrinsèques.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__writedr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [__readdr](../intrinsics/readdr.md)
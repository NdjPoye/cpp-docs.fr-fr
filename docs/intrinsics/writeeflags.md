---
title: __writeeflags | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __writeeflags
dev_langs: C++
helpviewer_keywords: __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1b87ffaacbbfee167c779f25ae83090b7b8e3397
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="writeeflags"></a>__writeeflags
Écrit la valeur spécifiée pour le programme d’inscription d’état et contrôle (EFLAGS).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `Value`|Valeur à écrire dans le Registre EFLAGS. Le `Value` paramètre est de 32 bits pour une plateforme 32 bits et 64 bits pour une plateforme 64 bits.|  
  
## <a name="remarks"></a>Remarques  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__writeeflags`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)
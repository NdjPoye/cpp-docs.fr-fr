---
title: "_interlockedbittestandset, fonctions intrinsèques | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _interlockedbittestandset_cpp
- _interlockedbittestandset_HLEAcquire
- _interlockedbittestandset64
- _interlockedbittestandset
- _interlockedbittestandset_rel
- _interlockedbittestandset64_HLEAcquire
- _interlockedbittestandset_HLERelease
- _interlockedbittestandset_acq
- _interlockedbittestandset_nf
- _interlockedbittestandset64_cpp
- _interlockedbittestandset64_HLERelease
dev_langs: C++
helpviewer_keywords:
- _interlockedbittestandset intrinsic
- _interlockedbittestandset64 intrinsic
- lock_bts instruction
ms.assetid: b1b7e334-53ea-48cf-ba60-5fa3ef51a1fc
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b3538ffb330bc4e90bbd3a25b80e48d5b44855f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="interlockedbittestandset-intrinsic-functions"></a>_interlockedbittestandset, fonctions intrinsèques
**Section spécifique à Microsoft**  
  
 Générer une instruction qui examine le bit `b` de l'adresse `a` et retourne sa valeur actuelle avant de lui affecter la valeur 1.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned char _interlockedbittestandset(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandset_acq(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandset_HLEAcquire(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandset_HLERelease(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandset_nf(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandset_rel(  
   long *a,  
   long b  
);  
unsigned char _interlockedbittestandset64(  
   __int64 *a,  
   __int64 b  
);  
unsigned char _interlockedbittestandset64_HLEAcquire(  
   __int64 *a,  
   __int64 b  
);  
unsigned char _interlockedbittestandset64_HLERelease(  
   __int64 *a,  
   __int64 b  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `a`  
 Pointeur vers la mémoire à examiner.  
  
 [in] `b`  
 Position du bit à tester.  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur du bit à la position `b` avant qu'il ne soit défini.  
  
## <a name="requirements"></a>Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|---------------|------------------|------------|  
|`_interlockedbittestandset`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_interlockedbittestandset_acq`, `_interlockedbittestandset_nf`, `_interlockedbittestandset_rel`|ARM|\<intrin.h >|  
|`_interlockedbittestandset_HLEAcquire`, `_interlockedbittestandset_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h >|  
|`_interlockedbittestandset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_interlockedbittestandset64_HLEAcquire`, `_interlockedbittestandset64_HLERelease`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h >|  
  
## <a name="remarks"></a>Notes  
 Sur les processeurs x86 et [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)], ces fonctions intrinsèques utilisent l'instruction `lock bts` pour lire le bit spécifié et lui affecter la valeur 1. L'opération est atomique.  
  
 Sur les processeurs ARM, utilisez les intrinsèques avec les suffixes `_acq` et `_rel` pour les sémantiques Acquire et Release, par exemple au début et à la fin d'une section critique. Les fonctions intrinsèques ARM avec un suffixe `_nf` (pour « no fence », « pas de délimitation ») n'agissent pas comme une barrière mémoire.  
  
 Sur les processeurs Intel qui prennent en charge les instructions HLE (Hardware Lock Elision), les intrinsèques ayant les suffixes `_HLEAcquire` et `_HLERelease` incluent une indication pour le processeur. Celle-ci permet d'accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel. Si ces intrinsèques sont appelés pour des processeurs qui ne prennent pas en charge les instructions HLE, l'indication est ignorée.  
  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)
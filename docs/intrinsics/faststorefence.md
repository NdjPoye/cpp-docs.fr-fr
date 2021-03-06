---
title: __faststorefence | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f8c4a343126a14e1aea931b1e154714af280904
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="faststorefence"></a>__faststorefence
**Section spécifique à Microsoft**  
  
 Garantit que chaque référence mémoire précédente, y compris les références mémoire de charge et de stockage, est globalement visible avant toute référence mémoire suivante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __faststorefence();  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__faststorefence`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
## <a name="remarks"></a>Notes  
 Génère une séquence d'instructions de cloisonnement de mémoire complète qui garantit que les opérations de chargement et de stockage émises avant cet intrinsèque sont globalement visibles avant la poursuite de l'exécution. L'effet est comparable à l'intrinsèque `_mm_mfence` sur toutes les plateformes x64, mais plus rapide que ce dernier.  
  
 Sur la plateforme AMD64, cette routine génère une instruction qui est une délimitation de stockage plus rapide que l'instruction `sfence`. Pour le code à durée critique, utilisez cet intrinsèque à la place de `_mm_sfence` uniquement sur les plateformes AMD64. Sur les plateformes Intel x64, l'instruction `_mm_sfence` est plus rapide.  
  
 Cette routine est disponible uniquement en tant qu'intrinsèque.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [compilateur, fonctions intrinsèques](../intrinsics/compiler-intrinsics.md)
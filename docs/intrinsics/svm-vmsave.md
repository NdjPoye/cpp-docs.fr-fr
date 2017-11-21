---
title: __svm_vmsave | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_vmsave
dev_langs: C++
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 49f0f2bc2446c45c394daa9a4ec1e8c0a6278c83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="svmvmsave"></a>__svm_vmsave
**Section spécifique à Microsoft**  
  
 Stocke un sous-ensemble de l’état du processeur dans le bloc de contrôle d’ordinateur virtuel spécifié (VMCB).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __svm_vmsave(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|L’adresse physique de la VMCB.|  
  
## <a name="remarks"></a>Remarques  
 Le `__svm_vmsave` fonction est équivalente à la `VMSAVE` instruction machine. Cette fonction prend en charge l’interaction du moniteur de machines virtuelles d’un hôte avec un système d’exploitation invité et ses applications. Pour plus d’informations, recherchez le document, « de Volume manuelle AMD64 Architecture programmeur 2 : programmation du système, « numéro 24593, révision 3.11 ou une version ultérieure, à la [AMD Corporation](http://go.microsoft.com/fwlink/?LinkId=23746) site.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__svm_vmsave`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmrun](../intrinsics/svm-vmrun.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)
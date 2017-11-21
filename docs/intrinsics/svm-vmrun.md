---
title: __svm_vmrun | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_vmrun
dev_langs: C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 04467cc1d6d13a5c7c983aae48d2208622a75683
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="svmvmrun"></a>__svm_vmrun
**Section spécifique à Microsoft**  
  
 Démarre l’exécution du code d’invité d’ordinateur virtuel qui correspond au bloc de contrôle de machine virtuelle spécifiée (VMCB).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|L’adresse physique de la VMCB.|  
  
## <a name="remarks"></a>Remarques  
 Le `__svm_vmrun` fonction utilise un minimum d’informations dans le VMCB pour commencer l’exécution du code d’invité d’ordinateur virtuel. Utilisez le [__svm_vmsave](../intrinsics/svm-vmsave.md) ou [__svm_vmload](../intrinsics/svm-vmload.md) fonctionner si vous avez besoin de plus d’informations pour gérer une interruption complexe ou à un autre invité.  
  
 Le `__svm_vmrun` fonction est équivalente à la `VMRUN` instruction machine. Cette fonction prend en charge l’interaction du moniteur de machines virtuelles d’un hôte avec un système d’exploitation invité et ses applications. Pour plus d’informations, recherchez le document, « de Volume manuelle AMD64 Architecture programmeur 2 : programmation du système, « numéro 24593, révision 3.11 ou une version ultérieure, à la [corporation d’AMD](http://go.microsoft.com/fwlink/?LinkId=23746) site.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__svm_vmrun`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)
---
title: __vmx_vmwrite | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_vmwrite
dev_langs: C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c9ebd2602fe38a0ec1b51389b1a8a90625dd75e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Section spécifique à Microsoft**  
  
 Écrit la valeur spécifiée dans le champ spécifié dans la structure de contrôle de machine virtuelle actuelle (VMCS).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `Field`|Le champ VMCS à écrire.|  
|[in] `FieldValue`|Valeur à écrire dans le champ VMCS.|  
  
## <a name="return-value"></a>Valeur de retour  
 0  
 L’opération a réussi.  
  
 1  
 L’opération a échoué avec l’état étendu disponible dans le `VM-instruction error field` de la VMCS actuelle.  
  
 2  
 L’opération a échoué sans état disponible.  
  
## <a name="remarks"></a>Remarques  
 Le `__vmx_vmwrite` fonction est équivalente à la `VMWRITE` instruction machine. La valeur de le `Field` paramètre est un index de champ codée qui est décrite dans la documentation Intel. Pour plus d’informations, recherchez le document, « Intel virtualisation technique spécification pour l’Architecture IA-32 Intel, » document numéro est C97063-002, sur le [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) de site, puis consultez l’annexe C document.  
  
## <a name="requirements"></a>Spécifications  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)
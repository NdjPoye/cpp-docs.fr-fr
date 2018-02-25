---
title: __vmx_vmread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_vmread
dev_langs:
- C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 351ef951a57a4f100861dbd12b8a77d11fc41df8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="vmxvmread"></a>__vmx_vmread
**Section spécifique à Microsoft**  
  
 Lit un champ spécifié à partir de la structure de contrôle de machine virtuelle actuelle (VMCS) et le place dans l’emplacement spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `Field`|Le champ VMCS à lire.|  
|[in] `FieldValue`|Un pointeur vers l’emplacement pour stocker la valeur de lecture à partir du champ VMCS spécifié par le `Field` paramètre.|  
  
## <a name="return-value"></a>Valeur de retour  
  
|Value|Signification|  
|-----------|-------------|  
|0|L’opération a réussi.|  
|1|L’opération a échoué avec l’état étendu disponible dans le `VM-instruction error field` de la VMCS actuelle.|  
|2|L’opération a échoué sans état disponible.|  
  
## <a name="remarks"></a>Notes  
 Le `__vmx_vmread` fonction est équivalente à la `VMREAD` instruction machine. La valeur de le `Field` paramètre est un index de champ codée qui est décrite dans la documentation Intel. Pour plus d’informations, recherchez le document, « Intel virtualisation technique spécification pour l’Architecture IA-32 Intel, » document numéro est C97063-002, sur le [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) de site, puis consultez l’annexe C de ce document .  
  
## <a name="requirements"></a>Configuration requise  
  
|Intrinsèque|Architecture|  
|---------------|------------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d’en-tête** \<intrin.h >  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Intrinsèques du compilateur](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
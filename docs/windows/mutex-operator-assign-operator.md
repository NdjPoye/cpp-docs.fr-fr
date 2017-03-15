---
title: "Mutex::operator=, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Mutex::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= (opérateur)"
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mutex::operator=, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Affecte (se déplace) le Mutex spécifié de l’objet à l’objet Mutex actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `h`  
 Une référence rvalue à un objet Mutex.  
  
## <a name="return-value"></a>Valeur de retour  
 Une référence à l’objet Mutex actuel.  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez la **sémantique de déplacement** section [déclarateur de référence Rvalue : & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Voir aussi
 [Mutex (classe)](../windows/mutex-class1.md)
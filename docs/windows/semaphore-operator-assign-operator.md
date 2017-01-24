---
title: "Semaphore::operator=, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= (opérateur)"
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Semaphore::operator=, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déplace le handle spécifié à partir d’un objet sémaphore à l’objet de sémaphore actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Semaphore& operator=(  
   _Inout_ Semaphore&& h  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `h`  
 Référence rvalue à un objet de sémaphore.  
  
## <a name="return-value"></a>Valeur de retour  
 Une référence à l’objet de sémaphore actuel.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>Voir aussi
 [Semaphore (classe)](../windows/semaphore-class.md)
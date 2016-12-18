---
title: "ClassFactory::LockServer, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory::LockServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockServer (méthode)"
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ClassFactory::LockServer, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incrémente ou décrémente le nombre de sous-jacent objets suivis par l’objet ClassFactory actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fLock`  
 `true` pour incrémenter le nombre d’objets suivis. `false` Pour décrémenter le nombre d’objets suivis.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, E_FAIL.  
  
## <a name="remarks"></a>Notes  
 ClassFactory effectue le suivi des objets dans une instance sous-jacente de la [Module](../windows/module-class.md) classe.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ClassFactory (classe)](../windows/classfactory-class.md)
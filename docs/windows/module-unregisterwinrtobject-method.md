---
title: "Module::UnregisterWinRTObject, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterWinRTObject (méthode)"
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::UnregisterWinRTObject, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Annule l’inscription d’un ou plusieurs [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] objets afin que les autres applications ne peuvent pas se connecter à leur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `cookie`  
 Pointeur vers une valeur qui identifie l’objet de classe dont l’inscription doit être révoqué.  
  
## <a name="return-value"></a>Valeur de retour  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)
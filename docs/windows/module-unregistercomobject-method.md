---
title: "Module::UnregisterCOMObject, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::UnregisterCOMObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterCOMObject (méthode)"
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::UnregisterCOMObject, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Annule l’inscription d’un ou plusieurs objets COM, ce qui empêche d’autres applications de se connecter à leur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
#### <a name="parameters"></a>Paramètres  
 `serverName`  
 (Non utilisé)  
  
 `cookies`  
 Tableau de pointeurs vers les valeurs qui identifient les objets de classe doit être annulée. Le tableau a été créé par le [RegisterCOMObject](../windows/module-registercomobject-method.md) (méthode).  
  
 `count`  
 Le nombre de classes pour annuler l’inscription.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si cette opération est réussie ; Sinon, une erreur HRESULT qui indique la raison pour laquelle l’opération a échoué.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)
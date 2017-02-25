---
title: "Module::RegisterWinRTObject, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterWinRTObject (méthode)"
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Module::RegisterWinRTObject, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Registres, un ou plusieurs [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] autres applications peuvent se connecter à ces objets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `serverName`  
 Nom qui spécifie un sous-ensemble des objets affectés par cette opération.  
  
 `activatableClassIds`  
 Tableau de CLSID activables à inscrire.  
  
 `cookie`  
 Une valeur qui identifie les objets de classe qui ont été enregistrés. Cette valeur est utilisée ultérieurement pour révoquer l’inscription.  
  
 `count`  
 Nombre d’objets à inscrire.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, une erreur HRESULT tels que CO_E_OBJISREG qui indique la raison pour laquelle l’opération a échoué.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)
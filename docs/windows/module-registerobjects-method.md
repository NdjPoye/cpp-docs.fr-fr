---
title: "Module::RegisterObjects, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterObjects (méthode)"
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Module::RegisterObjects, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inscrit COM ou [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] autres applications peuvent se connecter à ces objets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `module`  
 Un tableau de COM ou [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] objets.  
  
 `serverName`  
 Nom du serveur qui a créé les objets.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; dans le cas contraire, un HRESULT qui indique la raison pour laquelle l’opération a échoué.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
## <a name="see-also"></a>Voir aussi
[Module (classe)](../windows/module-class.md)
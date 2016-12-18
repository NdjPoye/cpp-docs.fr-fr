---
title: "Module::GetClassObject, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::GetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetClassObject (méthode)"
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::GetClassObject, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Extrait un cache des fabriques de classes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `clsid`  
 ID de classe.  
  
 `riid`  
 ID d’interface que vous demandez.  
  
 `ppv`  
 Pointeur vers l’objet retourné.  
  
 `serverName`  
 Le nom du serveur qui est spécifié dans le `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, ou `ActivatableClass` macro ; ou `nullptr` pour obtenir le nom du serveur par défaut.  
  
## <a name="return-value"></a>Valeur de retour  
  
## <a name="remarks"></a>Notes  
 Utilisez cette méthode uniquement pour COM, et non pas le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]. Cette méthode expose uniquement les méthodes IClassFactory.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)
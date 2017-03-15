---
title: "Module::GetActivationFactory, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory (méthode)"
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Module::GetActivationFactory, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient une fabrique d’activation pour le module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pActivatibleClassId`  
 IID d’une classe d’exécution.  
  
 `ppIFactory`  
 IActivationFactory pour la classe d’exécution spécifié.  
  
 `serverName`  
 Le nom d’un sous-ensemble des fabriques de classes dans le module actuel. Spécifiez le nom du serveur utilisé dans le [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) (macro), ou spécifiez `nullptr` pour obtenir le nom du serveur par défaut.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; dans le cas contraire, le HRESULT retourné par GetActivationFactory.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
[Classe de module](../windows/module-class.md)
 [activatableclass, Macros](../windows/activatableclass-macros.md)
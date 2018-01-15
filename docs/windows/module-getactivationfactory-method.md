---
title: "Module::getactivationfactory, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::GetActivationFactory
dev_langs: C++
helpviewer_keywords: GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d5c5ca4d470f52ff9dde862cc99b10a3459cd0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory, méthode
Obtient la fabrique d’activation pour le module.  
  
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
 IActivationFactory pour la classe runtime spécifié.  
  
 `serverName`  
 Le nom d’un sous-ensemble des fabriques de classes du module en cours. Spécifiez le nom du serveur utilisé dans le [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) (macro), ou spécifiez `nullptr` pour obtenir le nom du serveur par défaut.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK en cas de réussite ; dans le cas contraire, le HRESULT retourné par GetActivationFactory.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
[Classe de module](../windows/module-class.md) [activatableclass, Macros](../windows/activatableclass-macros.md)
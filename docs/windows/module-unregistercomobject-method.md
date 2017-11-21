---
title: "Module::unregistercomobject, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs: C++
helpviewer_keywords: UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 43ea6ab8f3990316be7bce27c06b3aee0df8fbf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="moduleunregistercomobject-method"></a>Module::UnregisterCOMObject, méthode
Annule l’inscription d’un ou plusieurs objets COM, ce qui empêche d’autres applications de se connecter à ceux-ci.  
  
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
 S_OK si cette opération a réussi ; Sinon, une erreur HRESULT qui indique la raison pour laquelle l’opération a échoué.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module, classe](../windows/module-class.md)
---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 010979a0a72fc1d522a921b20df4579bc6efa159
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType, opérateur
Indique si un ComPtr gère la durée de vie des objets d’une interface.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Si une interface est associée à ce ComPtr, l’adresse de la [BoolStruct::Member](../windows/boolstruct-member-data-member.md) membre de données ; sinon, `nullptr`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtr (classe)](../windows/comptr-class.md)   
 [ComPtr::Get, méthode](../windows/comptr-get-method.md)
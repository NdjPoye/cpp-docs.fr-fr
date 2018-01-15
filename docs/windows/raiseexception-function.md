---
title: RaiseException (fonction) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::RaiseException
dev_langs: C++
helpviewer_keywords: RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 380e3792c5b2b9504bec841965e70bd47ec619d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="raiseexception-function"></a>RaiseException (fonction)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
inline void __declspec(noreturn)   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hr`  
 Le code d’exception de l’exception est levée ; Autrement dit, la valeur HRESULT d’échec d’une opération.  
  
 `dwExceptionFlags`  
 Un indicateur qui indique une exception non bloquantes (la valeur de l’indicateur est égal à zéro), ou une exception noncontinuable (la valeur de l’indicateur est différente de zéro). Par défaut, l’exception est qui empêchait celle-ci.  
  
## <a name="remarks"></a>Notes  
 Lève une exception dans le thread appelant.  
  
 Pour plus d’informations, consultez les fenêtres **RaiseException** (fonction).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** internal.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)
---
title: "Ftmbase::GetUnmarshalClass, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs: C++
helpviewer_keywords: GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 978379c64f22026f19dd76afa39af08402cebc65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass, méthode
Obtient le CLSID COM utilise pour rechercher la DLL qui contient le code pour le proxy correspondant. COM charge cette DLL pour créer une instance non initialisée du proxy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `riid`  
 Référence à l’identificateur de l’interface pour être marshalés.  
  
 `pv`  
 Pointeur vers l’interface pour être marshalés ; peut d’être NULL si l’appelant n’a pas un pointeur vers l’interface souhaitée.  
  
 `dwDestContext`  
 Contexte de destination où l’interface spécifiée doit être démarshalée.  
  
 Spécifiez une ou plusieurs valeurs d’énumération MSHCTX.  
  
 Unmarshaling peut se produire dans un autre cloisonnement du processus actuel (MSHCTX_INPROC) ou dans un autre processus sur le même ordinateur que le processus en cours (MSHCTX_LOCAL).  
  
 `pvDestContext`  
 Réservé à un usage ultérieur ; doit être NULL.  
  
 `mshlflags`  
 Lorsque cette opération se termine, pointeur vers le CLSID à utiliser pour créer un proxy dans le processus client.  
  
 `pCid`  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK en cas de réussite ; Sinon, S_FALSE.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** ftm.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)
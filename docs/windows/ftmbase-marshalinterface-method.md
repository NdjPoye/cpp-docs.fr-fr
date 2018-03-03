---
title: "Ftmbase::MarshalInterface, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9df1e5d7559b434c1af0f1feff3b73b8141a8865
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface, méthode
Écrit dans un flux les données requises pour initialiser l’objet proxy dans un processus client.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pStm`  
 Pointeur vers le flux à utiliser pendant le marshaling.  
  
 `riid`  
 Référence à l’identificateur de l’interface pour être marshalés. Cette interface doit être dérivée de l’interface IUnknown.  
  
 `pv`  
 Pointeur vers le pointeur d’interface pour être marshalés ; peut d’être NULL si l’appelant n’a pas un pointeur vers l’interface souhaitée.  
  
 `dwDestContext`  
 Contexte de destination où l’interface spécifiée doit être démarshalée.  
  
 Spécifiez une ou plusieurs valeurs d’énumération MSHCTX.  
  
 Unmarshaling peut se produire dans un autre cloisonnement du processus actuel (MSHCTX_INPROC) ou dans un autre processus sur le même ordinateur que le processus en cours (MSHCTX_LOCAL).  
  
 `pvDestContext`  
 Réservé pour une future utilisation ; doit être nul.  
  
 `mshlflags`  
 Spécifie si les données doivent être marshalées doit être transmis au processus client, le cas par défaut, ou écrites sur une table globale, où il peut être récupéré par plusieurs clients.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK  
 Le pointeur d’interface a été correctement marshalé.  
  
 E_NOINTERFACE  
 L’interface spécifiée n’est pas pris en charge.  
  
 STG_E_MEDIUMFULL  
 Le flux de données est plein.  
  
 E_FAIL  
 L'opération a échoué.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** ftm.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)
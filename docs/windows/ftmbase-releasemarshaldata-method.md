---
title: "Ftmbase::releasemarshaldata, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
dev_langs: C++
helpviewer_keywords: ReleaseMarshalData method
ms.assetid: a94f9940-183a-4fde-8504-d223f346a0a9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f10c05aef4700c3f3c9b18c2d728452ee816ee05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasereleasemarshaldata-method"></a>FtmBase::ReleaseMarshalData, méthode
Détruit un paquet de données marshalé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHODIMP ReleaseMarshalData(  
   __in IStream *pStm  
) override;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pStm`  
 Pointeur vers un flux qui contient le paquet de données d’être détruites.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** ftm.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)
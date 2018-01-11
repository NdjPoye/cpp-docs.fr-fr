---
title: IConvertTypeImpl::CanConvert | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
dev_langs: C++
helpviewer_keywords: CanConvert method
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 618f09e2bd0aab553741495fd42f8b2dbca18185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="iconverttypeimplcanconvert"></a>IConvertTypeImpl::CanConvert
Fournit des informations sur la disponibilité de conversions de type sur une commande ou sur un ensemble de lignes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD(CanConvert)(   
   DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags    
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="remarks"></a>Notes  
 Utilise la conversion de données OLE DB dans `MSADC.DLL`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IConvertTypeImpl, classe](../../data/oledb/iconverttypeimpl-class.md)
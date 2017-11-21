---
title: IRowsetUpdateImpl::SetData | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
dev_langs: C++
helpviewer_keywords: SetData method
ms.assetid: 7288a8d1-a7cf-4957-b832-0f3b18fd0da4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e098db995bad0d99e47d6108436a5324d2920e9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetupdateimplsetdata"></a>IRowsetUpdateImpl::SetData
Définit les valeurs de données dans une ou plusieurs colonnes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD ( SetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IRowsetChange::SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="remarks"></a>Remarques  
 Cette méthode remplace la [IRowsetChangeImpl::SetData](../../data/oledb/irowsetchangeimpl-setdata.md) méthode inclut, mais la mise en cache des données d’origine pour permettre le traitement immédiat ou différé de l’opération.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)
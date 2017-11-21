---
title: CCommand::SetParameterInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
dev_langs: C++
helpviewer_keywords: SetParameterInfo method
ms.assetid: a70e92f4-1e73-41d7-a5b7-c6ebb45a6477
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 34a1bb0349b99bbc23d5ec588c9f7b7f50e1f19d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ccommandsetparameterinfo"></a>CCommand::SetParameterInfo
Spécifie le type natif de chaque paramètre de commande.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT CCommandBase::SetParameterInfo(  
   DB_UPARAMS ulParams,  
   const DBORDINAL* pOrdinals,  
   const DBPARAMBINDINFO* pParamInfo   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [ICommandWithParameters::SetParameterInfo](https://msdn.microsoft.com/en-us/library/ms725393.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)
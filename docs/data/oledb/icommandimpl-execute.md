---
title: ICommandImpl::Execute | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs:
- C++
helpviewer_keywords:
- Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d4d24bbb7f7aad94210672ce9bbf0cc0c7d5414
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
Exécute la commande.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="remarks"></a>Notes  
 L’interface sortante demandé sera une interface acquise à partir de l’objet d’ensemble de lignes créés par cette fonction.  
  
 **Exécutez** appelle [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Substituer l’implémentation par défaut pour créer plus d’un ensemble de lignes ou pour fournir vos propres conditions de création de différents ensembles de lignes.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [ICommandImpl (classe)](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)
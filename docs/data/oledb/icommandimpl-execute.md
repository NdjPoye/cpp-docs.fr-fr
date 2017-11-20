---
title: ICommandImpl::Execute | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs: C++
helpviewer_keywords: Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 84ff5892573f2bb1fc80f7eb88e21948df561fc0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
Exécute la commande.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="remarks"></a>Remarques  
 L’interface sortante demandé sera une interface acquise à partir de l’objet d’ensemble de lignes créés par cette fonction.  
  
 **Exécutez** appelle [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Substituer l’implémentation par défaut pour créer plus d’un ensemble de lignes ou pour fournir vos propres conditions de création de différents ensembles de lignes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [ICommandImpl (classe)](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)
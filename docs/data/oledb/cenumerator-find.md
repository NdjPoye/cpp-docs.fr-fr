---
title: CEnumerator::Find | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs: C++
helpviewer_keywords: Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8accf88c6391d782aacbc691f75433b7c6398e56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
Recherche d’un nom spécifié parmi les fournisseurs disponibles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool Find(   
   TCHAR* szSearchName    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 *szSearchName*  
 [in] Le nom à rechercher.  
  
## <a name="return-value"></a>Valeur de retour  
 **true** si le nom a été trouvé. dans le cas contraire, **false**.  
  
## <a name="remarks"></a>Remarques  
 Ce nom correspond à la **SOURCES_NAME** membre de la [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) interface.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CEnumerator, classe](../../data/oledb/cenumerator-class.md)
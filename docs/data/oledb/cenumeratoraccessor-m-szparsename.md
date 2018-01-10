---
title: CEnumeratorAccessor::m_szParseName | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
dev_langs: C++
helpviewer_keywords: m_szParseName
ms.assetid: 32e826b6-0890-4db4-aa92-fc1ea3f528b2
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18959d3743cf10c262aee583a0527cc5c067a806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cenumeratoraccessormszparsename"></a>CEnumeratorAccessor::m_szParseName
Chaîne à passer au [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) pour obtenir un moniker pour la source de données ou de l’énumérateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
WCHAR m_szParseName[129];  
  
```  
  
## <a name="remarks"></a>Notes  
 Consultez [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx) dans les *de référence du programmeur OLE DB* pour plus d’informations.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CEnumeratorAccessor, classe](../../data/oledb/cenumeratoraccessor-class.md)
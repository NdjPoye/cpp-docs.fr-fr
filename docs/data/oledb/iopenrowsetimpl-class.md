---
title: Iopenrowsetimpl, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IOpenRowsetImpl
dev_langs: C++
helpviewer_keywords: IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89a37274fd4040b24c36983fea968674acf4fcab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl, classe
Fournit l’implémentation pour la `IOpenRowset` interface.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>Paramètres  
 `SessionClass`  
 Votre classe, dérivée de `IOpenRowsetImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Crée un objet d’ensemble de lignes. Pas appelé directement par l’utilisateur.|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|Ouvre et retourne un ensemble de lignes qui inclut toutes les lignes à partir d’une seule table de base ou un index. (Pas dans ATLDB. H)|  
  
## <a name="remarks"></a>Remarques  
 Le [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) interface est obligatoire pour un objet de session. Il s’ouvre et retourne un ensemble de lignes qui inclut toutes les lignes à partir d’une seule table de base ou un index.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
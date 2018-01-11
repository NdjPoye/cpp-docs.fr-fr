---
title: CSession, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs: C++
helpviewer_keywords: CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d8b6bb75d12b4ab96c3a44c74f4487eb8a70efc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="csession-class"></a>CSession, classe
Représente une session d’accès de base de données unique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSession  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Abandon](../../data/oledb/csession-abort.md)|Annule (met fin à) la transaction.|  
|[Fermer](../../data/oledb/csession-close.md)|Ferme la session.|  
|[Validation](../../data/oledb/csession-commit.md)|Valide la transaction.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Retourne des informations relatives à une transaction.|  
|[Ouvrir](../../data/oledb/csession-open.md)|Ouvre une nouvelle session de l’objet de source de données.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Commence une nouvelle transaction pour cette session.|  
  
## <a name="remarks"></a>Notes  
 Une ou plusieurs sessions peuvent être associée à chaque connexion du fournisseur (source de données), qui est représentée par un [CDataSource](../../data/oledb/cdatasource-class.md) objet. Pour créer un nouveau `CSession` pour un `CDataSource`, appelez [CSession::Open](../../data/oledb/csession-open.md). Pour commencer une transaction de base de données, `CSession` fournit le `StartTransaction` (méthode). Une fois qu’une transaction est démarrée, vous pouvez valider à l’aide de la **validation** (méthode), ou sur Annuler à l’aide de la **abandonner** (méthode).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CatDB](../../visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
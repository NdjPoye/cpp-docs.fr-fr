---
title: CDataSource, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs: C++
helpviewer_keywords: CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: feb829812bd4223ca7c348f3a2825ad3b11839a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasource-class"></a>CDataSource, classe
Correspond à un objet de source de données OLE DB, qui représente une connexion via un fournisseur de source de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDataSource  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Fermer](../../data/oledb/cdatasource-close.md)|Ferme la connexion.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|Récupère la chaîne d’initialisation de la source de données qui est actuellement ouverte.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|Obtient les valeurs de propriétés actuellement définies pour la source de données connectée.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|Obtient la valeur d’une propriété unique actuellement définie pour la source de données connectée.|  
|[Ouvrir](../../data/oledb/cdatasource-open.md)|Crée une connexion à un fournisseur (source de données) en utilisant un **CLSID**, **ProgID**, ou un `CEnumerator` moniker fourni par l’appelant.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|Ouvre une source de données à partir d'un fichier spécifié par le nom de fichier fourni par l'utilisateur.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|Ouvre la source de données spécifiée par une chaîne d’initialisation.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|Permet à l’utilisateur de sélectionner un fichier de liaison de données créée précédemment pour ouvrir la source de données correspondante.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|Ouvre un objet de source de données à l’aide de la boîte de dialogue liaison de données.|  
  
## <a name="remarks"></a>Remarques  
 Une ou plusieurs sessions de base de données peuvent être créées pour une seule connexion. Ces sessions sont représentées par `CSession`. Vous devez appeler [CDataSource::Open](../../data/oledb/cdatasource-open.md) pour ouvrir la connexion avant de créer une session avec `CSession::Open`.  
  
 Pour obtenir un exemple montrant comment utiliser `CDataSource`, consultez la [CatDB](../../visual-cpp-samples.md) exemple.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
---
title: CXMLAccessor (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
dev_langs: C++
helpviewer_keywords: CXMLAccessor class
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 96620f287522168cd7b6b78d43163e8c4bb64217
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor, classe
Permet d’accéder aux sources de données en tant que données de type chaîne, lorsque vous n’avez aucune connaissance du schéma de la banque données (structure sous-jacente).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|Récupère les informations de colonne.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|Récupère le contenu entier d’une table en lignes.|  
  
## <a name="remarks"></a>Notes  
 Toutefois, `CXMLAccessor` diffère `CDynamicStringAccessorW` dans la mesure où il convertit toutes les données accédées à partir du magasin de données au format XML (avec balises). Cela est particulièrement utile pour la sortie vers des pages Web prenant en charge XML. Les noms de balises XML correspondront aux noms de colonne du magasin de données aussi proche que possible.  
  
 Utilisez `CDynamicAccessor` méthodes pour obtenir des informations de colonne. Ces informations de colonne vous permet de créer un accesseur dynamique au moment de l’exécution.  
  
 Les informations de colonne sont stockées dans une mémoire tampon créée et gérée par cette classe. Obtenir des informations de colonne à l’aide [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) ou obtenir des données de la colonne en lignes à l’aide de [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md).  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête**: atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles de consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor (classe)](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor (classe)](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor (classe)](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA, classe](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW, classe](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)
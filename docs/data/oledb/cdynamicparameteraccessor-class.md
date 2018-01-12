---
title: CDynamicParameterAccessor, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs: C++
helpviewer_keywords: CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b0c2590866db418f1652ebd1a46c0465ccb99086
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor (classe)
Semblable à [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) mais obtient les informations sur les paramètres à définir en appelant l’interface [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) .  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDynamicParameterAccessor : public CDynamicAccessor  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|Constructeur.|  
|[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)|Récupère les données du paramètre en mémoire tampon.|  
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|Récupère le nombre de paramètres dans l’accesseur.|  
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|Détermine si le paramètre spécifié est un paramètre d’entrée ou de sortie.|  
|[GetParamLength](../../data/oledb/cdynamicparameteraccessor-getparamlength.md)|Récupère la longueur du paramètre spécifié stocké en mémoire tampon.|  
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|Récupère le nom d’un paramètre spécifique.|  
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|Récupère l’état du paramètre spécifié stocké en mémoire tampon.|  
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|Récupère les données de chaîne du paramètre spécifié stocké en mémoire tampon.|  
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|Récupère le type de données d’un paramètre spécifique.|  
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|Définit la mémoire tampon à l’aide des données de paramètre.|  
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|Définit la longueur du paramètre spécifié stocké en mémoire tampon.|  
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|Définit l’état du paramètre spécifié stocké en mémoire tampon.|  
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|Définit les données de chaîne du paramètre spécifié stocké en mémoire tampon.|  
  
## <a name="remarks"></a>Notes  
 Le fournisseur doit prendre en charge `ICommandWithParameters` pour permettre au consommateur d’utiliser cette classe.  
  
 Les informations sur les paramètres sont stockées dans une mémoire tampon créée et gérée par cette classe. Obtenez les données de paramètre à partir de la mémoire tampon via [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) et [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Pour accéder à un exemple montrant comment utiliser cette classe pour exécuter une procédure stockée SQL Server et obtenir les valeurs de paramètre de sortie, consultez l’article de la Base de connaissances Q058860 relatif à l’exécution d’une procédure stockée via CDynamicParameterAccessor. Les articles de la Base de connaissances sont disponibles dans la documentation Visual Studio de MSDN Library ou sur [http://support.microsoft.com/](http://support.microsoft.com).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête**: atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles de consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor (classe)](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor (classe)](../../data/oledb/cdynamicaccessor-class.md)   
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)
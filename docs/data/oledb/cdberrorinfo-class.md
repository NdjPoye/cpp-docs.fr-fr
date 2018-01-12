---
title: Cdberrorinfo, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
dev_langs: C++
helpviewer_keywords: CDBErrorInfo class
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed20f02b51afcd338b0a84f92def104c079869b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo, classe
Fournit la prise en charge pour le traitement d’erreur OLE DB à l’aide de OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) interface.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDBErrorInfo  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Retourne toutes les informations d’erreur contenues dans un enregistrement d’erreur.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Appels [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) pour renvoyer des informations de base sur l’erreur spécifiée.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Appels [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) pour retourner un pointeur à une interface sur un objet d’erreur personnalisé.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Appels [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) pour retourner une **IErrorInfo** pointeur d’interface pour l’enregistrement spécifié.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Appels [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) pour retourner les paramètres d’erreur.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Obtient les enregistrements d’erreur pour l’objet spécifié.|  
  
## <a name="remarks"></a>Notes  
 Cette interface retourne un ou plusieurs enregistrements d’erreur à l’utilisateur. Appelez [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) premier, pour obtenir le nombre d’enregistrements d’erreur. Puis à appeler une de l’accès aux fonctions, telles que [CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)pour extraire des informations d’erreur pour chaque enregistrement.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [DBViewer](../../visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
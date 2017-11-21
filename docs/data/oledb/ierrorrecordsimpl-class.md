---
title: IErrorRecordsImpl, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
dev_langs: C++
helpviewer_keywords: IErrorRecordsImpl class
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6bd2b342f2e7b29103b08c67fa973ed4a8c64869
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl, classe
Implémente le OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) interface, ajouter des enregistrements à et récupérer des enregistrements d’un membre de données ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) de type **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   class T,   
   class RecordClass = ATLERRORINFO  
>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Une classe dérivée de `IErrorRecordsImpl`.  
  
 `RecordClass`  
 Une classe qui représente un objet d’erreur OLE DB.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Obtient la chaîne de description d’erreur à partir d’un enregistrement d’erreur.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|Obtient le GUID de l’erreur à partir d’un enregistrement d’erreur.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Obtient l’ID de contexte d’aide à partir d’un enregistrement d’erreur.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Obtient le chemin d’accès complet du fichier d’aide à partir d’un enregistrement d’erreur.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Obtient le code source d’erreur à partir d’un enregistrement d’erreur.|  
  
### <a name="interface-methods"></a>Méthodes d’interface  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|Ajoute un enregistrement à l’objet d’erreur OLE DB.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Retourne des informations de base sur l’erreur, telles que le code de retour et le numéro d’erreur spécifique au fournisseur.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Retourne un pointeur vers une interface sur un objet d’erreur personnalisé.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Retourne un [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) pointeur d’interface sur l’enregistrement spécifié.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Retourne les paramètres de l’erreur.|  
|[GetRecordCount](../../mfc/reference/cdaorecordset-class.md#getrecordcount)|Retourne le nombre d’enregistrements dans l’objet d’enregistrement OLE DB.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|[m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|Tableau d’enregistrements d’erreur.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
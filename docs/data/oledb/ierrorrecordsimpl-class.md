---
title: "IErrorRecordsImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IErrorRecordsImpl"
  - "ATL.IErrorRecordsImpl"
  - "IErrorRecordsImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IErrorRecordsImpl (classe)"
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IErrorRecordsImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente l'interface OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx), en ajoutant des enregistrements et l'extraction des enregistrements d'un membre de données \([m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)\) de type **CAtlArray\<**`RecordClass`**\>**.  
  
## Syntaxe  
  
```  
template <  
   class T,   
   class RecordClass = ATLERRORINFO  
>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### Paramètres  
 `T`  
 Une classe dérivée de `IErrorRecordsImpl`.  
  
 `RecordClass`  
 Une classe qui représente un objet d'erreur OLE DB.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Obtient la chaîne de description d'erreur à partir d'un enregistrement d'erreur.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|Obtient l'erreur GUID d'un enregistrement d'erreur.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Obtient l'ID de contexte d'aide d'un enregistrement d'erreur.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Obtient le nom d'accès complet du fichier d'aide d'un enregistrement d'erreur.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Obtient le code source de l'erreur d'un enregistrement d'erreur.|  
  
### Méthodes d'interface  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|Ajoute un enregistrement à l'objet d'erreur OLE DB.|  
|[Obtenir les erreurs d'informations de base.](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Retourne des informations de base sur l'erreur, comme le code de retour et le numéro d'erreur spécifique au fournisseur.|  
|[Obtenir les erreurs d'objets personnalisées.](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Retourne un pointeur vers une interface sur un objet personnalisé d'erreur.|  
|[Obtenir les informations d'erreurs](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Retourne un pointeur d'interface de [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) sur l'enregistrement spécifié.|  
|[Obtenir les paramètres d'erreurs](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Retourne le paramètre d'erreur.|  
|[GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|Retourne le nombre d'enregistrements dans l'objet d'enregistrement OLE DB.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|Tableau d'enregistrements d'erreur.|  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
---
title: "CDBErrorInfo, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo"
  - "ATL::CDBErrorInfo"
  - "ATL.CDBErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBErrorInfo (classe)"
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit la prise en charge de l'erreur OLE DB de traitement à l'aide de l'interface OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx).  
  
## Syntaxe  
  
```  
class CDBErrorInfo  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Obtenir toutes les informations d'erreurs](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Retourne toutes les informations sur les erreurs contenues dans un enregistrement d'erreur.|  
|[Obtenir les erreurs d'informations de base.](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Appelle [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) pour retourner des informations de base sur l'erreur spécifiée.|  
|[Obtenir les erreurs d'objets personnalisées.](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Appels [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) pour retourner un pointeur vers une interface sur une erreur d'objet personnalisée.|  
|[Obtenir les informations d'erreurs](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Appelle [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) pour retourner un pointeur d'interface **IErrorInfo** vers un enregistrement spécifié.|  
|[Obtenir les paramètres d'erreurs](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Appelle [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) pour retourner les paramètres d'erreur.|  
|[Obtenir les enregistrements d'erreurs.](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Obtient les enregistrements d'erreurs pour l'objet spécifié.|  
  
## Notes  
 Cette interface retourne un ou plusieurs enregistrements d'erreur à l'utilisateur.  Appelez [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) d'abord, pour obtenir le nombre d'enregistrements d'erreur.  Appelez l'une des fonctions d'accès, telle que [CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), pour extraire les informations d'erreur pour chaque enregistrement.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
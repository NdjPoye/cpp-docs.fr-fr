---
title: "CDBException Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDBException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBException class"
  - "database exceptions [C++]"
  - "erreurs (C++), base de données"
  - "exceptions [C++], base de données"
  - "ODBC (classes) (C++), exceptions"
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une condition d'exception résultante des classes de base de données.  
  
## Syntaxe  
  
```  
  
class CDBException : public CException  
  
```  
  
## Membres  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDBException::m\_nRetCode](../Topic/CDBException::m_nRetCode.md)|Contient le code de retour ODBC, de type **RETCODE**.|  
|[CDBException::m\_strError](../Topic/CDBException::m_strError.md)|Contient une chaîne qui décrit l'erreur dans la terminologie alphanumériques.|  
|[CDBException::m\_strStateNativeOrigin](../Topic/CDBException::m_strStateNativeOrigin.md)|Contient une chaîne décrivant l'erreur en termes de codes d'erreur retournés par ODBC.|  
  
## Notes  
 La classe inclut deux données membres publiques que vous pouvez utiliser pour déterminer la cause de l'exception ou pour afficher un message décrivant l'exception.  Les objets d'`CDBException` sont construits et levée par les fonctions membres des classes de base de données.  
  
> [!NOTE]
>  Cette classe est l'une des classes de l'Open Database Connectivity MFC \(ODBC\).  Si vous utilisez plutôt les classes nouvelles DAO \(DAO\), utilisez [CDaoException](../../mfc/reference/cdaoexception-class.md) à la place.  Tous les noms de classes DAO ont « CDao » comme préfixe.  Pour plus d'informations, consultez l'article [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md).  
  
 Les exceptions sont des cas d'opération anormale impliquant des conditions à l'extérieur de le contrôle de programme, tel que la source de données ou les erreurs d'E\/S de réseau.  Les erreurs que vous pouvez vous attendre à ce que consultez dans le cours normal d'exécuter votre programme ne sont généralement pas considérées comme des exceptions.  
  
 Vous pouvez accéder à ces objets dans la portée d'une expression de **collecteur** .  Vous pouvez également générer des objets d' `CDBException` de votre propre code avec la fonction globale d' `AfxThrowDBException` .  
  
 Pour plus d'informations sur la gestion des exceptions en général ou sur les objets d' `CDBException` , consultez les articles [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md) et [exceptions : exceptions de base de données](../../mfc/exceptions-database-exceptions.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## Configuration requise  
 **Header:** afxdb.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [AfxThrowDBException](../Topic/AfxThrowDBException.md)   
 [CRecordset::Update](../Topic/CRecordset::Update.md)   
 [CRecordset::Delete](../Topic/CRecordset::Delete.md)   
 [CException Class](../../mfc/reference/cexception-class.md)
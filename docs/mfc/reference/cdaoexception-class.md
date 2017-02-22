---
title: "CDaoException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoException class"
  - "collections, erreurs DAO"
  - "DAO (Data Access Objects), exceptions"
  - "erreurs (C++), DAO"
  - "Errors collection, DAO"
  - "exceptions, in MFC DAO classes"
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une condition d'exception résultante des classes de base de données MFC basée sur des objets \(DAO\) d'accès aux données.  
  
## Syntaxe  
  
```  
class CDaoException : public CException  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoException::CDaoException](../Topic/CDaoException::CDaoException.md)|Construit un objet `CDaoException`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md)|Retourne le nombre d'erreurs dans la collection des erreurs du moteur de base de données.|  
|[CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md)|Les informations d'erreur de retour sur un objet particulier d'erreur dans la collection d'erreurs.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoException::m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md)|Contient le code d'erreur étendu pour toute erreur dans les classes DAO MFC.|  
|[CDaoException::m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)|Un pointeur vers un objet de [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) qui contient des informations sur un objet d'erreur DAO.|  
|[CDaoException::m\_scode](../Topic/CDaoException::m_scode.md)|La valeur de [SCODE](../Topic/CDaoException::m_scode.md) associée à l'erreur.|  
  
## Notes  
 La classe inclut les données membres publiques que vous pouvez utiliser pour déterminer la cause de l'exception.  Les objets d'`CDaoException` sont construits et levée par les fonctions membres des classes de bases de données DAO.  
  
> [!NOTE]
>  Les classes de bases de données DAO sont séparées des classes de base de données MFC basée sur \(Open Database Connectivity\).  Tous les noms de classes de bases de données DAO ont le préfixe « CDao ».  Vous pouvez encore accéder aux sources de données ODBC avec les classes DAO.  En général les classes DAO MFC basée sur sont plus qui gèrent les classes ODBC MFC basée sur ; les classes DAO peuvent accéder aux données, notamment via des pilotes ODBC, via leur propre moteur de base de données.  Les classes DAO prennent également en charge des opérations de langage de définition de données \(DDL\), telles que l'ajout de tables via des classes, sans devoir appeler DAO directement.  Pour plus d'informations sur les exceptions levées par les classes ODBC, consultez [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Vous pouvez accéder aux objets exception dans la portée d'une expression de [CATCH](../Topic/CATCH.md) .  Vous pouvez également générer des objets d' `CDaoException` de votre propre code avec la fonction globale d' [AfxThrowDaoException](../Topic/AfxThrowDaoException.md) .  
  
 Dans MFC, les erreurs DAO sont exprimées comme exceptions, de type `CDaoException`.  Lorsque vous interceptez une exception de ce type, vous pouvez utiliser les fonctions membres d' `CDaoException` pour récupérer des informations sur tous les objets d'erreur DAO contenus dans la collection des erreurs du moteur de base de données.  Chaque fois qu'une erreur se produit, un ou plusieurs objets d'erreur dans la collection d'erreurs.  \(Normalement la collection contient uniquement un objet d'erreur ; si vous utilisez une source de données ODBC, vous êtes pour obtenir des objets de plusieurs erreurs.\) Lorsqu'une autre opération DAO génère une erreur, la collection d'erreurs est désactivée, et le nouvel objet d'erreur est défini dans la collection d'erreurs.  Les opérations de DAO qui ne génèrent pas d'erreur n'ont aucun effet sur la collection d'erreurs.  
  
 Pour les codes d'erreur DAO, consultez le fichier DAOERR.H.  Pour des informations connexes, consultez la rubrique « erreurs récupérables d'accès aux données » dans l'aide de DAO.  
  
 Pour plus d'informations sur la gestion des exceptions en général ou sur les objets d' `CDaoException` , consultez les articles [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md) et [exceptions : exceptions de base de données](../../mfc/exceptions-database-exceptions.md).  Le deuxième article contient un exemple de code illustrant la gestion des exceptions dans DAO.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)
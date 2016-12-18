---
title: "CException Class | Microsoft Docs"
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
  - "CException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchiveException class, classe de base"
  - "CDaoException class, classe de base"
  - "CDBException class, classe de base"
  - "CException class"
  - "CFileException class, classe de base"
  - "CInternetException class, classe de base"
  - "CMemoryException class, classe de base"
  - "CNotSupportedException class, classe de base"
  - "COleDispatchException class, classe de base"
  - "COleException class, classe de base"
  - "CResourceException class, classe de base"
  - "CUserException class"
  - "exceptions, classes for"
  - "macros, gestion des exceptions"
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
caps.latest.revision: 22
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base pour toutes les exceptions dans la bibliothèque MFC.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CException::CException](../Topic/CException::CException.md)|Construit un objet `CException`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CException::Delete](../Topic/CException::Delete.md)|Supprime un objet d' `CException` .|  
|[CException::ReportError](../Topic/CException::ReportError.md)|Stocke un message d'erreur dans un message à l'utilisateur.|  
  
## Notes  
 Étant donné qu' `CException` est une classe de base abstraite vous ne pouvez pas créer d'objets d' `CException` directement ; vous devez créer des objets de classes dérivées.  Si vous devez créer votre propre classe de style d' `CException`, utilisez l'une des classes dérivées répertoriées ci\-dessus en tant que modèle.  Assurez\-vous que votre classe dérivée utilise également `IMPLEMENT_DYNAMIC`.  
  
 Les classes dérivées et leurs descriptions sont répertoriées ci\-dessous :  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Une classe de base des exceptions critiques ressource MFC|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Spécification d'exception d'argument non valide|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Exception de mémoire insuffisante|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Demande d'une opération non prise en charge|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Exception d'Archive\- spécifique|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|Exception de fichier spécifique|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Ressource est introuvable ou non être créés|  
|[COleException](../../mfc/reference/coleexception-class.md)|Exception OLE|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|Exception de base de données \(autrement dit, conditions d'exception surgissant pour les classes de base de données MFC basée sur Open Database Connectivity\)|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|Exception OLE de dispatch \(automation\)|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|Exception qui indique que ressource est introuvable|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Exception d'objets d'accès aux données \(autrement dit, conditions d'exception surgissant pour les classes DAO\)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Exception Internet \(autrement dit, conditions d'exception surgissant pour les classes Internet\).|  
  
 Ces exceptions sont conçues pour être utilisées avec les macros de [JET](../Topic/THROW%20\(MFC\).md), de [THROW\_LAST](../Topic/THROW_LAST.md), d' [ESSAI](../Topic/TRY.md), de [CATCH](../Topic/CATCH.md), d' [AND\_CATCH](../Topic/AND_CATCH.md), et d' [END\_CATCH](../Topic/END_CATCH.md) .  Pour plus d'informations sur les exceptions, consultez [Traitement des exceptions](../../mfc/reference/exception-processing.md)ou, consultez l'article [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
 Pour intercepter une exception spécifique, utilisez la classe dérivée appropriée.  Pour intercepter tous les types d'exceptions, utilisez `CException`, puis utiliser [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) pour distinguer entre `CException`\- classes dérivées.  Notez que les travaux de `CObject::IsKindOf` uniquement pour les classes ont été déclaré avec la macro d' [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) , afin de tirer parti de la vérification de type dynamique.  Tout `CException`\- la classe dérivée que vous créez doit utiliser la macro d' `IMPLEMENT_DYNAMIC` , et.  
  
 Vous pouvez enregistrer des informations détaillées sur les exceptions à l'utilisateur en appelant [GetErrorMessage](../Topic/CFileException::GetErrorMessage.md) ou [ReportError](../Topic/CException::ReportError.md), deux fonctions membres qui utilisent chacune des classes dérivées d'`CException`.  
  
 Si une exception est interceptée par l'une des macros, l'objet d' `CException` est supprimé automatiquement ; ne le supprimez pas vous\-même.  Si une exception est interceptée à l'aide d'un mot clé de **collecteur** , il n'est pas automatiquement désactivée.  Consultez l'article [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md) pour plus d'informations sur le moment où supprimer un objet d'exeption.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CException`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Traitement des exceptions](../../mfc/reference/exception-processing.md)   
 [Comment faire : Créez mes propres Classes exceptions personnalisées ?](http://go.microsoft.com/fwlink/?LinkId=128045)
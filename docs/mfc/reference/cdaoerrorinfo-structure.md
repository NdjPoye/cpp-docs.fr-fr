---
title: "CDaoErrorInfo, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoErrorInfo (structure)"
  - "DAO (Data Access Objects), Errors (collection)"
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoErrorInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `CDaoErrorInfo` contient des informations au sujet d'un objet d'erreur défini pour les objets d'accès aux données \(DAO\).  
  
## Syntaxe  
  
```  
  
      struct CDaoErrorInfo  
{  
   long m_lErrorCode;  
   CString m_strSource;  
   CString m_strDescription;  
   CString m_strHelpFile;  
   long m_lHelpContext;  
};  
```  
  
#### Paramètres  
 *m\_lErrorCode*  
 Un code d'erreur DAO numérique.  Consultez la rubrique « erreurs enregistrées d'accès aux données » dans l'aide de la DAO.  
  
 *m\_strSource*  
 Le nom de l'objet ou de l'application qui a initialement créé le problème.  La propriété Source spécifie une expression de chaîne qui représente l'objet qui a généré initialement l'erreur ; l'expression est habituellement le nom de classe de l'objet.  Pour plus d'informations, consultez la rubrique « Propriété Source » dans l'aide du DAO.  
  
 *m\_strDescription*  
 Chaîne descriptive associée à une erreur.  Pour plus d'informations, consultez la rubrique « Propriété de Description » dans l'aide du DAO.  
  
 *m\_strHelpFile*  
 Un chemin d'accès complet à un fichier d'aide de Microsoft Windows.  Pour plus d'informations, consultez la rubrique « HelpContext, propriétés HelpFile » dans l'aide du DAO.  
  
 *m\_lHelpContext*  
 Un ID de contexte pour une rubrique dans un fichier d'aide de Microsoft Windows.  Pour plus d'informations, consultez la rubrique « HelpContext, propriétés HelpFile » dans l'aide du DAO.  
  
## Notes  
 MFC n'inclut pas les objets d'erreur DAO dans une classe.  En revanche, la classe [CDaoException](../../mfc/reference/cdaoexception-class.md) fournit une interface pour accéder à la collection d'Erreurs contenues dans l'objet de DAO **DBEngine** , l'objet qui contient également tous les espaces de travail.  Lorsqu'une opération de MFC DAO lève un objet `CDaoException` que vous interceptez, MFC remplit la structure `CDaoErrorInfo` et la stocke dans le membre d'exception de l'objet [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md). \(Si vous choisissez d'appeler DAO directement, vous devez appeler vous\-mêmes la fonction membre de l'objet d'exception [GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) pour remplir `m_pErrorInfo`.\)  
  
 Pour plus d'informations sur la gestion des erreurs DAO, consultez l'article [Exceptions : Exceptions de base de données](../../mfc/exceptions-database-exceptions.md).  Pour plus d'informations, consultez la rubrique « Objet d'Erreur » dans l'aide du DAO.  
  
 Les informations récupérées par la fonction membre [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) sont stockées dans une structure `CDaoErrorInfo`.  Examinez le membre de données [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) d'un objet `CDaoException` que vous interceptez dans un gestionnaire des exceptions, ou appelez `GetErrorInfo` d'un objet `CDaoException` que vous créez explicitement pour surveiller les erreurs qui peuvent s'être produites lors d'un appel direct aux interfaces DAO.  `CDaoErrorInfo` définit également une fonction membre `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoErrorInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)
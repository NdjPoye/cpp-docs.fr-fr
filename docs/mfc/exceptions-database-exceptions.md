---
title: "Exceptions&#160;: exceptions de base de donn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (C++), exceptions"
  - "exceptions, base de données (C++)"
  - "bases de données (C++), gestion des exceptions"
  - "codes d'erreur (C++), gestion des exceptions de base de données"
  - "gestion des exceptions (C++), bases de données"
  - "exceptions (C++), base de données"
  - "ODBC (C++), exceptions"
  - "ODBC (exceptions) (C++)"
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions&#160;: exceptions de base de donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment gérer les exceptions de base de données.  La plupart du contenu dans cet article s'applique que vous utilisiez des classes de MFC pour Open Database Connectivity \(ODBC\) ou des classes de MFC pour DAO \(DAO\).  Le contenu spécifique à un modèle ou à un autre est explicitement marqué.  Les rubriques traitées ici sont les suivantes :  
  
-   [Approche pour la gestion des exceptions](#_core_approaches_to_exception_handling)  
  
-   [Un exemple de gestion des exceptions de base de données](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> Approche pour la gestion des exceptions  
 La méthode est identique que vous utilisiez DAO ou ODBC.  
  
 Vous devez toujours écrire des gestionnaires d'exceptions pour gérer des conditions exceptionnelles.  
  
 L'approche la plus pragmatique pour saisir des exceptions base de données est de tester votre application avec des scénarios d'exception.  Déterminez les exceptions potentielles susceptibles de se produire pour une opération dans votre code, et forcez l'exception à être générée.  Puis examinez le résultat de trace pour afficher l'exception qui est levée, ou pour examiner les informations d'erreur retournées dans le débogueur.  Ceci vous permet de savoir quels codes de retour vous verrez pour les scénarios d'exception utilisés.  
  
### Les codes d'erreur utilisés pour les exceptions ODBC  
 En plus des codes de retour définis par l'infrastructure, dont le nom du formulaire **AFX\_SQL\_ERROR\_XXX**, plusieurs [CDBExceptions](../mfc/reference/cdbexception-class.md) sont basés sur les codes de retour d' [ODBC](../data/odbc/odbc-basics.md).  Les codes de retour pour de telles exceptions ont des noms de la forme **SQL\_ERROR\_XXX**.  
  
 Les codes de retour — à la fois définis par l'infrastructure et par l'ODBC — que les classes de base de données peuvent retourner sont décrits dans le membre de données de [m\_nRetCode](../Topic/CDBException::m_nRetCode.md) de la classe `CDBException`.  Des informations supplémentaires sur les codes de retour définis par ODBC sont disponibles dans le *guide de référence du programmeur* dans le SDK du ODBC de la librairie MSDN.  
  
### Les codes d'erreur utilisés pour les exceptions DAO  
 Pour les exceptions de DAO, des informations supplémentaires sont généralement disponibles.  Vous pouvez accéder aux informations d'erreurs via trois membres de données d'un objet intercepté d' [CDaoException](../mfc/reference/cdaoexception-class.md):  
  
-   [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) contient un pointeur vers un objet d' [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) qui encapsule les informations d'erreur dans la collection de DAO d'objets d'erreur associés à la base de données.  
  
-   [m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md) contient le code d'erreur étendu des classes DAO MFC.  Les codes d'erreur, dont le nom est de la forme **AFX\_DAO\_ERROR\_XXX**, sont décrits dans le membre de données dans `CDaoException`.  
  
-   [m\_scode](../Topic/CDaoException::m_scode.md) contient un OLE `SCODE` du DAO, le cas échéant.  Toutefois, vous devrez rarement travailler avec ce code d'erreur.  Généralement plus d'informations sont disponibles dans les deux autres membres de données.  Consultez le membre de données pour plus d'informations sur les valeurs d' `SCODE`.  
  
 Des informations supplémentaires sur les erreurs DAO, le type de l'objet d'erreur DAO, et la collection d'erreurs DAO sont disponibles dans la classe [CDaoException](../mfc/reference/cdaoexception-class.md).  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> Un exemple de gestion des exceptions de base de données  
 Les tentatives d'exemple suivantes de construire [CRecordset](../mfc/reference/crecordset-class.md)\- objet dérivé sur le segment à l'aide de l'opérateur de **new**, puis d'ouvrir l'ensemble d'enregistrements \(pour une source de données ODBC\).  Pour un exemple similaire aux classes de DAO, consultez « Exemple d'exception de DAO » ci\-dessous.  
  
### Exemple d'exception ODBC  
 La fonction membre d' [Ouvrir](../Topic/CRecordset::Open.md) peut lever une exception \(de type [CDBException](../mfc/reference/cdbexception-class.md) pour les classes ODBC\), donc ce code attache l'appel d' **Ouvrir** dans un bloc de **Essayer**.  Le bloc **attraper** suivant interceptera un `CDBException`.  Vous pouvez examiner l'objet d'exception lui\-même, appelé `e`, mais dans ce cas il est suffisant de savoir que la tentative de création d'un recordset a échoué.  Le bloc **attraper** affiche une boîte de message et nettoie en supprimant l'objet recordset.  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/CPP/exceptions-database-exceptions_1.cpp)]  
  
### Exemple d'exception DAO  
 L'exemple de DAO est similaire à l'exemple pour ODBC, mais vous pouvez généralement extraire plusieurs types d'informations.  Le code suivant tente un recordset.  Si cette tentative lève une exception, vous pouvez examiner un membre de données de l'objet exception pour plus d'informations sur l'erreur.  Comme dans l'exemple précédent d'ODBC, il est probablement suffisant de savoir que la tentative de création d'un recordset a échoué.  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/CPP/exceptions-database-exceptions_2.cpp)]  
  
 Ce code obtient la chaîne de message d'erreur du membre d' [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) de l'objet exception.  MFC remplit ce membre lorsqu'elle lève l'exception.  
  
 Pour obtenir des informations sur les erreurs retournées par un objet d' `CDaoException`, consultez les classes [CDaoException](../mfc/reference/cdaoexception-class.md) et [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).  
  
 Lorsque vous utilisez des bases de données Microsoft Jet \(fichier .mdb\), et dans la plupart des cas lorsque vous utilisez ODBC, il n'y aura qu'un seul objet d'erreur.  Dans le cas très peu fréquent lorsque vous utilisez une source de données ODBC et qu'il existe plusieurs erreurs, vous pouvez faire une boucle dans la collection d'erreurs de DAO selon le nombre d'erreurs retournées par [CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md).  Chaque fois que la boucle est complétée, appelez [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) pour remplir le membre de données de `m_pErrorInfo`.  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)
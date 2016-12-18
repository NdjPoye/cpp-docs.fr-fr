---
title: "CDaoDatabaseInfo, structure | Microsoft Docs"
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
  - "CDaoDatabaseInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabaseInfo (structure)"
  - "DAO (Data Access Objects), Databases (collection)"
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoDatabaseInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure de `CDaoDatabaseInfo` contient des informations sur un objet de base de données défini pour les objets d'accès aux données \(DAO\).  
  
## Syntaxe  
  
```  
  
      struct CDaoDatabaseInfo  
{  
   CString m_strName;       // Primary  
   BOOL m_bUpdatable;       // Primary  
   BOOL m_bTransactions;    // Primary  
   CString m_strVersion;    // Secondary  
   long m_lCollatingOrder;  // Secondary  
   short m_nQueryTimeout;   // Secondary  
   CString m_strConnect;    // All  
};  
```  
  
#### Paramètres  
 `m_strName`  
 Noms seulement de l'objet de base de données.  Pour récupérer directement la propriété, appelez [CDaoQueryDef::GetName](../Topic/CDaoDatabase::GetName.md).  Pour plus d'informations, consultez la rubrique « Propriété du Nom » dans l'aide du DAO.  
  
 `m_bUpdatable`  
 Indique si des modifications peuvent être apportées à la base de données.  Pour extraire directement cette propriété, appelez [CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md).  Pour plus d'informations, consultez la rubrique « Propriété des mises à jour » dans l'aide du DAO.  
  
 *m\_bTransactions*  
 Indique si une source de données prend en charge les transactions — la journalisation d'une série de modifications qui peuvent être validées restauration \(annulation\) ou validé \(journaux de transactions\).  Si une base de données est basé sur le moteur de base de données Microsoft Jet, la propriété de transactions est différente de zéro et vous pouvez utiliser les transactions.  D'autres fournisseurs de base de données peuvent ne pas prendre en charge les transactions.  Pour extraire directement cette propriété, appelez [CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md).  Pour plus d'informations, consultez la rubrique « Propriété des transactions » dans l'aide du DAO.  
  
 *m\_strVersion*  
 Indique la version du moteur de base de données Microsoft Jet.  Pour récupérer la valeur de cette propriété directement, appelez la fonction membre de l'objet de base de données [GetName](../Topic/CDaoDatabase::GetVersion.md).  Pour plus d'informations, consultez la rubrique « Propriété des versions » dans l'aide du DAO.  
  
 `m_lCollatingOrder`  
 Spécifie la séquence de l'ordre de tri dans le texte de la comparaison ou le tri de chaîne.  Les valeurs possibles sont les suivantes :  
  
-   **dbSortGeneral** Utilisez l'ordre de tri général \(anglais, Français, Allemand, Portugais, Italien, Espagnol et moderne\).  
  
-   **dbSortArabic** utilisation de l'ordre de tri arabe.  
  
-   **dbSortCyrillic** utilisation de l'ordre de tri russe.  
  
-   **dbSortCzech** utilisation de l'ordre de tri tchèque.  
  
-   **dbSortDutch** utilisation de l'ordre de tri néerlandais.  
  
-   **dbSortGreek** utilisation de l'ordre de tri grec.  
  
-   **dbSortHebrew** utilisation de l'ordre de tri hébreu.  
  
-   **dbSortHungarian** utilisation de l'ordre de tri hongrois.  
  
-   **dbSortIcelandic** utilisation de l'ordre de tri islandais.  
  
-   **dbSortNorwdan** utilisation de l'ordre de tri norvégien ou danois.  
  
-   **dbSortPDXIntl** utilisation de l'ordre de tri d'entier de paradoxe.  
  
-   **dbSortPDXNor** utilisation de ordre de tri norvégien ou danois du paradoxe.  
  
-   **dbSortPDXSwe** utilisation de ordre de tri suédois ou finnois du paradoxe.  
  
-   **dbSortPolish** utilisation de l'ordre de tri polonais.  
  
-   **dbSortSpanish** utilisation de l'ordre de tri espagnol.  
  
-   **dbSortSwedFin** utilisation de l'ordre de tri suédois ou finnois.  
  
-   **dbSortTurkish** utilisation de l'ordre de tri turc.  
  
-   **dbSortUndefined** l'ordre de tri n'est pas défini ou inconnu.  
  
 Pour plus d'informations, consultez la rubrique « personnaliser les paramètres de Registre Windows pour l'accès aux données » dans l'aide du DAO.  
  
 *m\_nQueryTimeout*  
 Le nombre de secondes pendant lesquelles le moteur de base de données Microsoft Jet attend avant qu'une erreur de temporisation ne se produise lorsqu'une requête est exécutée sur une base de données ODBC.  La valeur par défaut est de 60 secondes.  Lorsque QueryTimeout est 0, aucun délai d'attente ne se produit ; cela peut entraîner l'exécution du programme la réponse.  Pour récupérer la valeur de cette propriété directement, appelez la fonction membre de l'objet de base de données [GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md).  Pour plus d'informations, consultez la rubrique « Propriété des QueryTimeout » dans l'aide du DAO.  
  
 `m_strConnect`  
 Fournit des informations sur la source d'une base de données ouverte.  Pour plus d'informations sur les chaînes de connexion, ainsi que pour plus d'informations sur la récupération direct de la valeur de cette propriété, consultez la méthode de [CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md).  Pour plus d'informations, consultez la rubrique "Propriété des connections" dans l'aide DAO.  
  
## Notes  
 La base de données est un objet DAO sous\-jacentes d'un objet de MFC de la classe [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md).  Des références au primaire, au secondaire, et au delà indiquent comment les informations sont retournées par la fonction membre [GetTableDefInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md) de la classe .  
  
 Les informations récupérées par la fonction membre de [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md) sont stockées dans une structure de `CDaoDatabaseInfo`.  Appelez `GetDatabaseInfo` pour l'objet `CDaoWorkspace` de base de données dans lequel la collection des objets de type requêtes, l'élément est enregistré.  `CDaoDatabaseInfo` définit également une fonction membre `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoDatabaseInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)
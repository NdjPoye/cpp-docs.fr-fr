---
title: "CDaoWorkspace Class | Microsoft Docs"
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
  - "CDaoWorkspace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspace class"
  - "DAO workspaces [C++]"
  - "DAO workspaces [C++], CDaoWorkspace class"
  - "database engine [C++], accessing via workspace"
  - "DDLs [C++]"
  - "default workspaces [C++]"
  - "default workspaces [C++], DAO"
  - "valeurs par défaut (C++), espaces de travail"
  - "ODBC (classes) (C++), vs. DAO classes"
  - "persistence [C++], DAO workspace"
  - "security [MFC]"
  - "security [MFC], DAO workspaces"
  - "sessions [C++], DAO workspace"
  - "transaction spaces [C++]"
  - "transaction spaces [C++], DAO workspace"
  - "Workspace class"
  - "workspaces [C++], DAO"
  - "workspaces [C++], par défaut"
  - "workspaces [C++], interface to database engine"
  - "workspaces [C++], persistance"
  - "Workspaces collection"
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoWorkspace Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère nommé, session de base de données protégé par un mot de passe de la connexion à fermer une session, par un mono\-utilisateur.  
  
## Syntaxe  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](../Topic/CDaoWorkspace::CDaoWorkspace.md)|Crée un objet workspace.  Une fois, appelez **Créer** ou **Ouvrir**.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoWorkspace::Append](../Topic/CDaoWorkspace::Append.md)|Ajoute un espace de travail récemment créé à la collection des espaces de travail du moteur de base de données.|  
|[CDaoWorkspace::BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md)|Commence une nouvelle transaction, qui s'applique à toutes les bases de données ouverts dans l'espace de travail.|  
|[CDaoWorkspace::Close](../Topic/CDaoWorkspace::Close.md)|Ferme l'espace de travail et tous les objets qu'elle contient.  En attente des transactions sont le restaurée.|  
|[CDaoWorkspace::CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md)|Termine la transaction en cours et enregistre les modifications.|  
|[CDaoWorkspace::CompactDatabase](../Topic/CDaoWorkspace::CompactDatabase.md)|Compacte \(ou doubles\) une base de données.|  
|[CDaoWorkspace::Create](../Topic/CDaoWorkspace::Create.md)|Crée un objet workspace DAO.|  
|[CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)|Retourne le nombre d'objets de base de données DAO dans la collection des bases de données de l'espace de travail.|  
|[CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md)|Retourne des informations sur les bases de données DAO spécifiées définies dans la collection des bases de données de l'espace de travail.|  
|[CDaoWorkspace::GetIniPath](../Topic/CDaoWorkspace::GetIniPath.md)|Retourne l'emplacement des paramètres de l'initialisation du moteur de base de données Microsoft Jet dans le Registre Windows.|  
|[CDaoWorkspace::GetIsolateODBCTrans](../Topic/CDaoWorkspace::GetIsolateODBCTrans.md)|Retourne une valeur qui indique si plusieurs transactions qui impliquent la même source de données ODBC sont isolés via plusieurs connexions liaison à la source de données.|  
|[CDaoWorkspace::GetLoginTimeout](../Topic/CDaoWorkspace::GetLoginTimeout.md)|Retourne le nombre de secondes avant qu'une erreur se produit lorsque l'utilisateur essaie d'ouvrir une session dans une base de données ODBC.|  
|[CDaoWorkspace::GetName](../Topic/CDaoWorkspace::GetName.md)|Retourne le nom défini par l'utilisateur pour l'objet workspace.|  
|[CDaoWorkspace::GetUserName](../Topic/CDaoWorkspace::GetUserName.md)|Retourne le nom d'utilisateur spécifié lorsque l'espace de travail a été créé.  Il s'agit du nom du propriétaire de l'espace de travail.|  
|[CDaoWorkspace::GetVersion](../Topic/CDaoWorkspace::GetVersion.md)|Retourne une chaîne qui contient la version du moteur de base de données associé à l'espace de travail.|  
|[CDaoWorkspace::GetWorkspaceCount](../Topic/CDaoWorkspace::GetWorkspaceCount.md)|Retourne le nombre d'objets workspaces DAO dans la collection des espaces de travail du moteur de base de données.|  
|[CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md)|Retourne des informations sur un espace de travail spécifié DAO défini dans la collection des espaces de travail du moteur de base de données.|  
|[CDaoWorkspace::Idle](../Topic/CDaoWorkspace::Idle.md)|Permet au moteur de base de données pour effectuer des tâches d'arrière\-plan.|  
|[CDaoWorkspace::IsOpen](../Topic/CDaoWorkspace::IsOpen.md)|Retourne une valeur différente de zéro si l'espace de travail est ouvert.|  
|[CDaoWorkspace::Open](../Topic/CDaoWorkspace::Open.md)|Ouvre explicitement un objet workspace associé à l'espace de travail par défaut DAO.|  
|[CDaoWorkspace::RepairDatabase](../Topic/CDaoWorkspace::RepairDatabase.md)|Essaie de réparer une base de données endommagée.|  
|[CDaoWorkspace::Rollback](../Topic/CDaoWorkspace::Rollback.md)|Termine la transaction en cours et ne parvenez pas à enregistrer les modifications.|  
|[CDaoWorkspace::SetDefaultPassword](../Topic/CDaoWorkspace::SetDefaultPassword.md)|Définit le mot de passe que le moteur de base de données utilise lorsqu'un objet workspace est créé sans mot de passe spécifique.|  
|[CDaoWorkspace::SetDefaultUser](../Topic/CDaoWorkspace::SetDefaultUser.md)|Définit le nom d'utilisateur que le moteur de base de données utilise lorsqu'un objet workspace est créé sans nom d'utilisateur spécifique.|  
|[CDaoWorkspace::SetIniPath](../Topic/CDaoWorkspace::SetIniPath.md)|Définit l'emplacement des paramètres de l'initialisation du moteur de base de données Microsoft Jet dans le Registre Windows.|  
|[CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md)|Spécifie si plusieurs transactions qui impliquent la même source de données ODBC sont isolées en forçant plusieurs connexions à la source de données.|  
|[CDaoWorkspace::SetLoginTimeout](../Topic/CDaoWorkspace::SetLoginTimeout.md)|Définit le nombre de secondes avant qu'une erreur se produit lorsque l'utilisateur essaie d'ouvrir une connexion à une source de données ODBC.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoWorkspace::m\_pDAOWorkspace](../Topic/CDaoWorkspace::m_pDAOWorkspace.md)|Pointe vers l'objet sous\-jacent workspace DAO.|  
  
## Notes  
 Dans la plupart des cas, vous n'avez pas besoin de plusieurs espaces de travail, et vous n'avez pas besoin de créer des objets workspaces explicites ; lorsque vous ouvrez la base de données et les objets recordset, ils utilisent l'espace de travail par défaut DAO.  Toutefois, si nécessaire, vous pouvez exécuter plusieurs sessions à la fois en créant des objets workspaces supplémentaires.  Chaque objet workspace peut contenir des objets de base de données ouverts multiples dans sa propre collection de base de données.  Dans MFC, un espace de travail est principalement un gestionnaire de transactions, en spécifiant un ensemble de bases de données ouvertes tout dans le même « espace de transaction. »  
  
> [!NOTE]
>  Les classes de bases de données DAO sont séparées des classes de base de données MFC basée sur \(Open Database Connectivity\).  Tous les noms de classes de bases de données DAO ont un préfixe « CDao ».  En général les classes DAO MFC basée sur sont plus qui gèrent les classes ODBC MFC basée sur.  Les classes DAO accèdent aux données via le moteur de base de données Microsoft Jet, y compris les pilotes ODBC.  Ils prennent également en charge des opérations de langage de définition de données \(DDL\), telles que la création de bases de données et ajouter des tables et des champs via des classes, sans devoir appeler DAO directement.  
  
## Fonctions  
 La classe fournit `CDaoWorkspace` ce qui suit :  
  
-   Accès explicite, si nécessaire, un espace de travail par défaut, créé lors de l'initialisation du moteur de base de données.  Habituellement vous l'espace de travail par défaut DAO d'utilisation implicitement en créant la base de données et les objets recordset.  
  
-   Un espace de transaction dans lequel les transactions s'appliquent à toutes les bases de données ouverts dans l'espace de travail.  Vous pouvez créer des espaces de travail supplémentaires pour gérer les espaces de transaction séparés.  
  
-   Une interface à de nombreuses propriétés du moteur de base de données Microsoft Jet sous\-jacent \(consultez les fonctions membres static\).  En ouvrant ou en créant un espace de travail, ou appeler une fonction membre statique avant d'ouvrir ou créer, initialisez le moteur de base de données.  
  
-   Accès à la collection des espaces de travail du moteur de base de données, qui stocke tous les espaces de travail actifs qui ont été ajoutés à celui\-ci.  Vous pouvez également créer et utiliser des espaces de travail sans les ajouter à la collection.  
  
## Sécurité  
 MFC n'implémente pas les utilisateurs et groupes ne pas les collections de DAO, qui sont utilisées pour la vérification de sécurité.  Si vous avez besoin de ces aspects de DAO, vous devez les programmer vous\-même via des appels directs aux interfaces DAO.  Pour plus d'informations, consultez [note technique 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## Utilisation  
 Vous pouvez utiliser la classe `CDaoWorkspace` :  
  
-   Ouvrez explicitement l'espace de travail par défaut.  
  
     Habituellement votre utilisation de l'espace de travail par défaut est implicite — lorsque vous ouvrez des nouveaux objets de [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) ou de [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) .  Mais vous devrez peut\-être y accéder de manière explicite \(par exemple, aux propriétés du moteur de base de données d'accès ou à la collection des espaces de travail.  Consultez « l'utilisation implicite de l'espace de travail par défaut » ci\-dessous.  
  
-   Créez les nouveaux espaces de travail.  Appelez [ajoutez](../Topic/CDaoWorkspace::Append.md) si vous souhaitez les ajouter à la collection des espaces de travail.  
  
-   Ouvrez un espace de travail existant dans la collection des espaces de travail.  
  
 Créer un espace de travail qui n'existe pas déjà dans la collection des espaces de travail est décrit dans la fonction membre de [Create](../Topic/CDaoWorkspace::Create.md) .  Les objets workspaces ne persistent pas de quelque manière entre les sessions du moteur de datababase.  Si les liens d'application MFC de manière statique, en terminant l'application uninitializes le moteur de base de données.  Si les liens d'application avec MFC dynamiquement, le moteur de base de données n'est pas initialisé lorsque la DLL MFC est déchargé.  
  
 Ouvrir explicitement l'espace de travail par défaut, ou ouvrir un espace de travail existant dans les espaces de travail collection, est décrit dans la fonction membre d' [Ouvrez](../Topic/CDaoWorkspace::Open.md) .  
  
 Terminer une session de l'espace de travail en fermant l'espace de travail avec la fonction membre de [Fermez](../Topic/CDaoWorkspace::Close.md) .  **Fermer** ferme toutes les bases de données que vous ne vous êtes pas fermées précédemment, roulant en arrière toutes les transactions non enregistrées.  
  
## Transactions  
 DAO gère les transactions au niveau de l'espace de travail ; par conséquent, les transactions dans un espace de travail avec les bases de données ouvertes multiples s'appliquent à toutes les bases de données.  Par exemple, si deux bases de données ont les mises à jour non enregistrées et vous appelez [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md), toutes les mises à jour sont validées.  Si vous souhaitez limiter les transactions à une base de données, il vous faut un objet workspace séparé pour lui.  
  
## Utilisation implicite de l'espace de travail par défaut  
 L'espace de travail par défaut DAO runtime utilise MFC implicitement dans les circonstances suivantes :  
  
-   Si vous créez un objet d' `CDaoDatabase` mais ne le faites pas faire via un objet existant d' `CDaoWorkspace` , MFC crée un objet workspace temporaire pour vous, qui correspond à l'espace de travail par défaut DAO.  Si vous procédez ainsi pour plusieurs bases de données, tous les objets de base de données sont associés à l'espace de travail par défaut.  Vous pouvez accéder à l'espace de travail d'une base de données via une donnée membre d' `CDaoDatabase` .  
  
-   De même, si vous créez un objet d' `CDaoRecordset` sans fournir un pointeur vers un objet d' `CDaoDatabase` , MFC crée un objet de base de données temporaire et, par extension, un objet workspace temporaire.  Vous pouvez accéder à la base de données du recordset, et indirectement à son espace de travail, via une donnée membre d' `CDaoRecordset` .  
  
## D'autres opérations  
 D'autres opérations de base de données sont également fournies, tel que réparer une base de données est endommagé ou compacter une base de données.  
  
 Pour plus d'informations sur l'appel DAO directement et sur la sécurité DAO, consultez [note technique 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)
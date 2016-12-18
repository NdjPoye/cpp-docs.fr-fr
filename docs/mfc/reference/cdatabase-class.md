---
title: "CDatabase Class | Microsoft Docs"
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
  - "CDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDatabase (classe)"
  - "classes de base de données (C++), ODBC"
  - "connexions de base de données (C++), CDatabase (classe)"
  - "MFC (C++), ODBC"
  - "ODBC (C++), CDatabase (classe)"
  - "ODBC database class"
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: 24
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une connexion à une source de données, dans laquelle vous pouvez traiter la source de données.  
  
## Syntaxe  
  
```  
  
class CDatabase : public CObject  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDatabase::CDatabase](../Topic/CDatabase::CDatabase.md)|Construit un objet `CDatabase`.  Vous devez initialiser l'objet en appelant `OpenEx` ou **Ouvrir**.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDatabase::BeginTrans](../Topic/CDatabase::BeginTrans.md)|Commence une transaction «  » — une série d'appels réversibles à `AddNew`, à **Modifier**, à **Supprimer**, et les fonctions membres de **Mettre à jour** de la classe `CRecordset` — sur la source de données connectée.  La source de données doit prendre en charge les transactions pour **BeginTrans** a aucun effet.|  
|[CDatabase::BindParameters](../Topic/CDatabase::BindParameters.md)|Vous permet de définir des paramètres de manipulation avant d'appeler `CDatabase::ExecuteSQL`.|  
|[CDatabase::Cancel](../Topic/CDatabase::Cancel.md)|Annule une opération asynchrone ou un processus d'un deuxième thread.|  
|[CDatabase::CanTransact](../Topic/CDatabase::CanTransact.md)|Retourne une valeur différente de zéro si la source de données prend en charge les transactions.|  
|[CDatabase::CanUpdate](../Topic/CDatabase::CanUpdate.md)|Retourne une valeur différente de zéro si l'objet d' `CDatabase` peut être mise à jour \(non en lecture seule\).|  
|[CDatabase::Close](../Topic/CDatabase::Close.md)|Ferme la connexion à la source de données.|  
|[CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md)|Termine une transaction démarrée par **BeginTrans**.  Les commandes de la transaction qui modifient la source de données sont exécutées.|  
|[CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)|Exécute une instruction SQL.  Aucun enregistrement de données n'est retourné.|  
|[CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md)|Identifie les opérations dans lesquelles les signets persistent sur des objets recordset.|  
|[CDatabase::GetConnect](../Topic/CDatabase::GetConnect.md)|Retourne la chaîne de connexion ODBC utilisée pour connecter l'objet d' `CDatabase` à une source de données.|  
|[CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md)|Identifie l'effet de valider une transaction sur un objet recordset ouvert.|  
|[CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md)|Identifie l'effet de restauration d'une transaction sur un objet recordset ouvert.|  
|[CDatabase::GetDatabaseName](../Topic/CDatabase::GetDatabaseName.md)|Retourne le nom de la base de données en cours de utilisation.|  
|[CDatabase::IsOpen](../Topic/CDatabase::IsOpen.md)|Retourne une valeur différente de zéro si l'objet d' `CDatabase` est actuellement connecté à une source de données.|  
|[CDatabase::OnSetOptions](../Topic/CDatabase::OnSetOptions.md)|Appelé par l'infrastructure pour définir des options de connexion standard.  L'implémentation par défaut définit la valeur du délai d'expiration de la requête.  Vous pouvez générer ces options d'avance en appelant `SetQueryTimeout`.|  
|[CDatabase::Open](../Topic/CDatabase::Open.md)|Établit une connexion à une source de données \(par le biais d'un pilote ODBC\).|  
|[CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md)|Établit une connexion à une source de données \(par le biais d'un pilote ODBC\).|  
|[CDatabase::Rollback](../Topic/CDatabase::Rollback.md)|Modifications de l'inverse apportées pendant la transaction en cours.  La source de données retourne à son état précédent, comme défini à l'appel de **BeginTrans** , inchangé.|  
|[CDatabase::SetLoginTimeout](../Topic/CDatabase::SetLoginTimeout.md)|Définit le nombre de secondes après quoi une tentative de connexion de source de données chronomètrera.|  
|[CDatabase::SetQueryTimeout](../Topic/CDatabase::SetQueryTimeout.md)|Définit le nombre de secondes après quoi les opérations de requête de base de données chronomètreront.  Affecte tout le recordset suivant **Ouvrir**, `AddNew`, **Modifier**, et appels de **Supprimer** .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDatabase::m\_hdbc](../Topic/CDatabase::m_hdbc.md)|Handle de connexion ODBC \(Open Database Connectivity\) à une source de données.  Tapez **HDBC**.|  
  
## Notes  
 Une source de données est une instance spécifique de données hébergées par un certain système de gestion de base de données \(SGBD\).  Les exemples incluent le dBASE Microsoft SQL Server, Microsoft Access, de Borland, et le xBASE.  Vous pouvez avoir un ou plusieurs objets d' `CDatabase` actifs à la fois dans votre application.  
  
> [!NOTE]
>  Si vous utilisez DAO \(DAO\) classe plutôt que les classes ODBC \(Open Database Connectivity\), utilisez la classe [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) à la place.  Pour plus d'informations, consultez l'article [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md).  
  
 Pour utiliser `CDatabase`, construisez un objet d' `CDatabase` et appelez sa fonction membre d' `OpenEx` .  Cela ouvre une connexion.  Lorsque vous construisez ensuite des objets d' `CRecordset` pour s'exécuter sur la source de données connectée, passez le constructeur de recordsets un pointeur vers l'objet d' `CDatabase` .  Lorsque vous avez fini d'utiliser la connexion, appelez la fonction membre de **Fermer** et détruisez l'objet d' `CDatabase` .  **Fermer** ferme tous les recordsets que vous ne vous êtes pas fermés précédemment.  
  
 Pour plus d'informations sur `CDatabase`, consultez les articles [source de données \(ODBC\)](../../data/odbc/data-source-odbc.md) et [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## Configuration requise  
 **Header:** afxdb.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)
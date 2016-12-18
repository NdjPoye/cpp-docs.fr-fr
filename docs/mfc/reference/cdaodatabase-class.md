---
title: "CDaoDatabase Class | Microsoft Docs"
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
  - "CDaoDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabase class"
  - "CDaoDatabase class, and workspace"
  - "CDaoDatabase class, vs. CDatabase class"
  - "CDatabase (classe), vs. CDaoDatabase class"
  - "classes de base de données (C++), DAO"
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une connexion à une base de données dans laquelle vous pouvez traiter les données.  
  
## Syntaxe  
  
```  
class CDaoDatabase : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoDatabase::CDaoDatabase](../Topic/CDaoDatabase::CDaoDatabase.md)|Construit un objet `CDaoDatabase`.  Appelez **Ouvrir** pour connecter l'objet à une base de données.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md)|Retourne une valeur différente de zéro si les transactions de prend en charge des bases de données.|  
|[CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md)|Retourne une valeur différente de zéro si l'objet d' `CDaoDatabase` peut être mise à jour \(non en lecture seule\).|  
|[CDaoDatabase::Close](../Topic/CDaoDatabase::Close.md)|Ferme la connexion de base de données.|  
|[CDaoDatabase::Create](../Topic/CDaoDatabase::Create.md)|Crée l'objet de base de données DAO sous\-jacent et initialise l'objet d' `CDaoDatabase` .|  
|[CDaoDatabase::CreateRelation](../Topic/CDaoDatabase::CreateRelation.md)|Définit une nouvelle relation entre les tables dans la base de données.|  
|[CDaoDatabase::DeleteQueryDef](../Topic/CDaoDatabase::DeleteQueryDef.md)|Supprime un objet de querydef enregistré dans la collection de QueryDefs de la base de données.|  
|[CDaoDatabase::DeleteRelation](../Topic/CDaoDatabase::DeleteRelation.md)|Supprime une relation existant entre les tables dans la base de données.|  
|[CDaoDatabase::DeleteTableDef](../Topic/CDaoDatabase::DeleteTableDef.md)|Supprime la définition d'une table dans la base de données.  Cela supprime le tableau réel et toutes ses données.|  
|[CDaoDatabase::Execute](../Topic/CDaoDatabase::Execute.md)|Exécute une requête Action.  Appelant **Exécuter** pour une requête qui retourne des résultats lève une exception.|  
|[CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md)|Retourne la chaîne de connexion utilisée pour connecter l'objet d' `CDaoDatabase` à une base de données.  Utilisé pour ODBC.|  
|[CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md)|Retourne le nom de la base de données en cours de utilisation.|  
|[CDaoDatabase::GetQueryDefCount](../Topic/CDaoDatabase::GetQueryDefCount.md)|Retourne le nombre de requêtes définies pour la base de données.|  
|[CDaoDatabase::GetQueryDefInfo](../Topic/CDaoDatabase::GetQueryDefInfo.md)|Retourne des informations sur une requête spécifiée définie dans la base de données.|  
|[CDaoDatabase::GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md)|Retourne le nombre de secondes après quoi les opérations de requête de base de données chronomètreront.  Affecte ouvert tout suivant, ajoute nouveau, mise à jour, et modifications et d'autres opérations sur les sources de données ODBC \(uniquement\) tels que des appels de **Exécuter** .|  
|[CDaoDatabase::GetRecordsAffected](../Topic/CDaoDatabase::GetRecordsAffected.md)|Retourne le nombre d'enregistrements affectés par la dernière modification, la modification, ou l'opérateur d'addition ou par un appel à **Exécuter**.|  
|[CDaoDatabase::GetRelationCount](../Topic/CDaoDatabase::GetRelationCount.md)|Retourne le nombre de relations définies entre les tables dans la base de données.|  
|[CDaoDatabase::GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md)|Retourne des informations sur une relation spécifiée définie entre les tables dans la base de données.|  
|[CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md)|Retourne le nombre de tables définies dans la base de données.|  
|[CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)|Retourne des informations sur une table spécifiée dans la base de données.|  
|[CDaoDatabase::GetVersion](../Topic/CDaoDatabase::GetVersion.md)|Retourne la version du moteur de base de données associé à la base de données.|  
|[CDaoDatabase::IsOpen](../Topic/CDaoDatabase::IsOpen.md)|Retourne une valeur différente de zéro si l'objet d' `CDaoDatabase` est actuellement connecté à une base de données.|  
|[CDaoDatabase::Open](../Topic/CDaoDatabase::Open.md)|Établit une connexion à une base de données.|  
|[CDaoDatabase::SetQueryTimeout](../Topic/CDaoDatabase::SetQueryTimeout.md)|Définit le nombre de secondes après quoi les opérations de requête de base de données \(sur les sources de données ODBC uniquement\) chronomètreront.  Affecte ouvert tout suivant, ajoute une nouvelle fois, la mise à jour, et les opérations de suppression.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoDatabase::m\_pDAODatabase](../Topic/CDaoDatabase::m_pDAODatabase.md)|Pointeur vers l'objet de base de données DAO sous\-jacent.|  
|[CDaoDatabase::m\_pWorkspace](../Topic/CDaoDatabase::m_pWorkspace.md)|Pointeur vers l'objet de [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) qui contient la base de données et définit son espace de transaction.|  
  
## Notes  
 Pour plus d'informations sur les formats de base de données pris en charge, consultez la fonction membre de [GetName](../Topic/CDaoWorkspace::GetName.md) .  Vous pouvez avoir un ou plusieurs objets d' `CDaoDatabase` actifs à la fois dans un « espace de travail donné, » représenté par un objet de [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) .  L'espace de travail gère une collection d'objets de base de données ouverts, appelée la collection de base de données.  
  
> [!NOTE]
>  Les classes de bases de données DAO MFC sont séparées des classes de base de données MFC basée sur ODBC.  Tous les noms de classes de bases de données DAO ont le préfixe « CDao ».  La classe `CDaoDatabase` fournit une interface semblable à celle de la classe [CDatabase](../../mfc/reference/cdatabase-class.md)ODBC.  La principale différence est qu' `CDatabase` accède au système de gestion de base de données via \(Open Database Connectivity\) et un pilote ODBC pour ce système de gestion de base de données.  `CDaoDatabase` accède aux données via un objet d'accès aux données \(DAO\) sur le moteur de base de données Microsoft Jet.  En général les classes DAO MFC basée sur sont plus qui gèrent les classes ODBC MFC basée sur ; les classes DAO peuvent accéder aux données, notamment via des pilotes ODBC, via leur propre moteur de base de données.  Les classes DAO prennent également en charge des opérations de langage de définition de données \(DDL\), telles que l'ajout de tables via des classes, sans devoir appeler DAO directement.  
  
## Utilisation  
 Vous pouvez créer des objets de base de données implicitement, lorsque vous créez des objets recordset.  Mais vous pouvez également créer des objets de base de données explicitement.  Pour utiliser une base de données existante explicitement avec `CDaoDatabase`, effectuez l'une des opérations suivantes :  
  
-   Construisez un objet d' `CDaoDatabase` , en passant un pointeur vers un objet ouvert de [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) .  
  
-   Ou construisez un objet d' `CDaoDatabase` sans spécifier l'espace de travail \(MFC crée un objet temporaire workspace\).  
  
 Pour créer une base de données Microsoft Jet \(.MDB\), construisez un objet d' `CDaoDatabase` et appelez sa fonction membre de [Create](../Topic/CDaoDatabase::Create.md) .  n'appelez pas **Ouvrir** après **Créer**.  
  
 Pour ouvrir une base de données existante, construisez un objet d' `CDaoDatabase` et appelez sa fonction membre d' [Ouvrez](../Topic/CDaoDatabase::Open.md) .  
  
 L'un de ces techniques ajoute l'objet de base de données DAO aux bases de données collection de l'espace de travail et ouvre une connexion aux données.  Lorsque vous construisez ensuite des objets de [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), de [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), ou de [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) pour s'exécuter sur la base de données connectée, passez les constructeurs de ces objets un pointeur vers l'objet d' `CDaoDatabase` .  Lorsque vous avez fini d'utiliser la connexion, appelez la fonction membre de [Fermez](../Topic/CDaoDatabase::Close.md) et détruisez l'objet d' `CDaoDatabase` .  **Fermer** ferme tous les recordsets que vous ne vous êtes pas fermés précédemment.  
  
## Transactions  
 Le traitement des transactions de base de données est fourni au niveau de l'espace de travail \(consultez les fonctions membres de [BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md), de [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md), et de [Restaurer](../Topic/CDaoWorkspace::Rollback.md) de la classe `CDaoWorkspace`.  
  
## Connexions ODBC  
 La méthode recommandée pour travailler avec des sources de données ODBC est de joindre les tables externes à une base de données Microsoft Jet \(.MDB\).  
  
## Regroupements  
 Chaque base de données met à jour ses propres collections de tabledef, de querydef, de recordset, et d'objets relation.  La classe `CDaoDatabase` fournit les fonctions membres pour manipuler ces objets.  
  
> [!NOTE]
>  Les objets sont stockés dans DAO, pas dans l'objet de base de données MFC.  MFC fournit des classes pour le tabledef, le querydef, et les objets recordset mais pas pour les objets relation.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)
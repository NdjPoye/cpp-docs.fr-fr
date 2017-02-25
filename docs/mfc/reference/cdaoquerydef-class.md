---
title: "CDaoQueryDef Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoQueryDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoQueryDef class"
  - "requêtes (Visual Studio), defining"
  - "QueryDef objects"
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoQueryDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une définition de requête, ou « querydef, » généralement un enregistrement dans une base de données.  
  
## Syntaxe  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](../Topic/CDaoQueryDef::CDaoQueryDef.md)|Crée un objet de **CDaoQueryDef** .  L'appel suivant **Ouvrir** ou **Créer**, selon vos besoins.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoQueryDef::Append](../Topic/CDaoQueryDef::Append.md)|Ajoute le querydef à la collection de QueryDefs de la base de données en tant que requête enregistrée.|  
|[CDaoQueryDef::CanUpdate](../Topic/CDaoQueryDef::CanUpdate.md)|Retourne une valeur différente de zéro si la requête peut mettre à jour la base de données.|  
|[CDaoQueryDef::Close](../Topic/CDaoQueryDef::Close.md)|Ferme l'objet de querydef.  Détruisez l'objet C\+\+ lorsque vous avez terminé avec lui.|  
|[CDaoQueryDef::Create](../Topic/CDaoQueryDef::Create.md)|Crée l'objet sous\-jacent de querydef DAO.  Utilisez le querydef comme une requête temporaire, ou appelez **Ajouter** pour l'enregistrer dans la base de données.|  
|[CDaoQueryDef::Execute](../Topic/CDaoQueryDef::Execute.md)|Exécute la requête définie par l'objet de querydef.|  
|[CDaoQueryDef::GetConnect](../Topic/CDaoQueryDef::GetConnect.md)|Retourne la chaîne de connexion associée au querydef.  La chaîne de connexion identifie la source de données.  \(Pour les requêtes SQL direct uniquement ; sinon une chaîne vide.\)|  
|[CDaoQueryDef::GetDateCreated](../Topic/CDaoQueryDef::GetDateCreated.md)|Retourne la date à laquelle la requête enregistrée a été créée.|  
|[CDaoQueryDef::GetDateLastUpdated](../Topic/CDaoQueryDef::GetDateLastUpdated.md)|Retourne la date à laquelle la requête enregistrée à partir de la dernière mise à jour.|  
|[CDaoQueryDef::GetFieldCount](../Topic/CDaoQueryDef::GetFieldCount.md)|Retourne le nombre de champs définis par le querydef.|  
|[CDaoQueryDef::GetFieldInfo](../Topic/CDaoQueryDef::GetFieldInfo.md)|Retourne des informations sur un champ spécifié défini dans la requête.|  
|[CDaoQueryDef::GetName](../Topic/CDaoQueryDef::GetName.md)|Retourne le nom de querydef.|  
|[CDaoQueryDef::GetODBCTimeout](../Topic/CDaoQueryDef::GetODBCTimeout.md)|Retourne la valeur du délai d'attente utilisée par ODBC \(pour une requête ODBC\) lorsque le querydef est exécuté.  Cela détermine le temps tenir compte pour l'action de la requête se termine.|  
|[CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md)|Retourne le nombre de paramètres définis pour la requête.|  
|[CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md)|Retourne des informations sur un paramètre spécifié à la requête.|  
|[CDaoQueryDef::GetParamValue](../Topic/CDaoQueryDef::GetParamValue.md)|Retourne la valeur d'un paramètre spécifié à la requête.|  
|[CDaoQueryDef::GetRecordsAffected](../Topic/CDaoQueryDef::GetRecordsAffected.md)|Retourne le nombre d'enregistrements affectés par une requête Action.|  
|[CDaoQueryDef::GetReturnsRecords](../Topic/CDaoQueryDef::GetReturnsRecords.md)|Retourne une valeur différente de zéro si la requête définie par le querydef retourne des enregistrements.|  
|[CDaoQueryDef::GetSQL](../Topic/CDaoQueryDef::GetSQL.md)|Retourne la chaîne SQL qui spécifie la requête définie par le querydef.|  
|[CDaoQueryDef::GetType](../Topic/CDaoQueryDef::GetType.md)|Retourne le type de requête : supprimez, mettez à jour, ajoutez, faire\- table, et ainsi de suite.|  
|[CDaoQueryDef::IsOpen](../Topic/CDaoQueryDef::IsOpen.md)|Retourne une valeur différente de zéro si le querydef est ouvert et peut être exécuté.|  
|[CDaoQueryDef::Open](../Topic/CDaoQueryDef::Open.md)|Ouvre un querydef existant enregistré dans la collection de QueryDefs de la base de données.|  
|[CDaoQueryDef::SetConnect](../Topic/CDaoQueryDef::SetConnect.md)|Définit la chaîne de connexion pour une requête SQL direct sur une source de données ODBC.|  
|[CDaoQueryDef::SetName](../Topic/CDaoQueryDef::SetName.md)|Définit le nom de la requête enregistrée, en substituant le nom de service lorsque le querydef a été créé.|  
|[CDaoQueryDef::SetODBCTimeout](../Topic/CDaoQueryDef::SetODBCTimeout.md)|Définit la valeur du délai d'attente utilisée par ODBC \(pour une requête ODBC\) lorsque le querydef est exécuté.|  
|[CDaoQueryDef::SetParamValue](../Topic/CDaoQueryDef::SetParamValue.md)|Définit la valeur d'un paramètre spécifié à la requête.|  
|[CDaoQueryDef::SetReturnsRecords](../Topic/CDaoQueryDef::SetReturnsRecords.md)|Spécifie si le querydef retourne des enregistrements.  La définition de cet attribut à **TRUE** est valide que pour les requêtes SQL direct.|  
|[CDaoQueryDef::SetSQL](../Topic/CDaoQueryDef::SetSQL.md)|Définit la chaîne SQL qui spécifie la requête définie par le querydef.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoQueryDef::m\_pDAOQueryDef](../Topic/CDaoQueryDef::m_pDAOQueryDef.md)|Un pointeur vers OLE interface pour l'objet sous\-jacent de querydef DAO.|  
|[CDaoQueryDef::m\_pDatabase](../Topic/CDaoQueryDef::m_pDatabase.md)|Pointeur vers l'objet d' `CDaoDatabase` auquel le querydef est associé.  Le querydef peut être enregistré dans la base de données ou pas.|  
  
## Notes  
 Un querydef est objet d'accès aux données qui contient l'instruction SQL qui décrit une requête, et ses propriétés, telles que « date de création » et « délai d'attente de ODBC. » Vous pouvez également créer des objets temporaires de querydef sans les enregistrer, mais il est pratique \)et beaucoup plus efficace — d'enregistrer des requêtes en général réutilisées dans une base de données.  Un objet de [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) gère une collection appelée, la collection de QueryDefs, qui contient les querydefs enregistrés.  
  
> [!NOTE]
>  Les classes de bases de données DAO sont séparées des classes de base de données MFC basée sur \(Open Database Connectivity\).  Tous les noms de classes de bases de données DAO ont le préfixe « CDao ».  Vous pouvez encore accéder aux sources de données ODBC avec les classes DAO.  En général les classes DAO MFC basée sur sont plus qui gèrent les classes ODBC MFC basée sur ; les classes DAO peuvent accéder aux données, notamment via des pilotes ODBC, via leur propre moteur de base de données.  Les classes DAO prennent également en charge des opérations de langage de définition de données \(DDL\), telles que l'ajout de tables via des classes, sans devoir appeler DAO directement.  
  
## Utilisation  
 Le querydef d'utilisation des objets d'utiliser une requête enregistrée existante ou pour créer une nouvelle requête enregistrée ou à la requête temporaire :  
  
1.  Dans tous les cas, construisez d'abord un objet d' `CDaoQueryDef` , en fournissant un pointeur vers l'objet de [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) auquel la requête appartient.  
  
2.  Effectuez ensuite les éléments suivants, selon que vous voulez :  
  
    -   Pour utiliser une requête enregistrée existante, appelez la fonction membre d' [Ouvrez](../Topic/CDaoQueryDef::Open.md) de l'objet de querydef, en fournissant le nom de la requête enregistrée.  
  
    -   Pour créer une nouvelle requête enregistrée, appelez la fonction membre de [Create](../Topic/CDaoQueryDef::Create.md) de l'objet de querydef, en fournissant le nom de la requête.  Appelez ensuite [ajoutez](../Topic/CDaoQueryDef::Append.md) pour enregistrer la requête en l'ajoutant à la collection de QueryDefs de la base de données.  **Créer** place le querydef dans un état ouvert, donc après avoir appelé **Créer** que vous n'appelez pas **Ouvrir**.  
  
    -   Pour créer un querydef temporaire, appelez **Créer**.  Passez une chaîne vide pour le nom de requête.  n'appelez pas **Ajouter**.  
  
 Lorsque vous avez fini d'utiliser un objet de querydef, appelez sa fonction membre de [Fermez](../Topic/CDaoQueryDef::Close.md) ; détruisez l'objet de querydef.  
  
> [!TIP]
>  La façon la plus simple de créer des requêtes enregistrées est de créer et de les enregistrer dans votre base de données à l'aide de Microsoft Access.  Vous pouvez ouvrir et les utiliser dans votre code MFC.  
  
## Objectifs  
 Vous pouvez utiliser un objet de querydef pour chacune des fins :  
  
-   Pour créer un objet d' `CDaoRecordset`  
  
-   Pour appeler la fonction membre de **Exécuter** de l'objet pour exécuter directement une requête Action ou une requête SQL direct  
  
 Vous pouvez utiliser un objet de querydef pour tout type de requête, y compris sélectionnez, l'action, l'analyse croisée, la suppression, la mise à jour, l'ajout, le faire\- table, la définition de données, le convertisseur SQL, l'union, et les requêtes en bloc.  Le type de la requête est déterminé par le contenu de l'instruction SQL que vous fournissez.  Pour plus d'informations sur les types de requêtes, consultez **Exécuter** les fonctions membres et de [GetType](../Topic/CDaoQueryDef::GetType.md) .  Les recordsets sont généralement utilisés pour les requêtes ligne\- se retournantes, généralement ceux utilisant **le SELECT…**  Les mots clés.  **Exécuter** est le plus couramment utilisé pour les opérations en bloc.  Pour plus d'informations, consultez [exécutez](../Topic/CDaoQueryDef::Execute.md) et le [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## Querydefs et recordsets  
 Pour utiliser un objet de querydef pour créer un objet d' `CDaoRecordset` , vous créez généralement ou ouvrez un querydef comme décrit ci\-dessus.  Construisez l'objet recordset, en passant un pointeur vers l'objet de querydef lorsque vous appelez [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md).  Le querydef que vous passez doit être dans un état ouvert.  Pour plus d'informations, consultez la classe [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Vous ne pouvez pas utiliser un querydef pour créer un recordset \(le plus souvent utilisé pour un querydef\) à moins qu'il soit dans un état ouvert.  Placez le querydef dans un état ouvert en appelant **Ouvrir** ou **Créer**.  
  
## Bases de données externes  
 Les objets de Querydef représentent la meilleure façon d'utiliser le dialecte natif de SQL par un moteur de base de données externe.  Par exemple, vous pouvez créer une requête SQL du traitement \(comme utilisé dans Microsoft SQL Server\) et le stocker dans un objet de querydef.  Lorsque vous devez utiliser une requête SQL pas sur le moteur de base de données Microsoft Jet, vous devez fournir une chaîne de connexion qui indique la source de données externe.  Les requêtes avec les chaînes de connexion valides ignorent le moteur de base de données et passez la requête directement au serveur de base de données externe pour traiter.  
  
> [!TIP]
>  La meilleure façon d'utiliser les tableaux ODBC est de les lier à une base de données Microsoft Jet \(.MDB\).  
  
 Pour des informations connexes, consultez les rubriques « objet de QueryDef », « collection de QueryDefs », et « objet de CdbDatabase » dans le Kit de développement logiciel.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)
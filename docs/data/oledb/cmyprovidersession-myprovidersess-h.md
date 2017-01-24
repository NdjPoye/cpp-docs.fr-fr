---
title: "CMyProviderSession (MyProviderSess.H) | Microsoft Docs"
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
  - "cmyprovidersession"
  - ""myprovidersess.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSession (classe dans MyProviderSess.H)"
  - "fournisseurs OLE DB, fichiers générés par l'Assistant"
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSession (MyProviderSess.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MyProviderSess.H contient la déclaration et l'implémentation de l'objet session OLE DB.  L'objet source de données crée l'objet de session et représente une conversation entre un consommateur et un fournisseur.  Plusieurs sessions simultanées peuvent être ouvertes pour une source de données.  La liste d'héritage de `CMyProviderSession` est comme suit :  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 L'objet session hérite des interfaces **IGetDataSource**, `IOpenRowset`, **ISessionProperties** et **IDBCreateCommand**.  L'interface **IGetDataSource** permet à une session de récupérer la source de données qui l'a créée.  Cette option est pratique si vous avez besoin d'obtenir des propriétés de la source de données que vous avez créée ou d'autres informations que la source de données peut fournir.  L'interface **ISessionProperties** gère toutes les propriétés de la session.  Les interfaces `IOpenRowset` et **IDBCreateCommand** sont utilisées pour l'exécution des tâches de la base de données.  Si le fournisseur prend en charge les commandes, il implémente l'interface **IDBCreateCommand**.  Il permet de créer l'objet command qui peut exécuter les commandes.  Le fournisseur implémente toujours l'objet `IOpenRowset`.  Il est utilisé pour générer un jeu de lignes simple à partir d'un fournisseur.  Il s'agit normalement d'un jeu de lignes par défaut \(par exemple, `"select * from mytable"`\) provenant d'un fournisseur.  
  
 L'Assistant génère également trois classes de session : `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema` et `CMyProviderSessionTRSchema`.  Ces sessions sont utilisées pour les jeux de lignes du schéma.  Les jeux de lignes du schéma permettent au fournisseur de retourner des métadonnées au consommateur sans que celui\-ci ait à exécuter une requête ni à extraire des données.  L'extraction de métadonnées peut être une opération beaucoup plus rapide que la découverte des fonctionnalités d'un fournisseur.  
  
 La spécification OLE DB requiert que les fournisseurs implémentant l'interface **IDBSchemaRowset** prennent en charge trois types de jeux de lignes : **DBSCHEMA\_COLUMNS**, **DBSCHEMA\_PROVIDER\_TYPES** et `DBSCHEMA_TABLES`.  L'Assistant génère des implémentations pour chaque jeu de lignes du schéma.  Chaque classe générée par l'Assistant contient une méthode `Execute`.  Dans cette méthode `Execute`, vous pouvez retourner au fournisseur des données sur les tables, les colonnes et les types de données que vous prenez en charge.  Ces données sont généralement connues au moment de la compilation.  
  
## Voir aussi  
 [Fichiers générés par l'Assistant Fournisseur](../../data/oledb/provider-wizard-generated-files.md)
---
title: "CDataConnection, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataConnection"
  - "ATL.CDataConnection"
  - "CDataConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataConnection (classe)"
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CDataConnection, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère la connexion à la source de données.  
  
## Syntaxe  
  
```  
class CDataConnection  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|Constructeur.  Instancie et initialise un objet `CDataConnection`.|  
|[Copier](../../data/oledb/cdataconnection-copy.md)|Crée une copie d'une connexion de données existante.|  
|[Ouvrez .](../../data/oledb/cdataconnection-open.md)|Établit une connexion à une source de données à l'aide d'une chaîne d'initialisation.|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|Ouvre une session sur la connexion actuelle.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[BOOL, opérateur](../../data/oledb/cdataconnection-operator-bool.md)|Détermine si la session actuelle est ouverte ou non.|  
|[bool \(opérateur\)](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|Détermine si la session actuelle est ouverte ou non.|  
|[opérateur \(CDataSource\)&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|Retourne une référence à l'objet contenu `CDataSource`.|  
|[opérateur CDataSource\*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|Retourne un pointeur à l'objet contenu `CDataSource`.|  
|[opérateur CSession&&](../../data/oledb/cdataconnection-operator-csession-amp.md)|Retourne une référence à l'objet contenu `CSession`.|  
|[opérateur CSession\*](../../data/oledb/cdataconnection-operator-csession-star.md)|Retourne un pointeur à l'objet contenu `CSession`.|  
  
## Notes  
 `CDataConnection` est une classe utile pour créer des clients parce qu'elle encapsule les objets nécessaires \(source de données et session\) et une partie du travail à effectuer lors de la connexion à une source de données  
  
 Sans `CDataConnection`, vous devez créer un objet `CDataSource`, appeler la méthode [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md), puis créer une instance d'un objet [CSession](../../data/oledb/csession-class.md), appeler la méthode [Ouvrir](../../data/oledb/csession-open.md), puis créer un objet [CCommand](../../data/oledb/ccommand-class.md) et appeler sa méthode **Ouvrir**\*.  
  
 Avec `CDataConnection`, vous ne devez créer qu'un objet de connexion, le transmettre une chaîne d'initialisation, puis utiliser cette connexion pour ouvrir des commandes.  Si vous envisagez d'utiliser votre connexion à plusieurs reprises, il est judicieux de maintenir la connexion ouverte, et `CDataConnection` fournit un moyen commode à cet effet.  
  
> [!NOTE]
>  Si vous créez une application de base de données qui doit gérer plusieurs sessions, vous devez utiliser [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
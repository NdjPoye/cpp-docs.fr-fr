---
title: "Sources de donn&#233;es et sessions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "connexions (C++), source de données"
  - "sources de données (C++), OLE DB"
  - "OLE DB (modèles du consommateur) (C++), sources de données"
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Sources de donn&#233;es et sessions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'illustration suivante montre les classes qui prennent en charge la connexion et l'accès à une source de données.  Chaque classe est basée sur une implémentation de composant OLE DB standard.  
  
 ![Classes de source de données et de session](../../data/oledb/media/vcdatasourcesessionclasses.png "vcDataSourceSessionClasses")  
Classes de source de données et de session  
  
 Les classes sont les suivantes :  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md) Cette classe instancie l'objet source de données, qui crée et gère une connexion à une source de données par l'intermédiaire d'un fournisseur OLE DB.  La source de données accepte des informations telles que l'adresse de la source de données et les informations d'authentification sous la forme d'une chaîne de connexion.  
  
     Il convient également de noter que la classe d'assistance [CEnumerator](../../data/oledb/cenumerator-class.md) est souvent utilisée avant l'établissement de toute connexion visant à obtenir une liste de fournisseurs disponibles inscrits sur le système.  Cela vous permet de sélectionner un fournisseur en tant que source de données.  Par exemple, la boîte de dialogue **Propriétés des liaisons de données** utilise cette classe pour compléter la liste des fournisseurs sous l'onglet **Fournisseurs**.  C'est l'équivalent de la fonction **SQLBrowseConnect** ou **SQLDriverConnect**.  
  
-   [CSession](../../data/oledb/csession-class.md) Cette classe instancie l'objet session, qui représente une session d'accès unique à la source de données.  Cependant, vous pouvez créer plusieurs sessions sur une source de données.  Pour chaque session, vous pouvez créer des jeux de lignes, des commandes et d'autres objets d'accès aux données à partir de la source de données.  La session gère les transactions.  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)
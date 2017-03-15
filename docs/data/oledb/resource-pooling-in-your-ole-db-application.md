---
title: "Regroupement des ressources dans votre application OLE&#160;DB | Microsoft Docs"
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
  - "fournisseurs OLE DB, regroupement des ressources"
  - "services OLE DB, regroupement des ressources"
  - "OLE DB, regroupement des ressources"
  - "regroupement de ressources (OLE DB), services"
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Regroupement des ressources dans votre application OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour tirer parti du regroupement dans votre application, vous devez vous assurer que les services OLE DB sont appelés en obtenant la source de données par l'intermédiaire de **IDataInitialize** ou de **IDBPromptInitialize**.  Si vous utilisez directement `CoCreateInstance` pour appeler le fournisseur sur la base du CLSID du fournisseur, aucun service OLE DB n'est appelé.  
  
 Les services OLE DB conservent des regroupements de sources de données connectées tant qu'une référence à **IDataInitialize** ou à **IDBPromptInitialize** subsistera, ou tant qu'une connexion sera utilisée.  Les regroupements sont aussi automatiquement maintenus dans un environnement COM\+ 1.0 Services ou Services IIS \(Internet Information Services\).  Si vous voulez que votre application tire parti du regroupement en dehors d'un environnement COM\+ 1.0 Services ou IIS, vous devez conserver une référence à **IDataInitialize** ou à **IDBPromptInitialize**, ou maintenir une connexion au moins.  Pour faire en sorte que le regroupement ne soit pas détruit lorsque l'application libère la dernière connexion, conservez la référence ou maintenez la connexion pendant toute la durée de vie de votre application.  
  
 Les services OLE DB identifient le groupement à partir duquel la connexion est extraite au moment de l'appel de `Initialize`.  Une fois la connexion extraite d'un groupement, elle ne peut pas être déplacée vers un autre groupement.  Par conséquent, évitez d'exécuter dans votre application des actions qui risquent de modifier les informations d'initialisation, comme l'appel de `UnInitialize` ou l'appel de `QueryInterface` pour une interface spécifique à un fournisseur avant l'appel de `Initialize`.  Les connexions établies à l'aide d'une valeur d'invite autre que **DBPROMPT\_NOPROMPT** ne sont pas regroupées.  Cependant, la chaîne d'initialisation récupérée à partir d'une connexion établie par l'intermédiaire d'une invite peut servir à l'établissement de connexions regroupées supplémentaires avec la même source de données.  
  
 Certains fournisseurs doivent établir une connexion distincte pour chaque session.  Ces connexions supplémentaires doivent être répertoriées séparément dans la transaction distribuée, s'il en existe une.  Les services OLE DB mettent en cache et réutilisent une seule session par source de données, mais si l'application demande plus d'une session à la fois à partir d'une source de données, le fournisseur peut finir par effectuer des connexions supplémentaires et procéder à de nouvelles inscriptions de transactions qui ne sont pas regroupées.  Il est en fait plus efficace de créer une source de données séparée pour chaque session dans un environnement regroupé que de créer plusieurs sessions à partir d'une seule source de données.  
  
 Enfin, dans la mesure où ADO tire automatiquement partie des services OLE DB, vous pouvez utiliser ADO pour établir des connexions, le regroupement et l'inscription se produisant alors automatiquement.  
  
## Voir aussi  
 [Services et regroupement des ressources OLE DB](../../data/oledb/ole-db-resource-pooling-and-services.md)
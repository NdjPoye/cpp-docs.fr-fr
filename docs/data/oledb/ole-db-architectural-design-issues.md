---
title: "Questions relatives &#224; la conception architecturale d&#39;OLE&#160;DB | Microsoft Docs"
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
  - "OLE DB, considérations sur la conception d'applications"
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Questions relatives &#224; la conception architecturale d&#39;OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avant de commencer votre application OLE DB, vous devez répondre aux questions suivantes :  
  
 **Quelle implémentation de programmation utiliserez\-vous pour écrire votre application OLE DB ?**  
 Microsoft offre plusieurs bibliothèques permettant d'atteindre ce but : une bibliothèque de modèles OLE DB, des attributs OLE DB et des interfaces OLE DB brutes du Kit de développement OLE DB SDK.  De plus, des Assistants vous aident à écrire votre programme.  Ces implémentations sont décrites dans [Modèles, attributs et autres implémentations OLE DB](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md).  
  
 **Avez\-vous besoin d'écrire votre propre fournisseur ?**  
 La plupart des développeurs n'ont pas besoin d'écrire leur propre fournisseur.  Microsoft propose plusieurs fournisseurs.  Chaque fois que vous créez une connexion de données, par exemple lorsque vous ajoutez un consommateur à votre projet en utilisant l'Assistant Consommateur OLE DB ATL, la boîte de dialogue **Propriétés des liaisons de données** répertorie tous les fournisseurs disponibles inscrits sur votre système.  Si l'un de ces fournisseurs est approprié pour votre propre magasin de données et votre application d'accès aux données, le plus simple est de l'utiliser.  Cependant, si votre magasin de données ne rentre pas dans l'une de ces catégories, vous devez créer votre propre fournisseur.  Pour plus d'informations sur la création de fournisseurs, consultez [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
 **De quel niveau de prise en charge avez\-vous besoin pour votre consommateur ?**  
 Certains consommateurs peuvent être très élémentaires, et d'autres très élaborés.  La fonctionnalité des objets OLE DB est spécifiée par les propriétés.  Quand vous utilisez l'Assistant Consommateur OLE DB ATL pour créer un consommateur ou l'Assistant Fournisseur de base de données pour créer un fournisseur, celui\-ci définit les propriétés appropriées de l'objet afin de vous offrir un jeu standard de fonctionnalités.  Cependant, si les classes de consommateur ou de fournisseur générées par l'Assistant ne prennent pas en charge toutes les tâches que vous souhaitez qu'elles exécutent, vous devez vous référer aux interfaces de ces classes dans la [bibliothèque des modèles OLE DB](../../data/oledb/ole-db-templates.md).  Ces interfaces englobent les interfaces OLE DB brutes, offrant une implémentation supplémentaire afin de faciliter leur utilisation.  
  
 Par exemple, si vous souhaitez mettre à jour les données d'un ensemble de lignes, mais que vous avez oublié de le spécifier au moment de créer le consommateur par le biais de l'Assistant, vous pouvez spécifier la fonctionnalité ultérieurement en définissant les propriétés **DBPROP\_IRowsetChange** et **DBPROP\_UPDATABILITY** sur l'objet de commande.  Ensuite, une fois l'ensemble de lignes créé, il est doté de l'interface `IRowsetChange`.  
  
 **Do you have older code using another data access technology \(ADO, ODBC, or DAO\)?**  
 Compte tenu des combinaisons possibles des technologies \(comme l'utilisation de composants ADO avec des composants OLE DB et la migration du code ODBC vers OLE DB\), le traitement de toutes les situations possibles sortirait du cadre de la documentation Visual C\+\+.  Cependant, de nombreux articles couvrant différents scénarios sont disponibles sur les sites Web Microsoft suivants :  
  
-   [Microsoft Help and Support](http://go.microsoft.com/fwlink/?LinkId=148218)  
  
-   [Microsoft Data Access Technical Articles Overview](http://go.microsoft.com/fwlink/?LinkId=148217)  
  
-   [Visual Studio Solution Center](http://go.microsoft.com/fwlink/?LinkId=148215)  
  
-   [Search Microsoft.com](http://search.microsoft.com/)  
  
 Quand vous effectuez une recherche, entrez une combinaison de mots clés qui correspond le mieux à votre scénario ; par exemple : si vous avez utilisé des objets ADO avec un fournisseur OLE DB, essayez une recherche de type booléen avec **ADO AND "OLE DB"**.  If you wanted to migrate older DAO code to ODBC, select "all words" and specify strings such as **migrating DAO**.  
  
## Voir aussi  
 [Programmation OLE DB](../../data/oledb/ole-db-programming.md)   
 [Vue d'ensemble de la programmation OLE DB](../../data/oledb/ole-db-programming-overview.md)
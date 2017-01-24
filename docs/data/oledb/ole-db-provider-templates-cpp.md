---
title: "Mod&#232;les du fournisseur OLE&#160;DB (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bases de données (C++), modèles OLE DB"
  - "OLE DB (modèles du fournisseur) (C++), à propose des modèles du fournisseur OLE DB"
  - "OLE DB (fournisseurs) (C++), à propos des fournisseurs"
  - "modèles (C++), OLE DB"
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mod&#232;les du fournisseur OLE&#160;DB (C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB est un composant important de la stratégie d'accès universel aux données \(UDA, Universal Data Access\) élaborée par Microsoft.  L'architecture OLE DB permet un accès performant aux données à partir de n'importe quelle source de données.  Les données présentées sous forme de tableau sont accessibles au moyen d'OLE DB, qu'elles proviennent ou non d'une base de données.  Cette souplesse d'utilisation offre une formidable marge de manœuvre.  
  
 Comme expliqué dans [Fournisseurs et consommateurs OLE DB](../../data/oledb/ole-db-consumers-and-providers.md), la technologie OLE DB repose sur le concept de consommateur et de fournisseur.  Le consommateur présente des requêtes de données ; le fournisseur retourne des données sous forme de tableau au consommateur.  Du point de vue de la programmation, l'implication la plus importante de ce modèle est que le fournisseur doit implémenter tout appel pouvant émaner du consommateur.  
  
## Qu'est\-ce qu'un fournisseur ?  
 Un fournisseur OLE DB est un ensemble d'objets COM qui prennent en charge les appels d'interface provenant d'un objet consommateur, en transférant les données sous forme de tableau à partir d'une source durable \(appelée magasin de données\) vers le consommateur.  
  
 Les fournisseurs peuvent être de type simple ou complexe.  Le fournisseur peut prendre en charge un minimum de fonctionnalités ou servir de fournisseur complet de qualité production en implémentant un plus grand nombre d'interfaces.  Un fournisseur peut retourner une table, permettre au client de déterminer le format de cette table et effectuer des opérations sur ses données.  
  
 Chaque fournisseur implémente un jeu standard d'objets COM pour traiter les requêtes émanant du client, la finalité standard étant que tout consommateur OLE DB peut accéder aux données à partir de n'importe quel fournisseur, quel que soit le langage utilisé \(C\+\+ et Basic, par exemple\).  
  
 Chaque objet COM contient plusieurs interfaces, dont certaines sont obligatoires et d'autres facultatives.  En implémentant les interfaces obligatoires, un fournisseur garantit un niveau minimum de fonctionnalités \(appelé conformité\) que tout client doit pouvoir utiliser.  Un fournisseur peut implémenter des interfaces facultatives pour mettre en œuvre des fonctionnalités supplémentaires.  Ces interfaces sont décrites en détail dans [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md).  Le client doit toujours appeler `QueryInterface` pour déterminer si un fournisseur prend en charge une interface particulière.  
  
## Prise en charge du niveau de la spécification OLE DB  
 Les modèles du fournisseur OLE DB prennent en charge la spécification OLE DB version 2.7.  Grâce aux modèles du fournisseur OLE DB, vous pouvez implémenter un fournisseur conforme au niveau 0.  L'exemple de fournisseur utilise les modèles pour implémenter un serveur de commandes \(MS\-DOS\) non SQL qui exécute la commande DOS DIR pour interroger le système de fichiers.  L'exemple de fournisseur retourne les informations relatives au répertoire dans un ensemble de lignes, qui correspond au mécanisme OLE DB standard pour le retour de données sous forme de tableau.  
  
 Le type de fournisseur le plus simple pris en charge par les modèles OLE DB est un fournisseur en lecture seule sans commande.  Les fournisseurs dotés de commandes sont également pris en charge, tout comme les fonctions de création de signet et d'accès en lecture\/écriture.  Vous pouvez implémenter un fournisseur accessible en lecture\/écriture en écrivant du code supplémentaire.  Les transactions et les ensembles de lignes dynamiques ne sont pas pris en charge par la version actuelle, mais vous pouvez les ajouter le cas échéant.  
  
## Quand avez\-vous besoin de créer un fournisseur OLE DB ?  
 Vous n'avez pas toujours besoin de créer votre propre fournisseur ; Microsoft propose plusieurs fournisseurs standard préconditionnés via la boîte de dialogue **Propriétés des liaisons de données** dans Visual C\+\+.  La création d'un fournisseur OLE DB trouve sa raison principale dans l'exploitation de la stratégie d'accès universel aux données UDA.  Voici quelques avantages que vous pouvez en tirer :  
  
-   Accès aux données par l'intermédiaire de n'importe quel langage tel que C\+\+, Basic et Visual Basic Scripting Edition.  Cette approche permet à différents programmeurs de votre organisation d'accéder aux mêmes données de0 façon identique, quel que soit le langage utilisé.  
  
-   Exposition de vos données à d'autres sources de données telles que SQL Server, Excel et Access.  Cette approche peut se révéler très utile si vous souhaitez transférer des données entre différents formats.  
  
-   Participation à des opérations croisées entre des sources de données hétérogènes.  Il peut s'agir d'une méthode de stockage de données \(« warehousing »\) très performante.  L'utilisation de fournisseurs OLE DB permet de conserver les données dans leur format natif et de pouvoir quand même y accéder par une opération simple.  
  
-   Ajout de fonctionnalités supplémentaires à vos données, comme le traitement des requêtes.  
  
-   Amélioration des performances d'accès aux données en contrôlant leur mode de manipulation.  
  
-   Amélioration de la robustesse.  Si vous avez un format de données propriétaire auquel un seul programmeur peut accéder, vous êtes en danger.  L'utilisation de fournisseurs OLE DB permet d'ouvrir ce format propriétaire à tous vos programmeurs.  
  
## Fournisseurs en lecture seule et actualisables  
 Les fournisseurs varient sensiblement au niveau de la complexité et des fonctionnalités.  Il est pratique de diviser les fournisseurs en deux catégories, les fournisseurs en lecture seule et les fournisseurs actualisables :  
  
-   Visual C\+\+ 6.0 prenait en charge uniquement les fournisseurs en lecture seule.  La rubrique [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md) explique comment créer un fournisseur en lecture seule.  
  
-   Visual C\+\+ .NET prend en charge les fournisseurs actualisables, qui peuvent mettre à jour \(modifier\) le magasin de données.  Pour plus d'informations sur les fournisseurs actualisables, consultez [Création d'un fournisseur actualisable](../../data/oledb/creating-an-updatable-provider.md) ; l'exemple [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f) illustre l'utilisation d'un fournisseur actualisable.  
  
 Pour plus d'informations, consultez :  
  
-   [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)  
  
-   [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)  
  
-   [Programmation OLE DB](../../data/oledb/ole-db-programming.md)  
  
## Voir aussi  
 [Accès aux données](../Topic/Data%20Access%20in%20Visual%20C++.md)   
 [Documentation du Kit de développement logiciel \(SDK\) OLE DB](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [Guide de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx)
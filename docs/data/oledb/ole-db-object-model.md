---
title: "Mod&#232;le objet OLE&#160;DB | Microsoft Docs"
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
  - "OLE DB, modèle objet"
  - "jeux de lignes, modèle d'objet OLE DB"
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mod&#232;le objet OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le modèle objet OLE DB englobe les objets ou composants suivants.  Les quatre premiers objets ou composants répertoriés \(sources de données, sessions, commandes et jeux de lignes\) vous permettent de vous connecter à une source de données et de la visualiser.  Le reste, à commencer par les accesseurs, concerne l'utilisation des données une fois qu'elles sont affichées.  
  
## Sources de données  
 Les objets source de données vous permettent de vous connecter à une source de données telle qu'un fichier ou un SGBD.  Un objet source de données crée et gère la connexion, et contient des informations relatives aux autorisations et aux authentifications \(nom de connexion et mot de passe, par exemple\).  Un objet source de données peut créer une ou plusieurs sessions.  
  
## Sessions  
 Une session gère une interaction particulière avec la source de données pour rechercher et récupérer des données.  Chaque session correspond à une transaction unique.  Une transaction est une unité de travail indivisible définie selon le test des propriétés ACID.  Pour une définition du test ACID, consultez [Transactions](#vcconoledbcomponents_transactions).  
  
 Les sessions exécutent des tâches importantes telles que l'ouverture de jeux de lignes et le retour de l'objet source de données l'ayant créé.  Les sessions peuvent également retourner des métadonnées ou des informations concernant la source de données elle\-même \(des informations sur les tables, par exemple\).  
  
 Une session peut créer une ou plusieurs commandes.  
  
## Commandes  
 Les commandes exécutent une commande texte, telle qu'une instruction SQL.  Si la commande texte spécifie un jeu de lignes, par exemple une instruction SQL **SELECT**, la commande crée le jeu de lignes.  
  
 Une commande est tout simplement un conteneur d'une commande texte, qui est une chaîne \(une instruction SQL, par exemple\) passée par un consommateur à un objet source de données pour être exécutée par le magasin de données sous\-jacent du fournisseur.  En principe, la commande texte est une instruction SQL **SELECT** \(auquel cas, dans la mesure où SQL **SELECT** spécifie un jeu de lignes, la commande crée automatiquement un jeu de lignes\).  
  
## Jeux de lignes  
 Les jeux de lignes exposent les données sous la forme d'un tableau.  Un index est un cas spécial de jeu de lignes.  Vous pouvez créer des jeux de lignes à partir de la session ou de la commande.  
  
### Jeux de lignes du schéma  
 Les schémas contiennent des métadonnées \(informations structurelles\) concernant une base de données.  Les jeux de lignes du schéma sont des jeux de lignes qui contiennent des informations relatives au schéma.  Certains fournisseurs OLE DB pour SGBD prennent en charge des objets jeu de lignes du schéma.  Pour plus d'informations sur les jeux de lignes du schéma, consultez [Récupération de métadonnées à l'aide de jeux de lignes du schéma](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) et [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
### Objets de vue  
 Un objet de vue définit un sous\-ensemble de lignes et de colonnes d'un jeu de lignes.  Il ne contient pas de données propres.  Les objets de vue ne peuvent pas combiner des données provenant de plusieurs jeux de lignes.  
  
## Accesseurs  
 Seule la technologie OLE DB utilise le concept d'accesseur.  Un accesseur décrit comment les données sont stockées dans un consommateur.  Il contient un jeu de liaisons \(appelé mappage de colonnes\) entre les champs du jeu de lignes \(colonnes\) et les données membres que vous déclarez dans le consommateur.  
  
##  <a name="vcconoledbcomponents_transactions"></a> Transactions  
 Les objets de transaction sont utilisés lors de la validation ou de l'abandon de transactions imbriquées à un niveau autre que le niveau le plus bas.  Une transaction est une unité de travail indivisible définie selon le test des propriétés ACID.  Les propriétés ACID sont les suivantes :  
  
-   Atomicité : suppose qu'une transaction ne peut pas être divisée en petites unités de travail.  
  
-   Simultanéité : plusieurs transactions peuvent être exécutées en même temps.  
  
-   Isolement : une transaction a une connaissance limitée des modifications effectuées par une autre transaction.  
  
-   Durabilité : la transaction rend permanentes les modifications apportées au système.  
  
## Énumérateurs  
 Les énumérateurs recherchent les sources de données disponibles et d'autres énumérateurs.  Les consommateurs qui ne sont pas personnalisés pour une source de données particulière utilisent des énumérateurs pour rechercher une source de données à utiliser.  
  
 Un énumérateur racine, fourni avec le Kit de développement Microsoft Data Access SDK, parcourt la base de registres à la recherche de sources de données et autres énumérateurs.  D'autres énumérateurs parcourent la base de registres ou effectuent une recherche d'une manière spécifique à un fournisseur.  
  
## Erreurs  
 Toute interface sur un objet OLE DB peut générer des erreurs.  Les erreurs contiennent des informations supplémentaires sur une erreur, y compris un objet erreur personnalisé facultatif.  Ces informations sont contenues dans un HRESULT.  
  
## Notifications  
 Les notifications sont utilisées par des groupes de consommateurs coopératifs partageant un jeu de lignes \(« partageant » signifie en l'occurrence que les consommateurs sont censés travailler dans la même transaction\).  Les notifications permettent aux consommateurs coopératifs partageant un jeu de lignes d'êtres informées sur les actions opérées par leurs pairs sur le jeu de lignes.  
  
## Voir aussi  
 [Programmation OLE DB](../../data/oledb/ole-db-programming.md)   
 [Vue d'ensemble de la programmation OLE DB](../../data/oledb/ole-db-programming-overview.md)
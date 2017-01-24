---
title: "Mod&#232;les du consommateur OLE&#160;DB (C++) | Microsoft Docs"
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
  - "bases de données [C++], modèles OLE DB"
  - "OLE DB, consommateurs [C++], accès aux données"
  - "OLE DB, modèles de consommateur [C++]"
  - "bases de données [C++], consommateurs"
ms.assetid: d3e42612-0bc0-4d65-9c32-0e8a7b219e82
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mod&#232;les du consommateur OLE&#160;DB (C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les modèles de consommateurs OLE DB prennent ne charge la spécification OLE DB version 2.6. \(Les modèles de consommateurs OLE DB sont testés pour OLE DB 2.6, mais il ne prennent pas en charge chacune des interfaces de la spécification.\) Les modèles de consommateurs réduisent la quantité de code que vous devez écrire pour implémenter un consommateur OLE DB. Les modèles fournissent :  
  
-   Un accès facile aux fonctionnalités d’OLE DB, et une intégration facile à ATL et à MFC.  
  
-   Un modèle de liaison facile pour les paramètres et les colonnes des bases de données.  
  
-   Des types de données C\/C\+\+ natifs pour la programmation OLE DB.  
  
 Pour utiliser les modèles OLE DB, vous devez bien connaître les modèles C\+\+, COM et les interfaces OLE DB. Si vous ne connaissez pas bien OLE DB, consultez [Informations de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms718124.aspx).  
  
 Les modèles OLE DB prennent en charge le modèle objet OLE DB existant, au lieu d’ajouter un nouveau modèle objet. Les classes de la couche la plus élevée des modèles de consommateur OLE DB figurent en parallèle des composants définis dans la spécification OLE DB. La conception des modèles de consommateur OLE DB comprend des fonctionnalités avancées, comme les accesseurs multiples sur un ensemble de lignes. L’utilisation de modèles et de l’héritage multiple rend la bibliothèque souple et d’une taille réduite.  
  
## Comment les consommateurs OLE DB accèdent aux données  
 Les consommateurs utilisent différentes sortes d’objets, qui sont décrits dans les rubriques suivantes :  
  
-   [Sources de données et sessions](../../data/oledb/data-sources-and-sessions.md)  
  
-   [Accesseurs et jeux de lignes](../../data/oledb/accessors-and-rowsets.md)  
  
-   [Commandes et tables](../../data/oledb/commands-and-tables.md)  
  
-   [Enregistrements utilisateur](../../data/oledb/user-records.md)  
  
 Avant que le consommateur fasse quoi que ce soit, vous devez d’abord sélectionner un fournisseur OLE DB approprié au type de la base de données à laquelle vous devez accéder \(par exemple SQL, Oracle, ODBC et MSDS\). Pour cela, vous utilisez généralement un énumérateur \(consultez [CEnumerator](../../data/oledb/cenumerator-class.md) comme mentionné dans [Sources de données et sessions](../../data/oledb/data-sources-and-sessions.md)\).  
  
 L’[objet de source de données](../../data/oledb/data-sources-and-sessions.md) fournit les informations de connexion nécessaires pour se connecter à la source de données que vous avez sélectionnée. L’objet source de données contient aussi des informations d’authentification \(comme les noms et mots de passe de connexion\), qui sont utilisées pour donner aux utilisateurs l’autorisation d’accéder à la source de données. L’objet source de données établit une connexion à la base de données, puis crée un ou plusieurs objets session. Chaque [objet de session](../../data/oledb/data-sources-and-sessions.md) gère ses propres interactions avec la base de données \(effectuer des requêtes sur les données et les récupérer\) et effectue ces transactions indépendamment des autres sessions existantes.  
  
 La session crée des objets ensemble de lignes et commande. L’[objet de commande](../../data/oledb/commands-and-tables.md) permet aux utilisateurs d’interagir avec la base de données, par exemple en utilisant des commandes SQL. L’[objet d’ensemble de lignes \(rowset\)](../../data/oledb/accessors-and-rowsets.md) est un ensemble de données à travers lequel vous pouvez naviguer et où vous pouvez [mettre à jour, supprimer et insérer des lignes](../../data/oledb/updating-rowsets.md).  
  
 Un consommateur OLE DB lie les colonnes des tables de la base de données à des variables locales. Pour cela, il utilise un [accesseur](../../data/oledb/accessors-and-rowsets.md), qui contient un mappage indiquant comment les données sont stockées dans le consommateur. Le mappage est constitué d’un ensemble de liaisons entre les colonnes des tables et les mémoires tampons \(variables\) locales de l’application consommatrice.  
  
 Un concept important pour travailler avec des consommateurs est que vous déclarez deux classes dans un consommateur : la [classe command \(ou table\)](../../data/oledb/commands-and-tables.md) et la [classe enregistrement utilisateur](../../data/oledb/user-records.md). Vous accédez à l’ensemble de lignes via la classe command \(ou table\), qui hérite à la fois d’une classe accessor et d’une classe rowset. La classe d’enregistrement utilisateur \(user record\) contient le mappage des liaisons de lignes décrit précédemment.  
  
 Pour plus d’informations, consultez les rubriques suivantes :  
  
-   [Création d’un consommateur OLE DB](../../data/oledb/creating-an-ole-db-consumer.md)  
  
-   [Scénarios courants de consommateur OLE DB \(exemples\)](../../data/oledb/working-with-ole-db-consumer-templates.md)  
  
## Voir aussi  
 [Programmation OLE DB](../../data/oledb/ole-db-programming.md)   
 [Accès aux données](../Topic/Data%20Access%20in%20Visual%20C++.md)   
 [Documentation du Kit de développement logiciel \(SDK\) OLE DB](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [Informations de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx)
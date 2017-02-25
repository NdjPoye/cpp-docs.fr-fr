---
title: "Vue d&#39;ensemble de la programmation OLE&#160;DB | Microsoft Docs"
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
  - "OLE DB, à propos d'OLE DB"
  - "Universal Data Access"
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Vue d&#39;ensemble de la programmation OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Qu'est\-ce que OLE DB et qu'est\-ce qui la distingue des autres technologies de bases de données ?  OLE DB est une technologie de bases de données performante qui s'appuie sur l'architecture COM élaborée par Microsoft.  Ce qui caractérise OLE DB par rapport aux autres technologies de bases de données Microsoft, c'est la façon dont elle assure un accès universel aux données \(UDA, Universal Data Access\).  
  
## UDA \(Universal Data Access\)  
 UDA désigne une méthode uniforme d'accès à des données stockées sous différentes formes.  Dans le cas type d'une entreprise, une grande quantité d'informations est stockée en dehors des bases de données de l'entreprise.  Ces informations résident dans des systèmes de fichiers \(FAT ou NTFS, par exemple\), des fichiers séquentiels indexés, des bases de données personnelles \(telles qu'Access\), des tableurs \(tels qu'Excel\), des applications de planification de projets \(telles que Project\) et des applications de messagerie électronique \(telles qu'Outlook\).  
  
 L'accès à ces données par l'intermédiaire des diverses applications associées constitue un véritable goulet d'étranglement au niveau du workflow, ou à tout le moins un désagrément.  La plupart des entreprises se retrouvent dans cette situation, et traitent le problème en regroupant les informations dans un système de gestion de base de données \(SGBD\).  Cependant, une telle initiative est coûteuse, longue et, dans la plupart des cas, peu pratique.  
  
 La solution de remplacement consiste à développer une solution de type UDA \(Universal Data Access\).  OLE DB et ADO permettent de bénéficier de la fonctionnalité UDA.  De ces deux technologies, OLE DB est la plus exigeante en termes de performances et celle dont l'utilisation est préconisée avec les applications Visual C\+\+.  
  
 UDA offre deux fonctionnalités : la première est la « requête distribuée », ou accès uniforme à un large éventail de sources de données \(distribuées\) et la seconde est la possibilité de rendre des sources de données non SGBD accessibles aux applications de bases de données.  
  
-   Requête distribuée  
  
     Cette notion correspond à la possibilité d'accéder uniformément aux données de multiples sources de données \(distribuées\).  Les sources de données peuvent être de même type, par exemple deux bases de données Access distinctes, ou de types différents, comme une base de données SQL Server et une base de données Access.  « Uniformément » signifie que vous exécutez de manière significative la même requête sur toutes les sources de données.  
  
-   Accès non SGBD  
  
     La possibilité de rendre des sources de données non SGBD accessibles aux applications de bases de données.  Les exemples de sources de données SGBD incluent IMS, DB2, Oracle, SQL Server, Access et Paradox.  Les exemples de sources de données non SGBD incluent les informations contenues dans les systèmes de fichiers, la messagerie électronique, les tableurs et les outils de gestion de projet.  
  
 Prenons l'exemple d'un scénario dans lequel un service commercial a besoin de retrouver à un certain emplacement tous les messages électroniques envoyés par les clients au cours d'une semaine particulière.  Cette requête peut exiger une recherche dans un fichier de boîte aux lettres d'une application de messagerie et une recherche dans une table de clients Access pour spécifier les noms de ces clients.  Si Access est une application SGBD, Outlook ne l'est pas.  
  
 OLE DB permet de développer des applications pouvant accéder à diverses sources de données, qu'elles soient de type SGBD ou non.  OLE DB rend possible l'accès universel grâce à l'utilisation d'interfaces COM qui prennent en charge la fonctionnalité SGBD appropriée pour une source de données particulière.  COM réduit la duplication inutile des services et l'interopérabilité maximalisée non seulement entre les sources de données, mais également entre d'autres applications.  
  
## Avantages de COM  
 C'est à ce niveau qu'intervient l'architecture COM.  OLE DB repose sur un ensemble d'interfaces COM.  En accédant aux données par l'intermédiaire d'un ensemble uniforme d'interfaces, vous pouvez organiser une base de données en une matrice de composants coopératifs.  
  
 S'appuyant sur la spécification COM, OLE DB définit une collection extensible et actualisable d'interfaces qui mettent en œuvre et encapsulent des portions cohérentes et réutilisables de fonctions SGBD.  Ces interfaces définissent les limites des composants SGBD, tels que les conteneurs de lignes, les processeurs de requêtes et les coordinateurs de transactions, qui permettent un accès transactionnel uniforme à diverses sources d'informations.  
  
 En principe, les applications OLE DB sont écrites en tant que DLL, mais leur implémentation COM l'emporte sur les inconvénients des DLL \(comme les problèmes liés à l'attribution de noms et aux versions\) grâce à l'utilisation d'un code par composants.  Dans OLE DB, vous appelez des interfaces ou accédez à d'autres composants à l'aide de leur identifiant GUID \(Globally Unique Identifiers\).  
  
 Enfin, l'architecture COM assure le suivi de l'utilisation des composants par le biais d'un décompte de références.  Quand vous appelez une méthode sur une interface, le décompte de références est incrémenté ; quand la méthode retourne, le décompte de références est décrémenté.  Quand le décompte est égal à zéro, le composant auquel appartient la méthode est libéré.  
  
## Voir aussi  
 [Programmation OLE DB](../../data/oledb/ole-db-programming.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [modèles OLE DB](../../data/oledb/ole-db-templates.md)
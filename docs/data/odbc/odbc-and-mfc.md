---
title: ODBC et MFC | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 48dd657d4cf1b315b29fda881b949dea29204f24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-and-mfc"></a>ODBC et MFC
> [!NOTE]
>  Pour utiliser les classes de base de données MFC, vous devez disposer du pilote ODBC approprié pour votre source de données. Dernière Microsoft ODBC driver pour SQL Server est [Microsoft ODBC Driver 13 for SQL Server](https://www.microsoft.com/en-us/download/details.aspx?id=50420). La plupart des fournisseurs de base de données fournissent un pilote ODBC pour Windows. 
  
 Cette rubrique présente les principaux concepts de classes de base de données ODBC de la bibliothèque Microsoft Foundation Classes (MFC) et fournit une vue d’ensemble de la façon dont les classes fonctionnent ensemble. Pour plus d’informations sur ODBC et MFC, consultez les rubriques suivantes :  
  
-   [Connexion à une source de données](connecting-to-a-data-source.md)  
  
-   [Sélection et manipulation d’enregistrements](selecting-and-manipulating-records.md)  
  
-   [Affichage et manipulation de données dans un formulaire](displaying-and-manipulating-data-in-a-form.md)  
  
-   [Utilisation des Documents et vues](working-with-documents-and-views.md)  
  
-   [Accès à ODBC et SQL](access-to-odbc-and-sql.md)  
  
-   [Informations supplémentaires sur les classes ODBC MFC](further-reading-about-the-mfc-odbc-classes.md)  
  
 Les classes de base de données MFC basées sur ODBC sont conçues pour fournir l’accès aux bases de données pour laquelle un pilote ODBC est disponible. Les classes utilisent ODBC, votre application peut accéder aux données dans de nombreux formats de données différents et différentes configurations local/distant. Vous n’avez pas à écrire de code spécial pour gérer les systèmes de gestion de base de données différente (SGBD). Tant que vos utilisateurs ont un pilote ODBC approprié pour les données qu'auxquelles ils veulent accéder, ils peuvent utiliser votre programme pour manipuler des données dans les tables qui y sont stockées.  
  
## <a name="see-also"></a>Voir aussi  
 [ODBC (Open Database Connectivity)](open-database-connectivity-odbc.md)
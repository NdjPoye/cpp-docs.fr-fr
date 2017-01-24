---
title: "SQL | Microsoft Docs"
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
  - "classes de base de données (C++), instructions SQL"
  - "ODBC (C++), SQL (implémentation)"
  - "SQL (C++)"
  - "SQL (C++), ODBC"
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le langage SQL \(Structured Query Language\) permet de communiquer avec une base de données, afin de définir, interroger, modifier et contrôler les données.  À l'aide de la syntaxe SQL, vous pouvez construire une instruction qui extrait les enregistrements obéissant aux critères que vous définissez.  
  
> [!NOTE]
>  Ces informations s'appliquent aux classes ODBC MFC.  Si vous utilisez les classes DAO MFC, consultez la rubrique « Comparison of Microsoft Jet Database Engine SQL and ANSI SQL » dans l'aide de DAO.  
  
 Les instructions SQL commencent par un mot réservé, tel que **CREATE** ou **SELECT.** SQL est un langage extrêmement puissant, car une seule instruction peut affecter une table complète.  
  
 Il existe de nombreuses versions du langage SQL, chacune ayant été développée pour un SGBD particulier.  Les classes MFC de base de données admettent un ensemble d'instructions SQL qui correspond au projet de spécification SQL \(1991\) élaboré par X\/Open et le CAE \(Common Applications Environment\) de SQL Access Group.  Pour plus d'informations sur la syntaxe de ces instructions, consultez l'annexe C du guide *ODBC SDK* *Programmer's Reference* sur le CD\-ROM MSDN Library.  
  
 Cette rubrique explique :  
  
-   [les relations entre ODBC et SQL](#_core_open_database_connectivity_.28.odbc.29) ;  
  
-   [les mots clés SQL utilisés le plus couramment par les classes de base de données](#_core_the_database_classes) ;  
  
-   [l'utilisation de SQL par les classes de base de données](#_core_how_the_database_classes_use_sql).  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> ODBC \(Open Database Connectivity\)  
 Les classes de base de données sont implémentées avec ODBC, qui utilise une interface au niveau de l'appel plutôt qu'au niveau de l'incorporation de commandes SQL dans le code.  ODBC utilise SQL pour communiquer avec une [source de données](../../data/odbc/data-source-odbc.md) via les pilotes ODBC.  Ces pilotes interprètent le langage SQL et le traduisent, si nécessaire, pour l'adapter à un format spécifique de base de données comme Microsoft Access.  Pour plus d'informations sur l'utilisation de SQL par ODBC, consultez [ODBC](../../data/odbc/odbc-basics.md) et le guide ODBC SDK *Programmer's Reference* sur le CD\-ROM MSDN Library.  
  
##  <a name="_core_the_database_classes"></a> Classes de base de données  
 Les classes de base de données sont conçues pour vous permettre de manipuler et de mettre à jour les données d'une [source de données](../../data/odbc/data-source-odbc.md) existante.  L'[Assistant Création d'applications MFC](../../mfc/reference/database-support-mfc-application-wizard.md), l'[Assistant Consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) \(accessible via **Add Class**\) et les classes de base de données construisent automatiquement la plupart des instructions SQL.  
  
 Les classes de base de données utilisent une partie de SQL, connue sous le nom de langage de manipulation de données \(DML, Data Manipulation Language\).  Ces commandes permettent d'utiliser tout ou partie d'une source de données, ainsi que d'ajouter, modifier et supprimer des enregistrements.  Le tableau suivant répertorie les mots clés SQL les plus courants et leur utilisation par les classes de base de données.  
  
### Quelques mots clés SQL courants  
  
|Mot clé SQL|Utilisé par les Assistants et les classes de base de données pour :|  
|-----------------|-------------------------------------------------------------------------|  
|**SELECT**|Identifier les tables et les colonnes de la source de données à utiliser.|  
|**WHERE**|Appliquer un filtre qui restreint la sélection.|  
|**ORDER BY**|Appliquer un ordre de tri au recordset.|  
|**INSÉRER**|Ajouter de nouveaux enregistrements à un recordset.|  
|**DELETE**|Supprimer des enregistrements d'un recordset.|  
|**UPDATE**|Modifier les champs d'un enregistrement.|  
  
 En outre, les classes de base de données acceptent les instructions **CALL** ODBC, que vous pouvez utiliser pour appeler une requête prédéfinie \(ou procédure stockée\) sur certaines sources de données.  Le pilote de base de données ODBC interprète les instructions et les remplace par les commandes appropriées de chaque SGBD.  
  
> [!NOTE]
>  Certains SGBD ne prennent pas en charge les instructions **CALL**.  
  
 Si les classes ne parviennent pas à identifier une instruction fournie par l'utilisateur dans `CRecordset::Open`, celle\-ci est interprétée en tant que nom de table.  
  
 Pour plus d'informations sur la construction des instructions SQL par l'infrastructure, consultez [Recordsets : sélection d'enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) et [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
 Les bases de données SQL utilisent des types de données similaires à ceux des langages C et C\+\+.  Pour plus d'informations sur ces ressemblances, consultez [SQL : types de données SQL et C\+\+ \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
 Vous trouverez de plus amples informations sur SQL \(y compris une liste des instructions SQL prises en charge, les types de données, la grammaire SQL principale ainsi qu'une bibliographie\) dans le guide *ODBC SDK* *Programmer's Reference* sur le CD\-ROM MSDN Library.  
  
##  <a name="_core_how_the_database_classes_use_sql"></a> Utilisation de SQL par les classes de base de données  
 Les recordsets issus des classes de base de données utilisent ODBC pour communiquer avec une source de données ; ODBC récupère les enregistrements de la source de données par l'envoi d'instructions SQL.  Cette rubrique explique les relations entre les classes de base de données et SQL.  
  
 Un recordset crée une instruction SQL en ajoutant les différents éléments de l'instruction SQL dans une chaîne `CString`.  La chaîne est construite sous forme d'une instruction **SELECT**, laquelle retourne un ensemble d'enregistrements.  
  
 Lorsque le recordset appelle ODBC pour envoyer une instruction SQL à la source de données, le gestionnaire de pilotes ODBC passe l'instruction au pilote ODBC, puis celui\-ci l'adresse au SGBD sous\-jacent.  Le SGBD retourne comme résultat un ensemble d'enregistrements et le pilote ODBC retourne les enregistrements à l'application.  Les classes de base de données permettent à vos programmes d'accéder au jeu de résultats dans une classe C\+\+ de type sécurisé, dérivée de `CRecordset`.  
  
 Les rubriques suivantes proposent des informations complémentaires sur l'utilisation de SQL par les classes de base de données :  
  
-   [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)  
  
-   [SQL : types de données SQL et C\+\+ \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL : appels SQL directs \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)
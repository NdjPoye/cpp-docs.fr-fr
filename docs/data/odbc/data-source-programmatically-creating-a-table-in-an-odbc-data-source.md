---
title: "Source de donn&#233;es&#160;: cr&#233;ation d&#39;une table par programme dans une source de donn&#233;es ODBC | Microsoft Docs"
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
  - "sources de données ODBC, créer des tables dans"
  - "créer des tables ODBC par programme (C++)"
  - "tables (C++)"
  - "tables (C++), créer par programmation"
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Source de donn&#233;es&#160;: cr&#233;ation d&#39;une table par programme dans une source de donn&#233;es ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit comment créer une table pour votre source de données, en utilisant la fonction membre `ExecuteSQL` de la classe `CDatabase`, en passant à la fonction une chaîne comprenant une instruction SQL **CREATE TABLE**.  
  
 Pour plus d'informations générales sur les sources de données ODBC dans MFC, consultez [Source de données \(ODBC\)](../../data/odbc/data-source-odbc.md).  La rubrique [Source de données : configuration d'une source de données ODBC par programmation](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) décrit la création de sources de données.  
  
 Lorsque vous avez établi la source de données, vous pouvez facilement créer des tables à l'aide de la fonction membre `ExecuteSQL` et de l'instruction SQL **CREATE TABLE**.  Par exemple, si vous possédez un objet `CDatabase` intitulé `myDB`, vous pouvez utiliser le code MFC suivant pour créer une table :  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 Cet exemple de code crée une table appelée "OFFICES" dans la connexion de source de données Microsoft Access gérée par `myDB` ; la table comprend deux champs "OfficeID" et "OfficeName".  
  
> [!NOTE]
>  Les types de champs spécifiés dans l'instruction SQL **CREATE TABLE** peuvent varier selon le pilote ODBC que vous utilisez.  Grâce au programme Microsoft Query \(livré avec Visual C\+\+ 1.5\), vous pouvez connaître les types de champs disponibles pour une source de données.  Dans Microsoft Query, cliquez sur **Fichier**, puis sur **Table\_Definition**, sélectionnez une table à partir d'une source de données et regardez le type affiché dans la zone de liste déroulante **Type**.  La syntaxe SQL sert également à créer des index.  
  
## Voir aussi  
 [Source de données \(ODBC\)](../../data/odbc/data-source-odbc.md)
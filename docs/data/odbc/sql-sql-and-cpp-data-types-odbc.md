---
title: "SQL&#160;: types de donn&#233;es SQL et C++ (ODBC) | Microsoft Docs"
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
  - "types de données (C++), SQL et C++"
  - "SQL (C++), différences par rapport aux types de données C++"
  - "types de données SQL (C++)"
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL&#160;: types de donn&#233;es SQL et C++ (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Ces informations s'appliquent aux classes ODBC MFC.  Si vous utilisez les classes DAO MFC, consultez la rubrique « Comparison of Microsoft Jet Database Engine SQL and ANSI SQL » dans l'aide de DAO.  
  
 Le tableau suivant mappe les types de données SQL ANSI vers les types de données C\+\+.  Ce tableau constitue une information sur le langage C fournie en complément de l'annexe D du guide *ODBC SDK* *Programmer's Reference* sur le CD\-ROM MSDN Library.  Les Assistants gèrent automatiquement la plupart des mappages de types de données.  Si vous n'utilisez pas un Assistant, vous pouvez vous appuyer sur ces informations de mappage pour écrire manuellement le code relatif à l'échange des champs.  
  
### Mappage des types de données SQL ANSI vers des types de données C\+\+  
  
|Type de données SQL ANSI|Type de données C\+\+|  
|------------------------------|---------------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**INTEGER**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**BINARY**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**TIME**|**CTime, CString**|  
|**TIMESTAMP**|**CTime, CString**|  
  
 1.  Les types ANSI **DECIMAL** et **NUMERIC** sont mappés vers `CString`, car **SQL\_C\_CHAR** est le type de transfert ODBC par défaut.  
  
 2.  Les données de type Char sont tronquées par défaut si elles dépassent 255 caractères lorsqu'elles sont mappées vers le type de données `CString`.  Il est possible d'augmenter la longueur de troncation en définissant explicitement l'argument `nMaxLength` de `RFX_Text`  
  
 3.  Les données binaires sont tronquées par défaut si elles dépassent 255 caractères lorsqu'elles sont mappées vers le type de données `CByteArray`.  Il est possible d'augmenter la longueur de troncation en définissant explicitement l'argument `nMaxLength` de `RFX_Binary`  
  
 Si vous n'utilisez pas la bibliothèque de curseurs ODBC, il se peut que vous soyez confronté à un problème lors de la mise à jour de deux champs \(ou plus\) de longueur variable à l'aide du pilote ODBC de Microsoft SQL Server et des classes de base de données ODBC MFC.  Les types ODBC **SQL\_LONGVARCHAR** et **SQL\_LONGVARBINARY** sont mappés vers les types SQL Server text et image.  Une exception `CDBException` est levée si vous mettez à jour deux champs \(ou plus\) de longueur variable lors d'un même appel de `CRecordset::Update`.  En conséquence, ne mettez pas simultanément à jour plusieurs colonnes de type long avec `CRecordset::Update`.  En revanche, plusieurs colonnes de type long peuvent être mises à jour simultanément avec l'API ODBC **SQLPutData**.  Vous pouvez également utiliser la bibliothèque de curseurs ODBC, mais cette utilisation est déconseillée pour les pilotes, comme le pilote SQL Server, qui prennent en charge les curseurs et pour lesquels la bibliothèque de curseurs n'offre aucune utilité.  
  
 Si vous utilisez la bibliothèque de curseurs ODBC avec les classes de base de données ODBC MFC et le pilote ODBC de Microsoft SQL Server, une commande **ASSERT** peut s'accompagner d'une exception `CDBException` si l'appel de `CRecordset::Update` fait suite à celui de `CRecordset::Requery`.  Aussi, appelez de préférence `CRecordset::Close` et `CRecordset::Open` plutôt que `CRecordset::Requery`.  Une autre solution consiste à ne pas utiliser la bibliothèque de curseurs ODBC, car SQL Server et le pilote ODBC de SQL Server offrent une prise en charge native pour les curseurs en mode natif, et la bibliothèque de curseurs ODBC n'est donc pas nécessaire.  
  
## Voir aussi  
 [SQL](../../data/odbc/sql.md)   
 [SQL : appels SQL directs \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
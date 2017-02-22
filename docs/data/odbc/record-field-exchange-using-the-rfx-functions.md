---
title: "Record Field Exchange&#160;: utilisation des fonctions RFX | Microsoft Docs"
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
  - "types de données (C++), échange de champs d'enregistrements ODBC"
  - "DoFieldExchange (méthode), et fonctions RFX"
  - "appels de fonction, RFX (fonctions)"
  - "ODBC (C++), types de données"
  - "ODBC (C++), RFX"
  - "RFX (ODBC) (C++), types de données"
  - "RFX (ODBC) (C++), syntaxe et paramètres de la fonction"
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Record Field Exchange&#160;: utilisation des fonctions RFX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment utiliser les appels de fonctions RFX qui constituent le corps de votre substitution de `DoFieldExchange`.  
  
> [!NOTE]
>  Cette rubrique s'applique aux classes dérivées de [CRecordset](../../mfc/reference/crecordset-class.md) dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, le mécanisme RFX en bloc \(Bulk RFX\) est implémenté.  RFX en bloc est similaire à RFX.  Pour plus d'informations sur les différences, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Les fonctions globales RFX échangent les données entre les colonnes de la source de données et les membres de données de type champ du recordset.  Vous écrivez les appels de fonction RFX dans la fonction membre [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) de votre recordset.  Cette rubrique décrit brièvement les fonctions et indique les types de données disponibles pour chaque fonction RFX.  La [Note technique 43](../../mfc/tn043-rfx-routines.md) explique comment écrire ses propres fonctions RFX pour des types de données additionnels.  
  
##  <a name="_core_rfx_function_syntax"></a> Syntaxe des fonctions RFX  
 Chaque fonction RFX nécessite trois paramètres \(certaines admettent deux autres paramètres supplémentaires facultatifs\) :  
  
-   Un pointeur vers un objet [CFieldExchange](../../mfc/reference/cfieldexchange-class.md).  Vous transmettez simplement le pointeur `pFX` passé à `DoFieldExchange`.  
  
-   Nom de la colonne tel qu'il apparaît dans la source de données.  
  
-   Nom du membre de données de champ ou de paramètre correspondant dans la classe de recordset.  
  
-   \(Facultatif\) Dans certaines fonctions, la longueur maximale de la chaîne ou du tableau à transférer.  Par défaut, cette longueur est de 255 octets, mais il se peut que vous souhaitiez la modifier.  La taille maximale est fonction de la taille maximale d'un objet `CString` — **INT\_MAX** \(2 147 483 647\) octets — mais vous vous heurterez probablement aux limites du pilote avant d'atteindre cette taille.  
  
-   \(Facultatif\) Dans la fonction `RFX_Text`, vous utilisez quelquefois un cinquième paramètre pour définir le type de données d'une colonne.  
  
 Pour plus d'informations, consultez les fonctions RFX sous [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) dans *Class Library Reference*.  Pour obtenir un exemple d'utilisation particulière des paramètres, consultez [Recordset : calculs de totaux et autres résultats de regroupement \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).  
  
##  <a name="_core_rfx_data_types"></a> Types de données RFX  
 La bibliothèque de classes contient des fonctions RFX pour transférer plusieurs types de données différents entre la source de données et les recordsets.  La liste ci\-après résume les fonctions RFX par type de données.  Lorsque vous devez écrire vos propres appels de fonction RFX, choisissez dans cette liste de fonctions selon le type de données.  
  
|Fonction|Type de données|  
|--------------|---------------------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BYTE**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**double**|  
|`RFX_Single`|**float**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**long**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  
 Pour plus d'informations, consultez la documentation relative aux fonctions RFX sous [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) dans *Class Library Reference*.  Pour plus d'informations sur la correspondance entre les types de données C\+\+ et les types de données SQL, consultez le tableau « Mappage des types de données SQL ANSI et C\+\+ » dans [SQL : types de données SQL et C\+\+ \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
## Voir aussi  
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [Record Field Exchange : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)
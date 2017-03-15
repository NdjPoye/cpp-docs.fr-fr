---
title: "Recordset&#160;: calculs de totaux et autres r&#233;sultats de regroupement (ODBC) | Microsoft Docs"
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
  - "ODBC (recordsets), récupérer des valeurs agrégées SQL"
  - "recordsets, récupérer des valeurs agrégées SQL"
  - "récupérer les valeurs agrégées SQL à partir de recordsets"
  - "SQL (valeurs d'agrégation)"
  - "SQL (valeurs d'agrégation), récupérer à partir de recordsets"
  - "projets SQL Server, récupérer les valeurs agrégées de recordsets"
  - "SQL, récupérer les valeurs agrégées de recordsets"
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset&#160;: calculs de totaux et autres r&#233;sultats de regroupement (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 La présente rubrique explique comment utiliser des résultats de regroupement à l'aide des mots clés [SQL](../../data/odbc/sql.md) suivants :  
  
-   **SUM** Calcule le total des valeurs d'une colonne dont les données sont de type numérique.  
  
-   **MIN** Extrait la plus petite valeur d'une colonne dont les données sont de type numérique.  
  
-   **MAX** Extrait la plus grande valeur d'une colonne dont les données sont de type numérique.  
  
-   **AVG** Calcule la valeur moyenne de toutes valeurs d'une colonne dont les données sont de type numérique.  
  
-   **COUNT** Comptabilise le nombre d'enregistrements d'une colonne, quel que soit le type de données.  
  
 Ces fonctions SQL permettent d'obtenir des informations statistiques sur les enregistrements d'une source de données sans avoir à extraire les enregistrements.  Le recordset créé se compose généralement d'un seul enregistrement \(si les colonnes sont des regroupements\) contenant une valeur. \(Il peut y avoir plus d'un enregistrement si vous avez utilisé une clause **GROUP BY**.\) Cette valeur est le résultat du calcul ou de l'extraction effectué\(e\) par la fonction SQL.  
  
> [!TIP]
>  Pour ajouter une clause SQL **GROUP BY** \(et éventuellement une clause **HAVING**\) à l'instruction SQL, ajoutez\-la à la fin de **m\_strFilter**.  Par exemple :  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 Vous pouvez limiter le nombre d'enregistrements utilisés pour obtenir des résultats de regroupement en filtrant ou en triant les colonnes.  
  
> [!CAUTION]
>  Certains opérateurs de regroupement retournent un type de données différent de la colonne ou des colonnes à partir de laquelle ou desquelles ils sont regroupés.  
  
-   **SUM** et **AVG** peuvent retourner le type de données immédiatement supérieur \(par exemple, un appel avec `int` retourne **LONG** ou **double**\).  
  
-   **COUNT** retourne généralement **LONG** indépendamment du type de la colonne cible.  
  
-   **MAX** et **MIN** retournent le même type de données que celui des colonnes utilisées pour le calcul.  
  
     Par exemple, l'Assistant  **Ajouter une classe** crée `long` `m_lSales` pour recevoir la colonne Sales, mais vous devrez le remplacer par le membre de donnée `double m_dblSumSales` pour recevoir le résultat du regroupement.  Voir l'exemple suivant.  
  
#### Pour obtenir le résultat de regroupement d'un recordset  
  
1.  Créez un recordset comme décrit dans [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) et contenant la\(les\) colonne\(s\) à partir de laquelle \(desquelles\) vous voulez obtenir les résultats de regroupement.  
  
2.  Modifiez la fonction [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) du recordset.  Remplacez la chaîne représentant le nom de colonne \(deuxième argument des appels de fonction [RFX](../../data/odbc/record-field-exchange-using-rfx.md)\) par celle représentant la fonction de regroupement de la colonne.  Par exemple, remplacez :  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     par  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  Ouvrez le recordset.  Le résultat de l'opération de regroupement se trouve dans `m_dblSumSales`.  
  
> [!NOTE]
>  L'Assistant assigne effectivement les noms des membres de données sans préfixes Hongrois.  Par exemple, l'Assistant génère `m_Sales` pour la colonne Sales, plutôt que le nom `m_lSales` utilisé préalablement aux fins d'illustration.  
  
 Si vous utilisez une classe [CRecordView](../../mfc/reference/crecordview-class.md) pour visualiser les données, vous devez modifier l'appel de fonction DDX pour afficher la nouvelle valeur du membre de données. Dans le cas présent, il faudrait changer  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 À :  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : sélection d'enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
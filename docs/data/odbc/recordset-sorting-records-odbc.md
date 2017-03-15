---
title: "Recordset&#160;: tri d&#39;enregistrements (ODBC) | Microsoft Docs"
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
  - "ODBC (recordsets), trier"
  - "recordsets, trier"
  - "trier les données, données du recordset"
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset&#160;: tri d&#39;enregistrements (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Cette explique comment trier le recordset.  Vous pouvez définir une ou plusieurs colonnes à partir desquelles effectuer le tri, et choisir un ordre de tri ascendant ou descendant \(`ASC` ou **DESC**, `ASC` étant la valeur par défaut\) pour chaque colonne.  Par exemple, si vous indiquez deux colonnes, les enregistrements sont d'abord triés sur la première colonne, puis sur la seconde.  La clause SQL **ORDER BY** définit une instruction de tri.  Quand l'infrastructure ajoute la clause **ORDER BY** à la requête SQL du recordset, la clause contrôle le tri de la sélection.  
  
 Vous devez établir un ordre de tri du recordset après avoir construit l'objet mais avant d'appeler sa fonction membre **Open** \(ou la fonction membre **Requery** d'un objet recordset existant dont la fonction membre **Open** a été appelée préalablement\).  
  
#### Pour définir l'ordre de tri d'un objet recordset  
  
1.  Construisez un nouvel objet recordset \(ou préparez l'appel de **Requery** dans le cas d'un objet existant\).  
  
2.  Définissez la valeur du membre de données [m\_strSort](../Topic/CRecordset::m_strSort.md) de l'objet.  
  
     L'instruction de tri est une chaîne terminée par le caractère NULL.  Elle contient le contenu de la clause SQL **ORDER BY** mais non le mot clé **ORDER BY**.  Par exemple, utilisez  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  Définissez les autres options nécessaires, comme le filtre, le mode de verrouillage ou les paramètres.  
  
4.  Appelez la fonction **Open** pour un nouvel objet \(ou **Requery** pour un objet existant\).  
  
 Les enregistrements sélectionnés sont triés conformément à l'instruction définie.  Par exemple, pour trier un ensemble d'étudiants par ordre décroissant sur le nom, puis sur le prénom, écrivez le code suivant :  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 Le recordset contient tous les étudiants, triés par ordre décroissant \(de Z à A\) sur le nom, puis sur le prénom.  
  
> [!NOTE]
>  Si vous choisissez de substituer la chaîne SQL par défaut du recordset en passant votre propre chaîne SQL à la fonction **Open**, ne définissez pas de tri lorsque votre chaîne personnalisée contient une clause **ORDER BY**.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Recordset : filtrage d'enregistrements \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)
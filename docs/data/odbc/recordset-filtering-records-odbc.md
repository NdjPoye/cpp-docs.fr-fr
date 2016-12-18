---
title: "Recordset&#160;: filtrage d&#39;enregistrements (ODBC) | Microsoft Docs"
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
  - "données (MFC), filtrer"
  - "filtrer les recordsets"
  - "filtres (C++), recordset (objet)"
  - "ODBC (recordsets C++), filtrer les enregistrements"
  - "recordsets (C++), filtrer"
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: filtrage d&#39;enregistrements (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 La présente rubrique explique comment filtrer un recordset afin qu'il ne sélectionne qu'un sous\-ensemble particulier au sein des enregistrements disponibles.  Par exemple, vous pourriez vouloir ne sélectionner que les sections classe d'un cours donné, comme MATH101.  Un filtre est une condition de recherche définie par le contenu d'une clause SQL **WHERE**.  Quand l'infrastructure l'ajoute à l'instruction SQL du recordset, la clause **WHERE** limite la sélection.  
  
 Vous devez établir un filtre d'objet recordset après avoir construit l'objet mais avant d'appeler sa fonction membre **Open** \(ou la fonction membre **Requery** d'un objet recordset existant dont la fonction membre **Open** a été appelée préalablement\).  
  
#### Pour définir le filtre d'un objet recordset  
  
1.  Construisez un nouvel objet recordset \(ou préparez l'appel de **Requery** dans le cas d'un objet existant\).  
  
2.  Définissez la valeur du membre de données [m\_strFilter](../Topic/CRecordset::m_strFilter.md) de l'objet.  
  
     Le filtre est une chaîne terminée par le caractère NULL qui contient le contenu de la clause SQL **WHERE** mais pas le mot clé **WHERE**.  Par exemple, utilisez  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  La chaîne « MATH101 » est encadrée ci\-dessus par des guillemets simples.  Dans la spécification SQL ODBC, les guillemets simples sont utilisés pour identifier les littéraux de chaîne.  Vérifiez dans la documentation de votre pilote ODBC les utilisations requises par le SGBD en matière de guillemets.  Ce point de syntaxe est également traité plus loin dans la présente rubrique.  
  
3.  Définissez les autres options nécessaires, comme l'ordre de tri, le mode de verrouillage ou les paramètres.  Il peut être très utile de définir un paramètre.  Pour plus d'informations sur le paramétrage d'un filtre, consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
4.  Appelez la fonction **Open** pour le nouvel objet \(ou **Requery** pour un objet préalablement ouvert\).  
  
> [!TIP]
>  L'utilisation de paramètres dans votre filtre constitue pratiquement la méthode la plus efficace pour récupérer des enregistrements.  
  
> [!TIP]
>  Les filtres de recordsets sont utiles pour [joindre](../../data/odbc/recordset-performing-a-join-odbc.md) des tables ou utiliser des [paramètres](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) liés aux informations fournies ou calculées à l'exécution.  
  
 Le recordset ne sélectionne que les enregistrements qui satisfont aux critères de recherche que vous avez définis.  Par exemple, pour définir le filtre sur les cours évoqué ci\-dessus \(en supposant que la variable `strCourseID` ait pour valeur « MATH101 »\), écrivez le code suivant :  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 Le recordset contient tous les enregistrements des sections classe de MATH101.  
  
 Notez comment la chaîne de filtre a été définie dans l'exemple ci\-dessus, à l'aide d'une variable chaîne.  Il s'agit là d'une utilisation classique.  Mais supposez que vous souhaitiez spécifier la valeur littérale 100 pour l'ID de cours.  Le code suivant indique comment définir correctement la chaîne de filtrage avec une valeur littérale :  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 Notez l'utilisation des guillemets simples ; si vous définissez directement la chaîne du filtre, celle\-ci **n'est pas** :  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 L'utilisation des guillemets ci\-dessus est conforme à la spécification ODBC, mais certains SGBD requièrent d'autres types de guillemets.  Pour plus d'informations, consultez [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
> [!NOTE]
>  Si vous choisissez de substituer la chaîne SQL par défaut du recordset en passant votre propre chaîne SQL à la fonction **Open**, vous ne devez pas définir de filtre lorsque votre chaîne personnalisée contient une clause **WHERE**.  Pour plus d'informations sur la substitution de l'instruction SQL par défaut, consultez [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : tri d'enregistrements \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [Recordset : sélection d'enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [Recordset : verrouillage d'enregistrements \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)
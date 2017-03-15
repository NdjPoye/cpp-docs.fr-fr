---
title: "Recordset&#160;: ajout, modification et suppression d&#39;enregistrements (ODBC) | Microsoft Docs"
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
  - "AddNew (méthode)"
  - "données dans les recordsets (C++)"
  - "ODBC (recordsets C++), ajouter des enregistrements"
  - "ODBC (recordsets C++), supprimer des enregistrements"
  - "ODBC (recordsets C++), modifier les enregistrements"
  - "modification d'enregistrements (C++)"
  - "modification d'enregistrements (C++), dans les recordsets"
  - "enregistrements (C++), ajouter"
  - "enregistrements (C++), supprimer"
  - "enregistrements (C++), modifier"
  - "enregistrements (C++), mettre à jour"
  - "recordsets (C++), ajouter des enregistrements"
  - "recordsets (C++), supprimer des enregistrements"
  - "recordsets (C++), modifier les enregistrements"
  - "recordsets (C++), mettre à jour"
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Recordset&#160;: ajout, modification et suppression d&#39;enregistrements (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
> [!NOTE]
>  Vous pouvez désormais ajouter des enregistrements en bloc de façon plus efficace.  Pour plus d'informations, consultez [Recordset : ajout global d'enregistrements \(ODBC\)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Les instantanés et les feuilles de réponse dynamiques permettent d'ajouter, de modifier ou de supprimer des enregistrements.  Cette rubrique explique :  
  
-   [comment déterminer si un recordset est modifiable](#_core_determining_whether_your_recordset_is_updatable) ;  
  
-   [comment ajouter un nouvel enregistrement](#_core_adding_a_record_to_a_recordset) ;  
  
-   [comment modifier un enregistrement](#_core_editing_a_record_in_a_recordset) ;  
  
-   [comment supprimer un enregistrement](#_core_deleting_a_record_from_a_recordset).  
  
 Pour plus d'informations sur la façon dont les modifications sont effectuées et sur la façon dont elles apparaissent aux autres utilisateurs, consultez [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  En principe, lorsque vous ajoutez, modifiez ou supprimez un enregistrement, le recordset modifie aussitôt la source de données.  Vous pouvez à la place traiter en lot, sous forme de transactions, les mises à jour associées.  Si une transaction est en cours, la modification ne devient effective que lorsque la transaction a été validée.  Cela permet de reprendre ou d'annuler les modifications effectuées.  Pour plus d'informations sur les transactions, consultez [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
 Le tableau suivant résume les options disponibles pour les recordsets, accompagnées des différentes caractéristiques de mise à jour.  
  
### Options lecture\/modification d'un recordset  
  
|Type|Lire|Modification d'un enregistrement|Suppression d'un enregistrement|Ajout d'un enregistrement|  
|----------|----------|--------------------------------------|-------------------------------------|-------------------------------|  
|En lecture seule|Y|N|N|N|  
|Ajout seul|Y|N|N|Y|  
|Pleinement modifiable|Y|Y|Y|Y|  
  
##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> Détermination du caractère modifiable du recordset  
 Un objet recordset est modifiable si la source de données l'est et que le recordset a été ouvert comme étant modifiable.  Son caractère modifiable dépend également de l'instruction SQL que vous utilisez, des capacités du pilote ODBC et de l'éventuel chargement en mémoire de la bibliothèque de curseurs ODBC.  Il est impossible de modifier une source de données ou un recordset en lecture seule.  
  
#### Pour déterminer si le recordset est modifiable  
  
1.  Appelez la fonction membre [CanUpdate](../Topic/CRecordset::CanUpdate.md) de l'objet recordset.  
  
     `CanUpdate` retourne une valeur différente de zéro si le recordset est modifiable.  
  
 Par défaut, les recordsets sont entièrement modifiables \(vous pouvez effectuer les opérations `AddNew`, **Edit** et **Delete**\).  Mais vous pouvez également utiliser l'option [appendOnly](../Topic/CRecordset::Open.md) pour ouvrir des recordsets modifiables.  Un recordset ouvert de cette façon ne permet que l'ajout de nouveaux enregistrements à l'aide de `AddNew`.  Il n'est pas possible de modifier ou de supprimer des enregistrements existants.  Vous pouvez tester si un recordset est uniquement ouvert pour l'ajout en appelant la fonction membre [CanAppend](../Topic/CRecordset::CanAppend.md).  `CanAppend` retourne une valeur différente de zéro si le recordset est complètement modifiable ou ouvert uniquement pour l'ajout.  
  
 Le code suivant illustre comment vous pouvez utiliser `CanUpdate` pour un objet recordset appelé `rsStudentSet` :  
  
```  
if( !rsStudentSet.Open( ) )  
    return FALSE;  
if( !rsStudentSet.CanUpdate( ) )  
{  
    AfxMessageBox( "Unable to update the Student recordset." );  
    return;  
}  
```  
  
> [!CAUTION]
>  Lorsque vous vous préparez à modifier un recordset en appelant **Update**, prenez soin que le recordset comporte toutes les colonnes composant la clé primaire de la table \(ou toutes les colonnes d'un index unique de la table\).  Dans certains cas, l'infrastructure ne peut utiliser que les colonnes sélectionnées dans le recordset pour identifier l'enregistrement de la table à modifier.  Sans toutes les colonnes nécessaires, plusieurs enregistrements risquent d'être modifiés dans la table et l'intégrité référentielle de celle\-ci peut s'en trouver altérée.  Dans ce cas, l'infrastructure lève une exception quand vous appelez **Update**.  
  
##  <a name="_core_adding_a_record_to_a_recordset"></a> Ajout d'un enregistrement à un recordset  
 Vous pouvez ajouter de nouveaux enregistrements à un recordset si sa fonction membre [CanAppend](../Topic/CRecordset::CanAppend.md) retourne une valeur différente de zéro.  
  
#### Pour ajouter un nouvel enregistrement à un recordset  
  
1.  Assurez\-vous que des enregistrements peuvent être ajoutés au recordset.  
  
2.  Appelez la fonction membre [AddNew](../Topic/CRecordset::AddNew.md) de l'objet recordset.  
  
     `AddNew` prépare le recordset de telle sorte qu'il fasse office de tampon d'édition.  Tous les membres de données de type champ sont définis avec la valeur particulière Null et marqués comme non modifiés, de sorte que seules les valeurs modifiées \(« dirty »\) sont écrites dans la source de données lorsque vous appelez [Update](../Topic/CRecordset::Update.md).  
  
3.  Définissez les valeurs des membres de données de type champ du nouvel enregistrement.  
  
     Assignez des valeurs aux membres de données de type champ.  Ceux auxquels ne sont pas assignées de valeurs ne sont pas écrits dans la source de données.  
  
4.  Appelez la fonction membre **Update** de l'objet recordset.  
  
     **Update** termine l'ajout en écrivant le nouvel enregistrement dans la source de données.  Pour plus d'informations sur ce qui se passe en cas d'échec de l'appel de la fonction **Update**, consultez [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Pour plus d'informations sur le fonctionnement de l'ajout d'enregistrements et sur la disponibilité des enregistrements ajoutés dans le recordset, consultez [Recordset : fonctionnement d'AddNew, Edit et Delete \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md).  
  
 L'exemple suivant illustre l'ajout d'un nouvel enregistrement :  
  
```  
if( !rsStudent.Open( ) )  
    return FALSE;  
if( !rsStudent.CanAppend( ) )  
    return FALSE;                      // no field values were set  
rsStudent.AddNew( );  
rsStudent.m_strName = strName;  
rsStudent.m_strCity = strCity;  
rsStudent.m_strStreet = strStreet;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not added; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  Pour annuler un appel de `AddNew` ou **Edit**, effectuez simplement un nouvel appel de `AddNew` ou **Edit** ou appelez **Move** avec le paramètre **AFX\_MOVE\_REFRESH**.  Les membres de données sont réinitialisés à leurs valeurs précédentes et vous demeurez en mode **Edit** ou **Add**.  
  
##  <a name="_core_editing_a_record_in_a_recordset"></a> Modification d'un enregistrement dans un recordset  
 Vous pouvez modifier des enregistrements existants si la fonction membre [CanUpdate](../Topic/CRecordset::CanUpdate.md) de votre recordset retourne une valeur différente de zéro.  
  
#### Pour modifier un enregistrement existant dans un recordset  
  
1.  Assurez\-vous que le recordset est modifiable.  
  
2.  Accédez à l'enregistrement à mettre à jour.  
  
3.  Appelez la fonction membre [Edit](../Topic/CRecordset::Edit.md) de l'objet recordset.  
  
     **Edit** prépare le recordset de telle sorte qu'il fasse office de tampon d'édition.  Tous les membres de données de type champ sont marqués de sorte que le recordset peut savoir, par la suite, s'ils ont été modifiés.  Les nouvelles valeurs des membres de données de type champ modifiés sont écrites dans la source de données quand vous appelez [Update](../Topic/CRecordset::Update.md).  
  
4.  Définissez les valeurs des membres de données de type champ du nouvel enregistrement.  
  
     Assignez des valeurs aux membres de données de type champ.  Les membres auxquels ne sont pas assignées de valeurs demeurent inchangés.  
  
5.  Appelez la fonction membre **Update** de l'objet recordset.  
  
     **Update** termine la modification en écrivant l'enregistrement modifié dans la source de données.  Pour plus d'informations sur ce qui se passe en cas d'échec de l'appel de la fonction **Update**, consultez [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Après que vous avez modifié un enregistrement, celui\-ci demeure l'enregistrement courant.  
  
 L'exemple suivant montre une opération **Edit**.  L'exemple présume que l'utilisateur a atteint l'enregistrement qu'il souhaite modifier.  
  
```  
rsStudent.Edit( );  
rsStudent.m_strStreet = strNewStreet;  
rsStudent.m_strCity = strNewCity;  
rsStudent.m_strState = strNewState;  
rsStudent.m_strPostalCode = strNewPostalCode;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not updated; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  Pour annuler un appel de `AddNew` ou **Edit**, effectuez simplement un nouvel appel de `AddNew` ou **Edit** ou appelez **Move** avec le paramètre **AFX\_MOVE\_REFRESH**.  Les membres de données sont réinitialisés à leurs valeurs précédentes et vous demeurez en mode **Edit** ou **Add**.  
  
##  <a name="_core_deleting_a_record_from_a_recordset"></a> Suppression d'un enregistrement du recordset  
 Vous pouvez supprimer des enregistrements si la fonction membre [CanUpdate](../Topic/CRecordset::CanUpdate.md) de votre recordset retourne une valeur différente de zéro.  
  
#### Pour supprimer un enregistrement  
  
1.  Assurez\-vous que le recordset est modifiable.  
  
2.  Accédez à l'enregistrement à mettre à jour.  
  
3.  Appelez la fonction membre [Delete](../Topic/CRecordset::Delete.md) de l'objet recordset.  
  
     **Delete** marque immédiatement l'enregistrement comme supprimé, à la fois dans le recordset et dans la source de données.  
  
     Contrairement à `AddNew` et **Edit**, **Delete** n'appelle pas la fonction **Update**.  
  
4.  Accédez par défilement à un autre enregistrement.  
  
    > [!NOTE]
    >  Lorsque vous vous déplacez dans un recordset, les enregistrements supprimés ne peuvent pas être ignorés.  Pour plus d'informations, consultez la fonction membre [IsDeleted](../Topic/CRecordset::IsDeleted.md).  
  
 L'exemple suivant montre une opération **Delete**.  L'exemple présume que l'utilisateur a atteint l'enregistrement qu'il souhaite supprimer.  Après l'appel de **Delete**, il est important de se déplacer jusqu'à un nouvel enregistrement.  
  
```  
rsStudent.Delete( );  
rsStudent.MoveNext( );  
```  
  
 Pour plus d'informations sur les conséquences des fonctions membres `AddNew`, **Edit** et **Delete**, consultez [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : verrouillage d'enregistrements \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)
---
title: "Transaction : Exécution d’une Transaction dans un Recordset (ODBC) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd412549c86c3ca8ddc004016183b64248bdf292
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Transaction : exécution d’une transaction dans un recordset (ODBC)
Cette rubrique explique comment exécuter une transaction dans un jeu d’enregistrements.  
  
> [!NOTE]
>  Un seul niveau de transactions est pris en charge ; Vous ne pouvez pas imbriquer des transactions.  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>Pour exécuter une transaction dans un jeu d’enregistrements  
  
1.  Appelez le `CDatabase` l’objet **BeginTrans** fonction membre.  
  
2.  Si vous n’avez pas implémenté l’extraction de lignes en bloc, appelez le **AddNew/mise à jour**, **modifier/mettre à jour**, et **supprimer** les fonctions membres d’un ou plusieurs objets de jeu d’enregistrements du même base de données aussi souvent que nécessaire. Pour plus d’informations, consultez [Recordset : ajout, modification et suppression d’enregistrements (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Si vous avez implémenté l’extraction de lignes en bloc, vous devez écrire vos propres fonctions pour mettre à jour la source de données.  
  
3.  Enfin, appelez le `CDatabase` l’objet **CommitTrans** fonction membre. Si une erreur se produit dans une des mises à jour ou si vous décidez d’annuler les modifications, appelez sa **restauration** fonction membre.  
  
 L’exemple suivant utilise deux jeux d’enregistrements à supprimer l’inscription d’un étudiant à partir d’une base de données d’inscription scolaire, suppression de l’étudiant de toutes les classes dans lesquelles l’étudiant est inscrit. Étant donné que la **supprimer** appels doivent réussir dans les deux jeux d’enregistrements, une transaction est requise. L’exemple suppose l’existence de `m_dbStudentReg`, une variable membre de type `CDatabase` déjà connectée à la source de données et les classes de jeu d’enregistrements `CEnrollmentSet` et `CStudentSet`. Le `strStudentID` variable contient une valeur obtenue à partir de l’utilisateur.  
  
```  
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )  
{  
    // remove student from all the classes  
    // the student is enrolled in  
  
    if ( !m_dbStudentReg.BeginTrans( ) )  
        return FALSE;  
  
    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);  
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    CStudentSet rsStudentSet(&m_dbStudentReg);  
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsStudentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    TRY  
    {  
        while ( !rsEnrollmentSet.IsEOF( ) )  
        {  
            rsEnrollmentSet.Delete( );  
            rsEnrollmentSet.MoveNext( );  
        }  
  
        // delete the student record  
        rsStudentSet.Delete( );  
  
        m_dbStudentReg.CommitTrans( );  
    }  
  
    CATCH_ALL(e)  
    {  
        m_dbStudentReg.Rollback( );  
        return FALSE;  
    }  
    END_CATCH_ALL  
  
    rsEnrollmentSet.Close( );  
    rsStudentSet.Close( );  
  
    return TRUE;  
  
}  
```  
  
> [!NOTE]
>  Appel de **BeginTrans** à nouveau sans appeler **CommitTrans** ou **restauration** est une erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [Transactions (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Transaction : Répercussions des Transactions sur les mises à jour (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase (classe)](../../mfc/reference/cdatabase-class.md)   
 [CRecordset, classe](../../mfc/reference/crecordset-class.md)
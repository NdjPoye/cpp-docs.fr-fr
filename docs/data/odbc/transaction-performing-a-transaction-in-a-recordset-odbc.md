---
title: "Transaction&#160;: ex&#233;cution d&#39;une transaction dans un recordset (ODBC) | Microsoft Docs"
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
  - "transactions, mettre à jour des recordsets"
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Transaction&#160;: ex&#233;cution d&#39;une transaction dans un recordset (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment exécuter une transaction dans un recordset.  
  
> [!NOTE]
>  Un seul niveau des transactions est pris en charge ; vous ne pouvez pas imbriquer les transactions.  
  
#### Pour exécuter une transaction dans un recordset  
  
1.  Appelez la fonction membre **BeginTrans** de l'objet `CDatabase`.  
  
2.  Si vous n'avez pas implémenté l'extraction de lignes en bloc, appelez aussi souvent que nécessaire les fonctions membres **AddNew\/Update**, **Edit\/Update** et **Delete** d'un ou de plusieurs objets recordset de la même base de données.  Pour plus d'informations, consultez [Recordset : ajout, modification et suppression d'enregistrements \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  Si vous avez implémenté l'extraction de lignes en bloc, vous devez écrire vos propres fonctions pour mettre à jour la source de données.  
  
3.  Enfin, appelez la fonction membre **CommitTrans** de l'objet `CDatabase`.  Si une erreur se produit pendant l'une des mises à jour ou que vous décidiez d'annuler les modifications, appelez la fonction membre **Rollback**.  
  
 L'exemple plus bas utilise deux recordsets pour supprimer l'inscription d'un étudiant d'une base de données gérant les inscriptions d'une école. L'étudiant est ainsi retiré de tous les cours auxquels il était inscrit.  Les appels **Delete** doivent réussir dans les deux recordsets, ce qui implique l'utilisation d'une transaction.  Cet exemple suppose l'existence de `m_dbStudentReg`, variable membre de type `CDatabase` déjà connectée à la source de données, et des classes de recordsets `CEnrollmentSet` et `CStudentSet`.  La variable `strStudentID` contient une valeur fournie par l'utilisateur.  
  
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
>  Le fait d'appeler une nouvelle fois **BeginTrans** sans appeler **CommitTrans** ou **Rollback** constitue une erreur.  
  
## Voir aussi  
 [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [Transaction : répercussions des transactions sur les mises à jour \(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)
---
title: "Recordset&#160;: d&#233;claration de la classe d&#39;une requ&#234;te pr&#233;d&#233;finie (ODBC) | Microsoft Docs"
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
  - "ODBC (recordsets), requêtes"
  - "requêtes prédéfinies et recordsets"
  - "recordsets, requêtes prédéfinies"
  - "recordsets, procédures stockées"
  - "procédures stockées, et recordsets"
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: d&#233;claration de la classe d&#39;une requ&#234;te pr&#233;d&#233;finie (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 La présente rubrique explique comment créer une classe de recordset pour une requête prédéfinie \(parfois appelée procédure stockée, comme dans Microsoft SQL Server\).  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si l'extraction de lignes en bloc est implémentée, le processus est très similaire.  Pour plus d'informations sur les différences entre les recordsets qui implémentent l'extraction de lignes en bloc et ceux qui ne le font pas, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Certains SGBD permettent de créer une requête prédéfinie et de l'appeler depuis un programme comme une fonction.  La requête a un nom, peut prendre des paramètres et peut retourner des enregistrements.  La procédure de la présente rubrique décrit comment appeler une requête prédéfinie qui retourne des enregistrements \(et accepte des paramètres\).  
  
 Les classes de base de données ne prennent pas en charge la mise à jour des requêtes prédéfinies.  La différence entre une requête prédéfinie instantané et une requête prédéfinie feuille de réponse dynamique ne concerne pas la possibilité d'être modifiée, mais le fait de savoir si les modifications effectuées par les autres utilisateurs \(ou les autres recordsets du programme\) sont visibles dans le recordset.  
  
> [!TIP]
>  Vous n'avez pas besoin d'un recordset pour appeler une requête prédéfinie qui ne retourne pas d'enregistrements.  Préparez l'instruction SQL comme décrit ci\-dessous, mais exécutez\-la en appelant la fonction membre [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) de `CDatabase`.  
  
 Vous pouvez créer une seule classe de recordset pour gérer l'appel d'une requête prédéfinie, mais une partie du travail vous incombe.  Les Assistants ne prennent pas en charge la création d'une classe adaptée spécifiquement à cette fin.  
  
#### Pour créer une classe et appeler une requête prédéfinie \(ou procédure stockée\)  
  
1.  Utilisez l'[Assistant Consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) à partir de l'Assistant **Ajouter une classe** afin de créer une classe de recordset pour la table contenant la plupart des colonnes retournées par la requête.  Vous prenez ainsi de l'avance.  
  
2.  Ajoutez manuellement les membres de données de type champ pour toutes les colonnes de toutes les tables que la requête retourne, mais que l'Assistant n'a pas créés automatiquement.  
  
     Par exemple, si la requête retourne trois colonnes provenant chacune de deux tables additionnelles, ajoutez six membres de données de type champ \(avec le type de données approprié\) à la classe.  
  
3.  Ajoutez manuellement les appels de fonction [RFX](../../data/odbc/record-field-exchange-rfx.md) dans la fonction membre [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) de la classe, l'un correspondant au type de données de chaque membre de données de type champ ajouté.  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  Vous devez connaître les types de données et l'ordre des colonnes retournés dans le jeu de résultats.  L'ordre des appels de fonction RFX dans `DoFieldExchange` doit correspondre à l'ordre des colonnes du jeu de résultats.  
  
4.  Ajoutez manuellement les initialisations des nouveaux membres de données de type champ dans le constructeur de la classe de recordset.  
  
     Vous devez aussi incrémenter la valeur d'initialisation du membre de données [m\_nFields](../Topic/CRecordset::m_nFields.md).  L'Assistant écrit l'initialisation, mais il ne traite que les membres de données de type champ qu'il ajoute automatiquement.  Par exemple :  
  
    ```  
    m_nFields += 6;  
    ```  
  
     Certains types de données ne doivent pas être initialisés ici, comme, par exemple, `CLongBinary` ou les tableaux binaires.  
  
5.  Si la requête nécessite des paramètres, ajoutez un membre de données de type paramètre pour chaque paramètre, ainsi qu'un appel de fonctions RFX et une initialisation.  
  
6.  Vous devez incrémenter `m_nParams` pour chaque paramètre ajouté, comme vous l'avez fait dans `m_nFields` pour les champs ajoutés à l'étape 4 de cette procédure.  Pour plus d'informations, consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
7.  Écrivez manuellement une instruction SQL ayant la forme suivante :  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     où **CALL** est un mot clé ODBC, **proc\-name** le nom de la requête telle qu'elle est connue dans la source de données, et les « ? » des emplacements réservés pour les valeurs de paramètres fournies au recordset lors de l'exécution.  L'exemple suivant réserve un emplacement pour un paramètre :  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  Dans le code qui ouvre le recordset, définissez les valeurs des membres de données de type paramètre du recordset, puis appelez la fonction membre **Open**, en passant votre chaîne SQL au paramètre **lpszSQL**.  Ou remplacez la chaîne retournée par la fonction membre `GetDefaultSQL` dans votre classe.  
  
 Les exemples suivants illustrent la procédure d'appel d'une requête prédéfinie intitulée `Delinquent_Accts`, qui requiert un seul paramètre correspondant de numéro de secteur des ventes \(sales district number\).  Cette requête retourne trois colonnes : `Acct_No`, `L_Name`, `Phone`.  Toutes les colonnes sont issues de la table Customers.  
  
 Le recordset suivant définit les membres de données de type champ des colonnes retournées par la requête et le paramètre correspondant au numéro de secteur des ventes demandé lors de l'exécution.  
  
```  
class CDelinquents : public CRecordset  
{  
// Field/Param Data  
    LONG m_lAcct_No;  
    CString m_strL_Name;  
    CString m_strPhone;  
    LONG m_lDistParam;  
    // ...  
};  
```  
  
 La déclaration de classe est telle que l'Assistant l'a écrite, à l'exception du membre `m_lDistParam` ajouté manuellement.  D'autres membres ne sont pas indiqués ici.  
  
 L'exemple suivant illustre les initialisations des membres de données du constructeur `CDelinquents` :  
  
```  
CDelinquents::CDelinquents(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
    // Wizard-generated params:  
    m_lAcct_No = 0;  
    m_strL_Name = "";  
    m_strPhone = "";  
    m_nFields = 3;  
    // User-defined params:  
    m_nParams = 1;  
    m_lDistParam = 0;  
}  
```  
  
 Remarquez les initialisations de [m\_nFields](../Topic/CRecordset::m_nFields.md) et [m\_nParams](../Topic/CRecordset::m_nParams.md).  L'Assistant initialise `m_nFields` tandis que vous initialisez `m_nParams`.  
  
 L'exemple suivant illustre les fonctions RFX dans `CDelinquents::DoFieldExchange`:  
  
```  
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Long(pFX, "Acct_No", m_lAcct_No);  
    RFX_Text(pFX, "L_Name", m_strL_Name);  
    RFX_Text(pFX, "Phone", m_strPhone);  
    pFX->SetFieldType(CFieldExchange::param);  
    RFX_Long(pFX, "Dist_No", m_lDistParam);  
}  
```  
  
 Outre l'appel des fonctions RFX pour les trois colonnes retournées, le code gère la liaison du paramètre passé à l'exécution.  Ce paramètre constitue la clé de la colonne `Dist_No` \(numéro de secteur\).  
  
 Le prochain exemple montre comment définir la chaîne SQL et l'utiliser pour ouvrir le recordset.  
  
```  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
 Le code construit un instantané, lui passe le paramètre fourni préalablement par l'utilisateur et appelle la requête prédéfinie.  Lorsque la requête s'exécute, elle retourne les enregistrements correspondant au numéro de secteur des ventes spécifié.  Chaque enregistrement contient des colonnes pour le numéro de compte, le nom du client et son numéro de téléphone.  
  
> [!TIP]
>  Il se peut que vous vouliez gérer une valeur de retour \(paramètre de sortie\) à partir d'une procédure stockée.  Pour plus d'informations et obtenir un exemple, consultez [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : lancement d'une nouvelle requête sur un recordset \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [Recordset : déclaration de la classe d'une table \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Recordset : création d'une jointure \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)
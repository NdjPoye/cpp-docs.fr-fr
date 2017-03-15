---
title: "Recordset&#160;: param&#233;trage d&#39;un recordset (ODBC) | Microsoft Docs"
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
  - "ODBC (recordsets), paramétrer"
  - "paramétrer des recordsets"
  - "passer des paramètres, aux requêtes au moment de l'exécution"
  - "recordsets, paramétrer"
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Recordset&#160;: param&#233;trage d&#39;un recordset (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Il peut arriver que vous souhaitiez sélectionner des enregistrements à l'exécution, à l'aide d'informations préalablement calculées ou fournies par l'utilisateur final.  Les paramètres de recordset permettent d'atteindre cet objectif.  
  
 Cette rubrique explique :  
  
-   [l'objectif d'un recordset paramétré](#_core_parameterized_recordsets) ;  
  
-   [quand et pourquoi paramétrer un recordset](#_core_when_to_use_parameters) ;  
  
-   [comment déclarer des membres de données de type paramètre dans votre classe de recordset](#_core_parameterizing_your_recordset_class) ;  
  
-   [comment passer les informations sur les paramètres à un objet recordset lors de l'exécution](#_core_passing_parameter_values_at_run_time).  
  
##  <a name="_core_parameterized_recordsets"></a> Recordsets paramétrés  
 Un recordset paramétré permet de passer des informations sur les paramètres à l'exécution.  Il s'ensuit deux conséquences appréciables :  
  
-   une exécution en principe plus rapide ;  
  
-   la possibilité de créer une requête à l'exécution, à partir d'informations non disponibles au moment du design, comme celles qui sont calculées ou fournies par un utilisateur lors de l'exécution.  
  
 Quand vous appelez la fonction **Open** pour exécuter la requête, le recordset utilise les informations sur les paramètres pour compléter son instruction **SQL SELECT**.  Tout recordset peut être paramétré.  
  
##  <a name="_core_when_to_use_parameters"></a> Quand utiliser les paramètres  
 Parmi les utilisations de paramètres les plus classiques figurent les utilisations suivantes :  
  
-   Passage, lors de l'exécution, d'arguments à une requête prédéfinie.  
  
     Pour passer des paramètres à une procédure stockée, vous devez définir une instruction **CALL** ODBC personnalisée complète \(avec des emplacements réservés de paramètres\) lorsque vous appelez la fonction **Open**, substituant ainsi l'instruction SQL par défaut du recordset.  Pour plus d'informations, consultez [CRecordset::Open](../Topic/CRecordset::Open.md) dans *Class Library Reference* ainsi que [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md) et [Recordset : déclaration de la classe d'une requête prédéfinie \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  
  
-   Exécution efficace de nombreuses requêtes comportant différentes informations sur les paramètres.  
  
     Par exemple, chaque fois que l'utilisateur final recherche des informations sur un étudiant dans la base de données des étudiants inscrits; vous pouvez définir le nom de l'étudiant ou son ID comme étant des paramètres fournis par l'utilisateur.  Ensuite, quand vous appelez la fonction membre **Requery** du recordset, la requête ne sélectionne que l'enregistrement concernant cet étudiant.  
  
     La chaîne de filtre du recordset, stockée dans **m\_strFilter**, a la forme suivante :  
  
    ```  
    "StudentID = ?"  
    ```  
  
     Imaginons que l'ID de l'étudiant soit placé dans la variable `strInputID`.  Lorsque vous définissez un paramètre pour `strInputID` \(par exemple, l'ID étudiant 100\) la valeur de la variable est associée à l'emplacement de paramètre réservé, représenté par le « ? » dans la chaîne de filtre.  
  
     Assignez la valeur du paramètre de la façon suivante :  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     Vous ne pourriez pas définir une chaîne de filtre de la façon suivante :  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     Pour plus d'informations sur l'utilisation appropriée des guillemets dans les chaînes de filtre, consultez [Recordset : filtrage d'enregistrements \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
     La valeur du paramètre diffère à chaque fois que vous lancez une nouvelle requête sur le recordset avec un nouvel ID étudiant.  
  
    > [!TIP]
    >  L'utilisation d'un paramètre est plus efficace que la seule utilisation d'un filtre.  Dans le cas d'un recordset paramétré, la base de données ne doit traiter qu'une seule fois une instruction SQL **SELECT**.  Dans le cas d'un recordset filtré, l'instruction **SELECT** doit être exécutée chaque fois que vous lancez une nouvelle requête \(**Requery**\) avec une nouvelle valeur de filtre.  
  
 Pour plus d'informations sur les filtres, consultez [Recordset : filtrage d'enregistrements \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
##  <a name="_core_parameterizing_your_recordset_class"></a> Paramétrage de la classe de recordset  
  
> [!NOTE]
>  Cette section s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, l'implémentation de paramètres obéit à un processus similaire.  Pour plus d'informations, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Avant de créer la classe de recordset, déterminez les paramètres dont vous avez besoin, leurs types de données et comment le recordset les utilise.  
  
#### Pour paramétrer une classe de recordset  
  
1.  Exécutez l'[Assistant Consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) à partir de l'Assistant **Ajouter une classe** pour créer la classe.  
  
2.  Indiquez les membres de données de type champ des colonnes du recordset.  
  
3.  Une fois que l'Assistant a écrit la classe dans un fichier du projet, accédez au fichier .h et ajoutez manuellement un ou plusieurs membres de données de type paramètre à la déclaration de classe.  Cet ajout est similaire à celui de l'exemple suivant, relatif à une classe instantanée conçue pour répondre à la question « Which students are in the senior class? » \(« Quels étudiants font partie de la classe senior ? »\).  
  
    ```  
    class CStudentSet : public CRecordset  
    {  
    // Field/Param Data  
        CString m_strFirstName;  
        CString m_strLastName;  
        CString m_strStudentID;  
        CString m_strGradYear;  
  
        CString m_strGradYrParam;  
    };  
    ```  
  
     Ajoutez les membres de données de type paramètre après les membres de données de type champ générés par l'Assistant.  Par convention, le mot « Param » est ajouté à chaque nom de paramètre défini par l'utilisateur.  
  
4.  Modifiez la définition de la fonction membre [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) dans le fichier .cpp.  Ajoutez un appel de fonctions RFX pour chaque membre de données de type paramètre ajouté à la classe.  Pour plus d'informations sur l'écriture de fonctions RFX, consultez [Record Field Exchange : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  Faites précéder les appels RFX des paramètres par un appel unique à :  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  Dans le constructeur de la classe de recordset, incrémentez le compteur de paramètres, `m_nParams`.  
  
     Pour des informations, consultez [Record Field Exchange : utilisation du code écrit par l'Assistant](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md).  
  
6.  Lorsque vous écrivez le code créant l'objet recordset de la classe, placez un « ? » \(point d'interrogation\) à chaque endroit de l'instruction SQL où un paramètre doit être remplacé par une valeur.  
  
     Au moment de l'exécution, les emplacements réservés « ? » sont remplacés dans l'ordre par les valeurs que vous passez.  Le premier membre de données de type paramètre défini après l'appel de [SetFieldType](../Topic/CFieldExchange::SetFieldType.md) remplace le premier « ? » de la chaîne SQL, le deuxième membre de données de type paramètre remplace le deuxième « ? », et ainsi de suite.  
  
> [!NOTE]
>  L'ordre des paramètres est important : l'ordre des appels RFX des paramètres dans la fonction `DoFieldExchange` doit être identique à celui des emplacements de paramètres réservés dans la chaîne SQL.  
  
> [!TIP]
>  Il est probable que la chaîne utilisée soit celle que vous avez définie, le cas échéant, pour le membre de données [m\_strFilter](../Topic/CRecordset::m_strFilter.md) de la classe, mais certains pilotes ODBC autorisent des paramètres dans d'autres clauses SQL.  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a> Passage des valeurs des paramètres à l'exécution  
 Vous devez définir les valeurs des paramètres avant d'appeler les fonctions **Open** \(dans le cas d'un nouvel objet recordset\) ou **Requery** \(dans le cas d'un objet recordset existant\).  
  
#### Pour passer les valeurs des paramètres à un objet recordset à l'exécution  
  
1.  Construisez l'objet recordset.  
  
2.  Préparez une ou plusieurs chaînes, comme **m\_strFilter**, contenant la totalité ou une partie de l'instruction SQL.  Placez les emplacements réservés « ? » à l'endroit où les informations des paramètres doivent prendre place.  
  
3.  Assignez la valeur du paramètre fournie lors de l'exécution à chaque membre de données de type paramètre de l'objet.  
  
4.  Appelez la fonction membre **Open** \(ou **Requery** pour un recordset existant\).  
  
 Imaginons, par exemple, que vous vouliez définir une chaîne de filtre pour le recordset en utilisant les informations fournies lors de l'exécution.  Considérons que vous avez construit préalablement un recordset de la classe `CStudentSet` — appelé `rsStudent`s — et que vous voulez maintenant lancer une nouvelle requête pour obtenir un type particulier d'informations sur les étudiants.  
  
```  
// Set up a filter string with   
// parameter placeholders  
rsStudents.m_strFilter = "GradYear <= ?";  
  
// Obtain or calculate parameter values   
// to pass--simply assigned here   
CString strGradYear = GetCurrentAcademicYear( );  
  
// Assign the values to parameter data members  
rsStudents.m_strGradYrParam = strGradYear;  
  
// Run the query  
if( !rsStudents.Requery( ) )  
    return FALSE;  
```  
  
 Le recordset contient les enregistrements obéissant aux conditions définies par le filtre, construit à partir des paramètres fournis à l'exécution.  Dans le cas présent, le recordset contient les enregistrements de tous les « senior students » \(étudiants seniors\).  
  
> [!NOTE]
>  Si nécessaire, vous pouvez définir un membre de données de type paramètre avec la valeur Null, à l'aide de [SetParamNull](../Topic/CRecordset::SetParamNull.md).  Vous pouvez de même vérifier si un membre de données de type paramètre a la valeur Null, à l'aide de [IsFieldNull](../Topic/CRecordset::IsFieldNull.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : ajout, modification et suppression d'enregistrements \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Recordset : sélection d'enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)
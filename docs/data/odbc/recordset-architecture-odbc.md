---
title: "Recordset&#160;: architecture (ODBC) | Microsoft Docs"
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
  - "données membres du champ"
  - "données membres du champ, architecture des recordsets"
  - "m_nFields (donnée membre)"
  - "m_nFields (donnée membre), recordsets"
  - "m_nParams (donnée membre)"
  - "m_nParams (donnée membre), recordsets"
  - "ODBC (recordsets), architecture"
  - "membres de données paramètres des recordsets"
  - "recordsets, architecture"
  - "recordsets, données membres"
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset&#160;: architecture (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Cette rubrique décrit les membres de données qui composent l'architecture d'un objet recordset :  
  
-   [Membres de données de type champ](#_core_field_data_members)  
  
-   [Membres de données de type paramètre](#_core_parameter_data_members)  
  
-   [Utilisation des membres de données m\_nFields et m\_nParams](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si l'extraction de lignes en bloc est implémentée, l'architecture est similaire.  Pour plus d'informations sur les différences, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_a_sample_class"></a> Exemple de classe  
 Lorsque vous utilisez l'[Assistant Consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) à partir de l'Assistant **Ajouter une classe** et déclarez une classe de recordset dérivée de `CRecordset`, la classe obtenue possède la structure générale illustrée par l'exemple de classe suivant :  
  
```  
class CCourse : public CRecordset  
{  
public:  
   CCourse(CDatabase* pDatabase = NULL);  
   ...  
   CString m_strCourseID;  
   CString m_strCourseTitle;  
   CString m_strIDParam;  
};  
```  
  
 En début de classe, l'Assistant écrit un ensemble de [membres de données de type champ](#_core_field_data_members).  Lorsque vous créez la classe, vous devez indiquer un ou plusieurs membres de données de type champ.  Si la classe est paramétrée, à l'image de l'exemple de classe \(avec le membre de données `m_strIDParam`\), vous devez ajouter manuellement les [membres de données de type paramètre](#_core_parameter_data_members).  L'Assistant ne prend pas en charge l'ajout de paramètres à une classe.  
  
##  <a name="_core_field_data_members"></a> Membres de données de type champ  
 Les membres les plus importants de votre classe de recordset sont les membres des données de champ.  Pour chaque colonne que vous sélectionnez à partir de la source des données, la classe contient un membre de données du type de données approprié pour cette colonne.  Par exemple, l'[exemple de classe](#_core_a_sample_class) illustré en début de cette rubrique possède deux membres de données de type champ, les deux de type `CString`, appelés `m_strCourseID` et `m_strCourseTitle`.  
  
 Lorsque le recordset sélectionne une série d'enregistrements, la structure lie automatiquement les colonnes de l'enregistrement actuel \(après l'appel **Open**, le premier enregistrement est considéré comme l'enregistrement actuel\) aux données membres de champ de l'objet.  Autrement dit, l'infrastructure utilise le membre approprié de données de type champ comme tampon, dans lequel il stocke le contenu de la colonne d'un enregistrement.  
  
 Quand l'utilisateur passe à un nouvel enregistrement, l'infrastructure utilise les membres des données de champ pour représenter l'enregistrement actuel.  L'infrastructure actualise les membres des données de champ en remplaçant les valeurs de l'enregistrement précédent.  Les membres des données de champ sont également utilisés pour la mise à jour de l'enregistrement actuel ou pour l'ajout de nouveaux enregistrements.  Dans le cadre du processus de mise à jour d'un enregistrement, vous indiquez les valeurs de mise à jour en les assignant directement au\(x\) membre\(s\) de données de type champ approprié\(s\).  
  
##  <a name="_core_parameter_data_members"></a> Membres de données de type paramètre  
 Si la classe est paramétrée, elle comporte un ou plusieurs données membres de paramétrage.  Une classe paramétrée vous permet de baser une requête de recordset sur des informations obtenues ou calculées au moment de l'exécution.  
  
 En général, le paramètre vous aide à affiner la sélection, comme dans l'exemple suivant :  Fondé sur l'[exemple de classe](#_core_a_sample_class) du début de cette rubrique, l'objet recordset pourrait exécuter l'instruction SQL suivante :  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 Le « ? » constitue un emplacement réservé pour la valeur de paramètre fournie à l'exécution.  Lorsque vous construisez le recordset et définissez sa donnée membre `m_strIDParam` sur MATH101, l'instruction SQL effective pour le recordset devient :  
  
```  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 En définissant des membres des données de paramétrage, vous indiquez à l'infrastructure les paramètres utilisés dans la chaîne SQL.  L'infrastructure lie le paramètre, ce qui permet à ODBC de savoir où doivent être recherchées les valeurs qui viendront se substituer aux emplacements réservés.  Dans cet exemple, le recordset qui en résulte contient uniquement l'enregistrement provenant de la table Course avec une colonne CourseID dont la valeur est MATH101.  Toutes les colonnes spécifiées de cet enregistrement sont sélectionnées.  Vous pouvez indiquer autant de paramètres \(et d'emplacements réservés\) que vous le souhaitez.  
  
> [!NOTE]
>  MFC ne fait rien lui\-même de ces paramètres \(il n'effectue pas, notamment, de substitution de texte\).  À la place, MFC indique à ODBC où rechercher le paramètre ; ODBC récupère les données et effectue l'opération de paramétrage nécessaire.  
  
> [!NOTE]
>  L'ordre des paramètres est important.  Pour plus d'informations à ce sujet et sur les paramètres, consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a> Utilisation de m\_nFields et de m\_nParams  
 Quand un Assistant écrit un constructeur pour votre classe, il initialise aussi le membre de données [m\_nFields](../Topic/CRecordset::m_nFields.md), qui contient le nombre de [membres de données de type champ](#_core_field_data_members) dans la classe.  Si vous ajoutez des [paramètres](#_core_parameter_data_members) à votre classe, vous devez également procéder à l'initialisation du membre de données [m\_nParams](../Topic/CRecordset::m_nParams.md), qui contient le nombre de membres de données de type paramètre.  L'infrastructure utilise ces valeurs pour travailler avec les données membres.  
  
 Pour plus d'informations et d'exemples, consultez [Record Field Exchange : utilisation de RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : déclaration de la classe d'une table \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)
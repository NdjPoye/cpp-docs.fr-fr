---
title: "SQL&#160;: personnalisation de l&#39;instruction SQL du recordset (ODBC) | Microsoft Docs"
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
  - "personnaliser les instructions SQL"
  - "ODBC (recordsets), instructions SQL"
  - "substituer, instructions SQL"
  - "recordsets, instructions SQL"
  - "instructions SQL, personnaliser"
  - "instructions SQL, recordset"
  - "SQL, ouvrir des recordsets"
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL&#160;: personnalisation de l&#39;instruction SQL du recordset (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique :  
  
-   comment l'infrastructure construit une instruction SQL ;  
  
-   comment substituer l'instruction SQL.  
  
> [!NOTE]
>  Ces informations s'appliquent aux classes ODBC MFC.  Si vous utilisez les classes DAO MFC, consultez la rubrique « Comparison of Microsoft Jet Database Engine SQL and ANSI SQL » dans l'aide de DAO.  
  
## Construction d'une instruction SQL  
 Votre recordset base la sélection des enregistrements principalement sur une instruction SQL **SELECT**.  Lorsque vous déclarez votre classe à l'aide d'un Assistant, celui\-ci écrit une version de substitution de la fonction membre `GetDefaultSQL`, à peu près similaire au code suivant \(pour une classe de recordset intitulée `CAuthors`\) :  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 Par défaut, cette substitution retourne le nom de la table que vous avez défini au sein de l'Assistant.  Dans cet exemple, la table a pour nom « AUTHORS ». Lorsque, par la suite, vous appelez la fonction membre **Open** du recordset, **Open** construit l'instruction **SELECT** finale, sous la forme :  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 où `table-name` est obtenu par l'appel de `GetDefaultSQL` et `rfx-field-list` par les appels de la fonction RFX dans `DoFieldExchange`.  C'est ce que vous obtenez pour une instruction **SELECT** à moins que vous ne lui substituiez une version de remplacement à l'exécution ; il est également possible de modifier l'instruction par défaut à l'aide de paramètres ou d'un filtre.  
  
> [!NOTE]
>  Si vous indiquez un nom de colonne qui contient \(ou peut contenir\) des espaces, vous devez encadrer le nom entre crochets.  Par exemple, le nom « Prénom » doit s'écrire « \[Prénom\] ».  
  
 Pour substituer l'instruction **SELECT** par défaut, passez une chaîne contenant une instruction **SELECT** complète lors de l'appel de la fonction **Open**.  Au lieu de construire sa propre chaîne par défaut, le recordset utilise la chaîne que vous fournissez.  Si l'instruction de remplacement contient une clause **WHERE**, ne définissez pas de filtre dans **m\_strFilter**, car vous seriez alors en présence de deux instructions de filtrage.  De même, si l'instruction de remplacement contient une clause **ORDER BY**, ne définissez pas de commande de tri dans `m_strSort`, car vous auriez également deux instructions de tri.  
  
> [!NOTE]
>  Si vous utilisez des chaînes littérales dans vos filtres \(ou dans d'autres parties de l'instruction SQL\), vous devrez peut\-être « encadrer» \(autrement dit, entourer de délimiteurs spécifiques\) ces chaînes à l'aide d'un préfixe ou d'un suffixe \(composés d'un ou de plusieurs caractères\) propres au SGBD.  
  
 Il se peut également, en fonction de votre SGBD, que vous soyez confronté à certaines exigences syntaxiques particulières lors d'opérations telles que les jointures externes.  Utilisez les fonctions ODBC pour obtenir ces informations du pilote du SGBD.  Par exemple, appelez **::SQLGetTypeInfo** pour un type de données particulier comme **SQL\_VARCHAR**, afin d'obtenir les caractères **LITERAL\_PREFIX** et **LITERAL\_SUFFIX**.  Si vous écrivez un code indépendant de la base de données, consultez l'annexe C du guide *ODBC SDK* *Programmer's Reference* sur le CD\-ROM MSDN Library pour obtenir des informations de syntaxe détaillées.  
  
 Un objet recordset construit l'instruction SQL qu'il utilise pour sélectionner les enregistrements, sauf si vous passez une instruction SQL personnalisée.  Cette opération dépend principalement de la valeur que vous passez au paramètre `lpszSQL` de la fonction membre **Open**.  
  
 L'aspect général d'une instruction SQL **SELECT** est le suivant :  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 Une solution pour ajouter le mot clé **DISTINCT** à l'instruction SQL de votre recordset consiste à incorporer le mot clé dans le premier appel de fonction RFX dans `DoFieldExchange`.  Par exemple :  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  N'utilisez cette solution que dans le cas d'un recordset ouvert en lecture seule.  
  
## Substitution de l'instruction SQL  
 Le tableau ci\-après illustre les différentes possibilités pour le paramètre `lpszSQL` de la fonction **Open**.  Les différents cas présentés dans ce tableau sont expliqués en détail après le tableau.  
  
 **Le paramètre lpszSQL et la chaîne SQL obtenue**  
  
|Case|Valeur passée à lpszSQL|Instruction SELECT obtenue|  
|----------|-----------------------------|--------------------------------|  
|1|**NULL**|**SELECT** *rfx\-field\-list* **FROM** *table\-name*<br /><br /> `CRecordset::Open` appelle `GetDefaultSQL` pour obtenir le nom de la table.  La chaîne obtenue est l'une de celles qui sont présentées dans les cas 2 à 5, selon la valeur retournée par `GetDefaultSQL`.|  
|2|Un nom de table|**SELECT** *rfx\-field\-list* **FROM** *table\-name*<br /><br /> La liste des champs est extraite des instructions RFX de `DoFieldExchange`.  Si **m\_strFilter** et `m_strSort` ne sont pas vides, les clauses **WHERE** et\/ou **ORDER BY** sont ajoutées.|  
|3 \*|Une instruction **SELECT** complète sans clause **WHERE** ou **ORDER BY**|Telle qu'elle a été passée.  Si **m\_strFilter** et `m_strSort` ne sont pas vides, les clauses **WHERE** et\/ou **ORDER BY** sont ajoutées.|  
|4 \*|Une instruction **SELECT** complète avec les clauses **WHERE** et\/ou **ORDER BY**|Telle qu'elle a été passée.  **m\_strFilter** et\/ou `m_strSort` doivent rester vides, ou deux instructions de filtre et\/ou de tri sont générées.|  
|5 \*|Un appel à une procédure stockée|Telle qu'elle a été passée.|  
  
 \*`m_nFields` doit être inférieur ou égal au nombre de colonnes indiqué dans l'instruction **SELECT**.  Le type de données de chaque colonne définie dans l'instruction **SELECT** doit être identique à celui de la colonne de sortie RFX correspondante.  
  
### Cas 1   lpszSQL \= NULL  
 La sélection du recordset dépend de ce que `GetDefaultSQL` retourne après avoir été appelée par `CRecordset::Open`.  Les cas 2 à 5 décrivent les différentes chaînes obtenues possibles.  
  
### Cas 2   lpszSQL \= nom de table  
 Le recordset utilise RFX \(Record Field Exchange\) pour créer la liste des colonnes à partir des noms de colonnes fournis dans les appels de fonctions RFX de la substitution de la classe de recordset de `DoFieldExchange`.  Si vous déclarez la classe du recordset à l'aide d'un Assistant, le présent cas génère le même résultat que le cas 1 \(à condition que vous ayez passé le même nom de table que celui qui est défini dans l'Assistant\).  Si vous écrivez votre classe sans recourir à un Assistant, le cas 2 constitue la solution la plus simple pour construire l'instruction SQL.  
  
 L'exemple suivant construit une instruction SQL qui sélectionne des enregistrements à partir d'une application de base de données MFC.  Lorsque l'infrastructure appelle la fonction membre `GetDefaultSQL`, celle\-ci retourne le nom de table `SECTION`.  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 Afin d'obtenir les noms des colonnes pour l'instruction SQL **SELECT**, l'infrastructure appelle la fonction membre `DoFieldExchange`.  
  
```  
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Text(pFX, "CourseID", m_strCourseID);  
    RFX_Text(pFX, "InstructorID", m_strInstructorID);  
    RFX_Text(pFX, "RoomNo", m_strRoomNo);  
    RFX_Text(pFX, "Schedule", m_strSchedule);  
    RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 Lorsque l'instruction SQL est complète, elle présente l'aspect suivant :  
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### Cas 3  lpszSQL \= instruction SELECT\/FROM  
 Vous définissez la liste des colonnes manuellement plutôt que de vous en remettre à RFX pour la construire automatiquement.  Vous pourriez vouloir agir ainsi dans les cas suivants :  
  
-   Vous voulez spécifier le mot clé **DISTINCT** après **SELECT**.  
  
     La liste des colonnes doit correspondre aux noms et types de colonnes, et ce dans un ordre identique à celui de `DoFieldExchange`.  
  
-   Vous avez de bonnes raisons de vouloir récupérer manuellement les valeurs des colonnes à l'aide de la fonction ODBC **::SQLGetData** plutôt que de laisser RFX lier et récupérer automatiquement les colonnes.  
  
     Par exemple, vous souhaitez peut\-être intégrer les nouvelles colonnes qu'un client a ajoutées aux tables de la base de données après que l'application a été distribuée.  Vous devez ajouter ces membres de données de champ supplémentaires, inconnus lors de la déclaration de la classe avec un Assistant.  
  
     La liste des colonnes doit correspondre aux noms et types de colonnes, et ce dans un ordre identique à celui qui est défini dans `DoFieldExchange`, suivie des noms de colonnes liées manuellement.  Pour plus d'informations, consultez [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Vous voulez joindre des tables en spécifiant plusieurs tables dans la clause **FROM**.  
  
     Pour obtenir des informations et un exemple, consultez [Recordset : création d'une jointure \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
### Cas 4  lpszSQL \= SELECT\/FROM Plus avec WHERE et\/ou ORDER BY  
 Vous fournissez toutes les informations : la liste des colonnes \(établie à partir des appels RFX dans `DoFieldExchange`\), la liste des tables et le contenu d'une clause **WHERE** et\/ou d'une clause **ORDER BY**.  Si vous utilisez les clauses **WHERE** et\/ou **ORDER BY**, n'utilisez ni **m\_strFilter** ni `m_strSort`.  
  
### Cas 5    lpszSQL \= appel d'une procédure stockée  
 Si vous devez appeler une requête prédéfinie \(comme une procédure stockée dans une base de données Microsoft SQL Server\), vous devez écrire une instruction **CALL** dans la chaîne que vous passez à `lpszSQL`.  Les Assistants ne prennent pas en charge la déclaration d'une classe de recordset pour l'appel d'une requête prédéfinie.  Certaines requêtes prédéfinies ne retournent pas d'enregistrements.  
  
 Si une requête prédéfinie ne retourne pas d'enregistrements, vous pouvez utiliser directement la fonction `ExecuteSQL` de la fonction membre `CDatabase`.  Dans le cas d'une requête prédéfinie qui ne retourne pas d'enregistrements, vous devez également écrire manuellement les appels RFX dans `DoFieldExchange` pour toute colonne retournée par la procédure.  Les appels RFX doivent être dans le même ordre et retourner les mêmes types que ceux de la requête prédéfinie.  Pour plus d'informations, consultez [Recordset : déclaration de la classe d'une requête prédéfinie \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  
  
## Voir aussi  
 [SQL : types de données SQL et C\+\+ \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL : appels SQL directs \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
---
title: "Recordset&#160;: s&#233;lection d&#39;enregistrements par les recordsets (ODBC) | Microsoft Docs"
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
  - "ODBC (recordsets), sélectionner des enregistrements"
  - "sélection des enregistrements, ODBC (recordsets)"
  - "enregistrements, sélectionner"
  - "recordsets, construire des instructions SQL"
  - "recordsets, sélectionner des enregistrements"
  - "instructions SQL, recordset"
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Recordset&#160;: s&#233;lection d&#39;enregistrements par les recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Cette rubrique explique :  
  
-   [vos rôle et options dans la sélection d'enregistrements](#_core_your_options_in_selecting_records) ;  
  
-   [comment un recordset construit son instruction SQL et sélectionne les enregistrements](#_core_how_a_recordset_constructs_its_sql_statement) ;  
  
-   [les actions à entreprendre pour personnaliser la sélection](#_core_customizing_the_selection).  
  
 Les recordsets sélectionnent les enregistrements d'une source de données via un pilote ODBC en envoyant des instructions SQL au pilote.  L'instruction SQL envoyée dépend de la façon dont vous avez conçu et ouvert la classe de recordset.  
  
##  <a name="_core_your_options_in_selecting_records"></a> Options de sélection des enregistrements  
 Le tableau suivant répertorie les options de sélection des enregistrements.  
  
### Comment et quand influer sur un recordset  
  
|Pour...|Vous pouvez :|  
|-------------|-------------------|  
|Déclarer la classe de recordset à l'aide de l'Assistant **Ajouter une classe**|Définir la table à partir de laquelle s'effectue la sélection.<br /><br /> Définir les colonnes à inclure.<br /><br /> Consultez [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|  
|Implémenter la classe de recordset|Substituer les fonctions membres `OnSetOptions` \(option avancée\) pour définir des options propres à l'application ou modifier les valeurs par défaut.  Définir les membres de données de type paramètre si vous voulez un recordset paramétré.|  
|Construire un objet recordset \(avant d'appeler **Open**\)|Préciser la condition de recherche \(éventuellement composée\) à utiliser dans la clause **WHERE** qui filtre les enregistrements.  Consultez [Recordset : filtrage d'enregistrements \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Définir l'ordre de tri à utiliser dans la clause **ORDER BY** qui trie les enregistrements.  Consultez [Recordset : tri d'enregistrements \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Définir les valeurs des paramètres ajoutés à la classe.  Consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|  
|Exécuter la requête du recordset en appelant **Open**|Définir une chaîne SQL personnalisée pour remplacer la chaîne SQL par défaut définie par l'Assistant.  Consultez [CRecordset::Open](../Topic/CRecordset::Open.md) dans *Class Library Reference* et [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).|  
|Appeler **Requery** pour lancer une nouvelle requête sur le recordset avec les valeurs les plus récentes de la source de données|Définir de nouveaux paramètres, un filtrage ou un tri.  Consultez [Recordset : lancement d'une nouvelle requête sur un recordset \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).|  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> Construction de l'instruction SQL par le recordset  
 Quand vous appelez la fonction membre [Open](../Topic/CRecordset::Open.md) d'un objet recordset, **Open** construit l'instruction SQL à l'aide d'une partie ou de la totalité des éléments suivants :  
  
-   Le paramètre **lpszSQL** passé à **Open**.  S'il est différent de **NULL**, ce paramètre définit une chaîne SQL personnalisée, ou une partie de celle\-ci.  La structure analyse la chaîne.  Si la chaîne est une instruction SQL **SELECT** ou une instruction ODBC **CALL**, l'infrastructure utilise la chaîne comme instruction SQL du recordset.  Si la chaîne ne commence pas par "SELECT" ou "{CALL", l'infrastructure utilise ce qui a été fourni pour construire la clause SQL **FROM**.  
  
-   La chaîne retournée par [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md).  Par défaut, il s'agit du nom de la table que vous avez défini pour le recordset dans l'Assistant, mais vous pouvez modifier ce qui est retourné par la fonction.  L'infrastructure appelle `GetDefaultSQL` — si la chaîne ne commence pas par "SELECT" ou par "{CALL", elle est considérée comme nom de table, utilisé alors pour construire la chaîne SQL.  
  
-   Les membres de données de type champ de recordset, qui doivent être liés à des colonnes spécifiques de la table.  L'infrastructure lie les colonnes de l'enregistrement aux adresses de ces membres, les utilisant comme tampons.  L'infrastructure détermine la corrélation des membres de données de type champ et des colonnes de la table à partir des appels de fonction [RFX](../../data/odbc/record-field-exchange-using-rfx.md) ou RFX en bloc dans les fonctions membres [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) ou [DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md) du recordset.  
  
-   Le [filtre](../../data/odbc/recordset-filtering-records-odbc.md) du recordset, s'il existe, contenu dans le membre de données [m\_strFilter](../Topic/CRecordset::m_strFilter.md).  L'infrastructure utilise la chaîne pour construire une clause SQL **WHERE**.  
  
-   L'ordre de [tri](../../data/odbc/recordset-sorting-records-odbc.md) du recordset, s'il existe, contenu dans le membre de données [m\_strSort](../Topic/CRecordset::m_strSort.md).  L'infrastructure utilise la chaîne pour construire une clause SQL **ORDER BY**.  
  
    > [!TIP]
    >  Pour utiliser la clause SQL **GROUP BY** \(et éventuellement la clause **HAVING**\), ajoutez les clauses à la fin de la chaîne de filtre.  
  
-   Les valeurs des [membres de données de type paramètre](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) que vous avez définis pour la classe.  Vous définissez les valeurs des paramètres juste avant d'appeler **Open** ou **Requery**.  L'infrastructure lie les valeurs des paramètres aux emplacements réservés « ? » de la chaîne SQL.  À la compilation, vous définissez la chaîne avec les emplacements réservés.  À l'exécution, l'infrastructure complète les informations à partir des valeurs de paramètres que vous passez.  
  
 **Open** construit une instruction SQL **SELECT** à partir de ces éléments.  Pour plus d'informations sur l'utilisation de ces éléments par l'infrastructure, consultez [Personnalisation de la sélection](#_core_customizing_the_selection).  
  
 Après avoir construit l'instruction, **Open** l'envoie au gestionnaire de pilotes ODBC \(et à la bibliothèque de curseurs ODBC si elle a été chargée en mémoire\), lequel à son tour la transmet au pilote ODBC du SGBD concerné.  Le pilote communique avec le SGBD pour effectuer la sélection sur la source de données et extrait le premier enregistrement.  L'infrastructure charge l'enregistrement dans les membres de données de type champ de recordset.  
  
 Vous pouvez associer ces techniques pour ouvrir des [tables](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) et pour construire une requête fondée sur la [jointure](../../data/odbc/recordset-performing-a-join-odbc.md) de plusieurs tables.  Avec une personnalisation supplémentaire, vous pouvez appeler des [requêtes prédéfinies](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) \(procédures stockées\), sélectionner des colonnes inconnues au moment du design et les [lier](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) aux champs du recordset, ou effectuer bien d'autres tâches d'accès aux données.  Les tâches que vous ne pouvez pas effectuer en personnalisant les recordsets peuvent toujours être accomplies en [appelant les fonctions ODBC API](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) ou en exécutant directement les instructions SQL avec [CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md).  
  
##  <a name="_core_customizing_the_selection"></a> Personnalisation de la sélection  
 Outre le fait de fournir un filtre, un ordre de tri ou des paramètres, vous pouvez prendre les mesures suivantes pour personnaliser la sélection du recordset :  
  
-   Passer une chaîne SQL personnalisée à **lpszSQL** lorsque vous appelez la fonction [Open](../Topic/CRecordset::Open.md) pour le recordset.  Toute valeur passée à **lpsqSQL** a priorité sur ce que la fonction membre [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md) retourne.  
  
     Pour plus d'informations, consultez [SQL: personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md), qui décrit les types d'instructions SQL \(ou d'instructions partielles\) que vous pouvez passer à **Open** et l'utilisation qu'en fait l'infrastructure.  
  
    > [!NOTE]
    >  Si la chaîne personnalisée que vous passez ne commence pas par "SELECT" ou "{CALL", MFC en déduit qu'elle contient un nom de table.  Cette remarque s'applique aussi à l'élément à puce suivant.  
  
-   Modifier la chaîne que l'Assistant écrit dans la fonction membre `GetDefaultSQL` du recordset.  Modifiez le code de la fonction pour changer ce qu'elle retourne.  Par défaut, l'Assistant écrit une fonction `GetDefaultSQL` retournant un seul nom de table.  
  
     Vous pouvez demander à `GetDefaultSQL` de retourner les éléments que vous passez au paramètre **lpszSQL** de la fonction **Open**.  Si vous ne passez pas une chaîne personnalisée SQL dans **lpszSQL**, l'infrastructure utilise la chaîne retournée par `GetDefaultSQL`.  Au minimum, `GetDefaultSQL` doit retourner un nom de table.  Mais vous pouvez faire en sorte que soient retournés plusieurs noms de tables, une instruction **SELECT** complète, une instruction ODBC **CALL**, etc.  Pour obtenir la liste de ce que vous pouvez passer à **lpszSQL** \(ou demander à `GetDefaultSQL` de retourner\) consultez [SQL : personnalisation de l'instruction SQL du recordset \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
     Si vous effectuez une jointure sur deux ou plusieurs tables, réécrivez `GetDefaultSQL` pour personnaliser la liste des tables utilisée dans la clause SQL **FROM**.  Pour plus d'informations, consultez [Recordset : création d'une jointure \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
-   Lier manuellement les membres de données de type champ supplémentaires, peut\-être à partir des informations obtenues à l'exécution sur le schéma de la source de données.  Ajoutez les membres de données de type champ à la classe de recordset, les appels de fonction [RFX](../../data/odbc/record-field-exchange-using-rfx.md) ou RFX en bloc correspondants aux fonctions membres [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) ou [DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md), et les initialisations des membres de données dans le constructeur de classe.  Pour plus d'informations, consultez [Recordset : liaison dynamique des colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Substituer les fonctions membres du recordset; comme `OnSetOptions`, pour définir les options propres à l'application ou substituer les valeurs par défaut.  
  
 Si vous devez établir le recordset à partir d'une instruction SQL complexe, vous devrez utiliser conjointement certaines de ces techniques de personnalisation.  Par exemple, vous pouvez utiliser des clauses et mots clés SQL non directement pris en charge par les recordsets ou joindre plusieurs tables.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)   
 [SQL](../../data/odbc/sql.md)   
 [Recordset : verrouillage d'enregistrements \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)
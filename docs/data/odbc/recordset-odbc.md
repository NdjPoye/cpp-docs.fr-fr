---
title: "Recordset (ODBC) | Microsoft Docs"
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
  - "recordsets dynamiques"
  - "dynasets"
  - "recordsets avant uniquement"
  - "ODBC (recordsets)"
  - "ODBC (recordsets), CRecordset (objets)"
  - "recordsets, à propos des recordsets"
  - "recordsets, créer"
  - "recordsets, dynasets"
  - "recordsets, instantanés"
  - "instantanés, ODBC (recordsets)"
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Un objet de la classe [CRecordset](../../mfc/reference/crecordset-class.md) représente un ensemble d'enregistrements sélectionnés à partir d'une source de données.  Les enregistrements peuvent provenir :  
  
-   d'une table ;  
  
-   d'une requête ;  
  
-   d'une procédure stockée accédant à une ou plusieurs tables.  
  
 Un exemple de recordset constitué à partir d'une table est « all customers » \(« tous les clients »\) ; ce recordset accède à la table Customer.  Un exemple de requête est « all invoices for Joe Smith » \(« toutes les factures de Joe Smith »\). Un exemple de recordset fondé sur une procédure stockée \(parfois appelée requête prédéfinie\) est « all of the delinquent accounts » \(« tous les comptes mauvais payeurs »\), qui appelle une procédure stockée dans la base de données principale.  Un recordset peut joindre deux ou plusieurs tables d'une même source de données, mais non des tables de sources de données différentes.  
  
> [!NOTE]
>  Pour plus d'informations sur la dérivation des classes de recordset à l'aide des Assistants, consultez [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) et [Prise en charge des bases de données, Assistant Application MFC](../../mfc/reference/database-support-mfc-application-wizard.md).  
  
> [!NOTE]
>  Certains pilotes ODBC prennent en charge les vues de base de données.  Dans ce sens, une vue est alors une requête créée initialement par l'instruction SQL `CREATE VIEW` Les Assistants ne prennent pas en charge les vues, mais vous pouvez vous\-même écrire le code correspondant.  
  
##  <a name="_core_recordset_capabilities"></a> Capacités des recordsets  
 Tous les objets recordset partagent les capacités suivantes :  
  
-   Si la source de données n'est pas en lecture seule, vous pouvez indiquer que le recordset est [modifiable](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [extensible](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md) ou en lecture seule.  Si le recordset est modifiable, vous avez le choix entre le [verrouillage](../../data/odbc/recordset-locking-records-odbc.md) optimiste ou pessimiste, à condition que le pilote assure la prise en charge appropriée de la méthode de verrouillage.  Si la source de données est en lecture seule, le recordset sera en lecture seule.  
  
-   Vous pouvez appeler des fonctions membres pour [faire défiler](../../data/odbc/recordset-scrolling-odbc.md) les enregistrements sélectionnés.  
  
-   Vous pouvez [filtrer](../../data/odbc/recordset-filtering-records-odbc.md) les enregistrements pour indiquer les enregistrements à sélectionner parmi ceux qui sont disponibles.  
  
-   Vous pouvez [trier](../../data/odbc/recordset-sorting-records-odbc.md) les enregistrements en ordre croissant ou décroissant, et ce sur une ou plusieurs colonnes.  
  
-   Vous pouvez [paramétrer](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) le recordset pour définir la sélection du recordset à l'exécution.  
  
##  <a name="_core_snapshots_and_dynasets"></a> Instantanés et feuilles de réponse dynamiques  
 Il existe deux principaux types de recordsets : les [instantanés](../../data/odbc/snapshot.md) et les [feuilles de réponse dynamiques](../../data/odbc/dynaset.md).  Tous deux sont pris en charge par la classe `CRecordset`.  Chacun partage les caractéristiques communes à l'ensemble des recordsets, mais chacun dispose également d'extensions de fonctionnalités qui lui sont propres.  Les instantanés fournissent une vue statique des données et sont particulièrement utiles dans le cas des états ou lorsque vous souhaitez obtenir une vue des données à un instant précis.  Les feuilles de réponse dynamiques sont utiles lorsque vous voulez que les mises à jour effectuées par d'autres utilisateurs soient visibles dans le recordset, sans que vous ayez à lancer de nouveau une requête ou à actualiser le recordset.  Les instantanés et les feuilles de réponse dynamiques peuvent être modifiables ou en lecture seule.  Pour prendre en compte les enregistrements ajoutés ou supprimés par d'autres utilisateurs, appelez [CRecordset::Requery](../Topic/CRecordset::Requery.md).  
  
 `CRecordset` autorise également deux autres types de recordsets : les recordsets dynamiques et les recordsets en avant seulement \(forward\-only\).  Les premiers sont semblables aux feuilles de réponse dynamiques ; cependant, ils prennent en compte tout enregistrement ajouté ou supprimé sans appeler `CRecordset::Requery`.  Pour cette raison, les recordsets dynamiques sont généralement coûteux en temps de traitement sur le SGBD et nombre de pilotes ODBC ne les prennent pas en charge.  En comparaison, les recordsets en avant seulement offrent la méthode d'accès la plus efficace pour les recordsets ne nécessitant pas de mises à jour ou de défilement arrière.  Par exemple, vous pouvez utiliser un recordset en avant seulement pour déplacer les données d'une source à une autre, quand vous n'avez besoin de consulter les données qu'en avançant.  Pour utiliser un recordset en avant seulement, vous devez effectuer les deux actions suivantes :  
  
-   Passer l'option **CRecordset::forwardOnly** comme paramètre `nOpenType` de la fonction membre [Open](../Topic/CRecordset::Open.md).  
  
-   Indiquer **CRecordset::readOnly** dans le paramètre `dwOptions` de la fonction **Open**.  
  
    > [!NOTE]
    >  Pour plus d'informations sur la configuration requise des pilotes ODBC pour la prise en charge des feuilles de réponse dynamiques, consultez [ODBC](../../data/odbc/odbc-basics.md).  Pour obtenir la liste des pilotes ODBC contenus dans cette version de Visual C\+\+ et des informations sur l'obtention de pilotes supplémentaires, consultez [Liste de pilotes ODBC](../../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_your_recordsets"></a> Vos recordsets  
 Pour chaque table, vue ou procédure stockée distincte à laquelle vous souhaitez accéder, vous définissez généralement une classe dérivée de `CRecordset`. \(L'exception est la jointure de base de données, où un recordset représente des colonnes provenant de deux ou de plusieurs tables.\) Lorsque vous dérivez une classe de recordset, vous activez le mécanisme RFX \(Record Field eXchange\) ou RFX en bloc \(Bulk RFX\), tous deux similaires au mécanisme DDX \(Dialog Data eXchange\).  RFX et RFX en bloc simplifient le transfert de données entre la source et le recordset ; en outre, RFX peut transférer les données de votre recordset vers la source de données.  Pour plus d'informations, consultez [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md) et [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Un objet recordset donne accès à tous les enregistrements sélectionnés.  Vous faites défiler les enregistrements sélectionnés à l'aide des fonctions membres de la classe `CRecordset`, comme `MoveNext` et `MovePrev`.  En même temps, un objet recordset ne représente qu'un seul des enregistrements sélectionnés, à savoir l'enregistrement courant.  Vous pouvez examiner les champs de l'enregistrement courant en déclarant les variables membres de la classe du recordset correspondant aux colonnes de la table ou des enregistrements obtenus par la requête de base de données.  Pour plus d'informations sur les données membres d'un recordset, consultez [Recordset : architecture \(ODBC\)](../../data/odbc/recordset-architecture-odbc.md).  
  
 Les rubriques suivantes décrivent en détail l'utilisation des objets Recordset :  Les rubriques sont réparties en catégories fonctionnelles et présentées selon l'ordre de lecture naturel afin d'en faciliter la consultation séquentielle.  
  
### Rubriques relatives aux mécanismes d'ouverture, de lecture et de fermeture des recordsets  
  
-   [Recordset : architecture \(ODBC\)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [Recordset : déclaration de la classe d'une table \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [Recordset : création et fermeture de recordsets \(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [Recordset : défilement \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)  
  
-   [Recordset : signets et positions absolues \(ODBC\)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [Recordset : filtrage d'enregistrements \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [Recordset : tri d'enregistrements \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### Rubriques relatives aux mécanismes de modification des recordsets  
  
-   [Recordset : ajout, modification et suppression d'enregistrements \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [Recordset : verrouillage d'enregistrements \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [Recordset : lancement d'une nouvelle requête sur un recordset \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### Rubriques relatives à quelques techniques avancées  
  
-   [Recordset : création d'une jointure \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)  
  
-   [Recordset : déclaration de la classe d'une requête prédéfinie \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)  
  
-   [Recordset : utilisation d'éléments de données volumineux \(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [Recordset : calculs de totaux et autres résultats de regroupement \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### Rubriques sur le fonctionnement des recordsets  
  
-   [Recordset : sélection d'enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)  
  
-   [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [MFC ODBC, consommation](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md)
---
title: "Recordset&#160;: fonctionnement d&#39;AddNew, Edit et Delete (ODBC) | Microsoft Docs"
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
  - "AddNew (méthode)"
  - "données dans les recordsets (C++)"
  - "ODBC (recordsets C++), ajouter des enregistrements"
  - "ODBC (recordsets C++), supprimer des enregistrements"
  - "ODBC (recordsets C++), modifier les enregistrements"
  - "modification d'enregistrements (C++), dans les recordsets"
  - "enregistrements (C++), ajouter"
  - "enregistrements (C++), supprimer dans des recordsets"
  - "enregistrements (C++), modifier"
  - "enregistrements (C++), mettre à jour"
  - "recordsets (C++), ajouter des enregistrements"
  - "recordsets (C++), supprimer des enregistrements"
  - "recordsets (C++), modifier les enregistrements"
  - "recordsets (C++), mettre à jour"
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: fonctionnement d&#39;AddNew, Edit et Delete (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 La présente rubrique explique le fonctionnement des fonctions membres `AddNew`, **Edit** et **Delete** de la classe `CRecordset`.  Les rubriques traitées ici sont les suivantes :  
  
-   [le fonctionnement de l'ajout d'enregistrements ;](#_core_adding_a_record)  
  
-   [Visibilité des enregistrements ajoutés](#_core_visibility_of_added_records)  
  
-   [le fonctionnement de la modification d'enregistrements ;](#_core_editing_an_existing_record)  
  
-   [le fonctionnement de la suppression d'enregistrements.](#_core_deleting_a_record)  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Comme complément d'information, vous pouvez lire la rubrique [RFX : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md), qui décrit le rôle correspondant de RFX dans les opérations de mise à jour.  
  
##  <a name="_core_adding_a_record"></a> Ajout d'un enregistrement  
 L'ajout d'un nouvel enregistrement à un recordset nécessite l'appel de la fonction membre [AddNew](../Topic/CRecordset::AddNew.md) du recordset, la définition des valeurs des membres de données de type champ du nouvel enregistrement et l'appel de la fonction membre [Update](../Topic/CRecordset::Update.md) pour écrire l'enregistrement dans la source de données.  
  
 Comme condition préalable de l'appel de `AddNew`, le recordset ne doit pas avoir été ouvert en lecture seule.  Les fonctions membres `CanUpdate` et `CanAppend` permettent de définir ces conditions.  
  
 Lorsque vous appelez `AddNew` :  
  
-   L'enregistrement du tampon d'édition est stocké, si bien que son contenu peut être restauré si l'opération est annulée.  
  
-   Les membres de données de type champ sont pourvus d'un indicateur, de telle sorte qu'il est possible par la suite d'identifier les modifications dont ils ont été l'objet.  Les membres de données de type champ sont aussi marqués comme non modifiés et définis avec la valeur Null.  
  
 Après que vous avez appelé `AddNew`, le tampon d'édition représente un nouvel enregistrement vide, prêt à être complété à l'aide de valeurs.  À cette fin, vous assignez manuellement les valeurs.  Au lieu d'indiquer la valeur réelle des données d'un champ, vous pouvez appeler `SetFieldNull` pour définir la valeur Null.  
  
 Pour valider les modifications, vous appelez **Update**.  Lorsque vous appelez **Update** pour le nouvel enregistrement :  
  
-   Si votre pilote ODBC prend en charge la fonction API ODBC **::SQLSetPos**, MFC utilise la fonction pour ajouter l'enregistrement à la source de données.  Avec **::SQLSetPos**, MFC peut ajouter plus efficacement un enregistrement car il n'a pas à construire et à traiter une instruction SQL.  
  
-   S'il n'est pas possible d'utiliser **::SQLSetPos**, MFC procède de la manière suivante :  
  
    1.  Si aucune modification n'est détectée, **Update** ne fait rien et retourne la valeur 0.  
  
    2.  S'il y a eu des modifications, **Update** construit une instruction SQL **INSERT**.  Les colonnes représentées par tous les membres de données de type champ modifiés \(« dirty »\) sont répertoriées dans l'instruction **INSERT**.  Pour imposer l'insertion d'une colonne, appelez la fonction membre [SetFieldDirty](../Topic/CRecordset::SetFieldDirty.md) :  
  
        ```  
        SetFieldDirty( &m_dataMember, TRUE );  
        ```  
  
    3.  **Update** valide le nouvel enregistrement — l'instruction **INSERT** est exécutée et l'enregistrement est validé dans la table de la source de données \(et le recordset, s'il ne s'agit pas d'un instantané\) à moins qu'une transaction soit en cours.  
  
    4.  L'enregistrement stocké est restauré dans le tampon d'édition.  L'enregistrement qui était courant avant l'appel de `AddNew` redevient l'enregistrement courant, indépendamment du fait que l'instruction **INSERT** se soit déroulée ou non avec succès.  
  
    > [!TIP]
    >  Pour contrôler totalement le nouvel enregistrement, suivez la solution suivante : définissez les valeurs de tous les champs qui contiendront des valeurs, puis définissez explicitement tous les champs qui conserveront la valeur Null en appelant `SetFieldNull` avec un pointeur vers le champ et le paramètre avec la valeur **TRUE** \(par défaut\).  Si vous voulez garantir qu'un champ ne sera pas écrit dans la source de données, appelez `SetFieldDirty` avec un pointeur vers le champ et le paramètre avec la valeur **FALSE**, et ne modifiez pas la valeur du champ.  Pour déterminer si un champ peut avoir ou non la valeur Null, appelez `IsFieldNullable`.  
  
    > [!TIP]
    >  Pour détecter à quel moment les membres de données du recordset changent de valeur, MFC utilise la valeur **PSEUDO\_NULL** appropriée à chaque type de données que vous pouvez stocker dans un recordset.  Si vous devez explicitement définir un champ avec la valeur **PSEUDO\_NULL** et qu'un champ a déjà été marqué avec la valeur Null, vous devez aussi appeler `SetFieldNull`, en passant l'adresse du champ dans le premier paramètre et **FALSE** dans le second paramètre.  
  
##  <a name="_core_visibility_of_added_records"></a> Visibilité des enregistrements ajoutés  
 Quand le recordset peut\-il voir un enregistrement ajouté ?  Que des enregistrements ajoutés soient visibles ou non dépend de deux facteurs :  
  
-   les capacités du pilote ;  
  
-   les bénéfices dont l'infrastructure peut tirer parti.  
  
 Si votre pilote ODBC prend en charge la fonction API ODBC **::SQLSetPos**, MFC utilise la fonction pour ajouter les enregistrements.  Avec **::SQLSetPos**, les enregistrements ajoutés sont visibles par tout recordset MFC modifiable.  Sans prise en charge de la fonction, les enregistrements ajoutés ne sont pas visibles et vous devez appeler **Requery** pour les visualiser.  L'utilisation de **::SQLSetPos** est également plus efficace.  
  
##  <a name="_core_editing_an_existing_record"></a> Modification d'un enregistrement existant  
 La modification d'un enregistrement existant dans un recordset nécessite de faire défiler le jeu jusqu'à l'enregistrement, d'appeler la fonction membre [Edit](../Topic/CRecordset::Edit.md) du recordset, de définir les valeurs des membres de données de type champ du nouvel enregistrement et d'appeler la fonction membre [Update](../Topic/CRecordset::Update.md) pour écrire l'enregistrement modifié dans la source de données.  
  
 Comme condition préalable de l'appel de **Edit**, le recordset doit être modifiable et positionné sur un enregistrement.  Les fonctions membres `CanUpdate` et `IsDeleted` permettent de définir ces conditions.  L'enregistrement courant ne doit pas avoir été déjà supprimé et des enregistrements doivent être présents dans le recordset \(`IsBOF` et `IsEOF` retournent la valeur 0\).  
  
 Lorsque vous appelez **Edit**, l'enregistrement présent dans le tampon d'édition \(l'enregistrement actif\) est stocké.  Les valeurs de l'enregistrement stocké sont ultérieurement utilisées pour détecter si des champs ont été modifiés.  
  
 Après que vous avez appelé **Edit**, le tampon d'édition continue de contenir l'enregistrement courant, mais il est désormais prêt à accepter les modifications sur les membres de données de type champ.  Pour modifier l'enregistrement, définissez manuellement les valeurs des membres de données de type champ que vous voulez modifier.  Au lieu d'indiquer la valeur réelle des données d'un champ, vous pouvez appeler `SetFieldNull` pour définir la valeur Null.  Pour valider les modifications, appelez **Update**.  
  
> [!TIP]
>  Pour quitter le mode `AddNew` ou **Edit**, appelez **Move** avec le paramètre **AFX\_MOVE\_REFRESH**.  
  
 Comme condition préalable à l'appel de **Update**, le recordset ne doit pas être vide et l'enregistrement courant ne doit pas avoir été supprimé.  `IsBOF`, `IsEOF` et `IsDeleted` doivent retourner la valeur 0.  
  
 Lorsque vous appelez **Update** pour l'enregistrement modifié :  
  
-   Si votre pilote ODBC prend en charge la fonction API ODBC **::SQLSetPos**, MFC utilise la fonction pour mettre à jour l'enregistrement dans la source de données.  Avec **::SQLSetPos**, le pilote compare le tampon d'édition et l'enregistrement correspondant sur le serveur, et met à jour l'enregistrement sur le serveur en cas de différence.  Avec **::SQLSetPos**, MFC peut mettre à jour plus efficacement un enregistrement car il n'a pas à construire et à traiter une instruction SQL.  
  
     ou  
  
-   S'il n'est pas possible d'utiliser **::SQLSetPos**, MFC procède de la manière suivante :  
  
    1.  S'il n'y a eu aucune modification, **Update** ne fait rien et retourne la valeur 0.  
  
    2.  S'il y a eu des modifications, **Update** construit une instruction SQL **UPDATE**.  Les colonnes répertoriées dans l'instruction **UPDATE** sont établies à partir des membres de données de type champ qui ont été modifiés.  
  
    3.  **Update** valide les modifications — exécution de l'instruction **UPDATE** — et l'enregistrement est modifié sur la source de données, mais non validé si une transaction est en cours \(consultez [Transaction : exécution d'une transaction dans un recordset \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) pour plus d'informations sur la façon dont la transaction affecte la mise à jour\).  ODBC conserve une copie de l'enregistrement, qui change également.  
  
    4.  Contrairement à `AddNew`, **Edit** ne restaure pas l'enregistrement stocké.  L'enregistrement modifié demeure en place comme enregistrement courant.  
  
    > [!CAUTION]
    >  Lorsque vous vous préparez à modifier un recordset en appelant **Update**, prenez soin que le recordset comporte toutes les colonnes composant la clé primaire de la table \(ou toutes les colonnes d'un index unique sur la table, ou un nombre suffisant de colonnes pour identifier la ligne de façon unique\).  Dans certains cas, l'infrastructure ne peut utiliser que les colonnes sélectionnées dans le recordset pour identifier l'enregistrement de la table à modifier.  Sans toutes les colonnes nécessaires, plusieurs enregistrements peuvent être modifiés dans la table.  Dans ce cas, l'infrastructure lève une exception quand vous appelez **Update**.  
  
    > [!TIP]
    >  Si vous appelez `AddNew` ou **Edit** après avoir déjà appelé l'une ou l'autre des fonctions mais avant d'appeler **Update**, le tampon d'édition est actualisé avec l'enregistrement stocké, en remplacement du nouvel enregistrement ou de l'enregistrement modifié en cours.  Ce comportement vous fournit un moyen d'interrompre une fonction `AddNew` ou **Edit** et d'en commencer une nouvelle : si vous établissez que l'enregistrement en cours est erroné, il vous suffit d'appeler de nouveau **Edit** ou `AddNew`.  
  
##  <a name="_core_deleting_a_record"></a> Suppression d'un enregistrement  
 La suppression d'un enregistrement du recordset nécessite d'accéder à l'enregistrement et d'appeler la fonction membre [Delete](../Topic/CRecordset::Delete.md) du recordset.  Contrairement à `AddNew` et **Edit**, **Delete** n'appelle pas la fonction **Update**.  
  
 Comme condition préalable de l'appel de **Delete**, le recordset doit être modifiable et positionné sur un enregistrement.  Les fonctions membres `CanUpdate`, `IsBOF`, `IsEOF` et `IsDeleted` permettent de définir ces conditions.  
  
 Lorsque vous appelez **Delete** :  
  
-   Si votre pilote ODBC prend en charge la fonction API ODBC **::SQLSetPos**, MFC utilise la fonction pour supprimer l'enregistrement dans la source de données.  L'utilisation de **::SQLSetPos** est également plus efficace que celle de SQL.  
  
     ou  
  
-   S'il n'est pas possible d'utiliser **::SQLSetPos**, MFC procède de la manière suivante :  
  
    1.  L'enregistrement actif présent dans le tampon d'édition n'est pas sauvegardé comme dans `AddNew` et **Edit**.  
  
    2.  **Delete** construit l'instruction SQL **DELETE** qui supprime l'enregistrement.  
  
         L'enregistrement courant du tampon d'édition n'est pas sauvegardé comme dans `AddNew` ou **Edit**.  
  
    3.  **Delete** valide la suppression — exécution de l'instruction **DELETE**.  L'enregistrement est marqué comme supprimé dans la source de données et, si l'enregistrement est un instantané, dans ODBC.  
  
    4.  Les valeurs de l'enregistrement supprimé se trouvent toujours dans les membres de données de type champ de recordset, mais les membres de données de type champ sont marqués comme Null et la fonction membre du recordset `IsDeleted` retourne une valeur différente de zéro.  
  
    > [!NOTE]
    >  Après la suppression d'un enregistrement, vous devez accéder par défilement à un autre enregistrement pour remplir à nouveau le tampon d'édition avec les données du nouvel enregistrement.  Un nouvel appel de **Delete** ou l'appel de **Edit** constitue une erreur.  
  
 Pour plus d'informations sur les instructions SQL utilisées dans les opérations de mise à jour, consultez [SQL](../../data/odbc/sql.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : informations complémentaires sur les mises à jour \(ODBC\)](../../data/odbc/recordset-more-about-updates-odbc.md)   
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)
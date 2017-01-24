---
title: "Assistant Consommateur OLE DB ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.consumer.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Consommateur OLE DB ATL"
  - "projets ATL, ajouter des consommateurs OLE DB ATL"
  - "chaînes de connexion (C++), consommateurs OLE DB"
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Consommateur OLE DB ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'Assistant Consommateur OLE DB ATL permet de définir une classe de consommateur OLE DB avec les liaisons de données nécessaires pour accéder à la source de données spécifiée, par le biais du fournisseur OLE DB indiqué.  
  
> [!NOTE]
>  Cet Assistant nécessite que vous cliquiez sur le bouton **Source de données** pour sélectionner une source de données, avant d'entrer des noms dans les champs `Class` et **Fichier .h**.  
  
## Liste UIElement  
 **Source de données**  
 Le bouton **Source de données** vous permet de définir la source de données spécifiée à l'aide du fournisseur OLE DB indiqué.  Lorsque vous cliquez sur ce bouton, la boîte de dialogue **Propriétés des liaisons de données** s'affiche.  Pour plus d'informations sur la génération de chaînes de connexion et la boîte de dialogue **Propriétés des liaisons de données**, consultez [Vue d'ensemble des API de liaison de données](https://msdn.microsoft.com/en-us/library/ms718102.aspx) dans la documentation du [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
> [!NOTE]
>  Dans les versions précédentes, cliquer sur la touche MAJ et sur le bouton **Source de données** ouvrait une boîte de dialogue d'ouverture de fichier pour vous permettre de sélectionner un fichier .udl.  Cette fonctionnalité n'est plus prise en charge.  
  
 La boîte de dialogue se compose de quatre onglets :  
  
-   Onglet **Fournisseur**  
  
-   Onglet **Connexion**  
  
-   Onglet **Avancé**  
  
-   Onglet **Tous**  
  
     Les informations supplémentaires suivantes décrivent les onglets de la boîte de dialogue **Propriétés des liaisons de données**.  
  
     Cliquez sur **OK** pour terminer.  La boîte de dialogue **Sélectionner l'objet de base de données** s'affiche.  Dans cette boîte de dialogue, sélectionnez le tableau, la vue ou la procédure stockée que le consommateur doit utiliser.  
  
     **Fournisseur**  
     Sélectionnez un fournisseur approprié pour gérer la connexion à la source de données.  Le type de fournisseur est en général déterminé par le type de base de données auquel vous vous connectez.  Cliquez sur le bouton `Next` ou sur l'onglet **Connexion**.  
  
     **Connexion**  
     Le contenu de cet onglet dépend du fournisseur que vous avez sélectionné.  Bien qu'il existe de nombreux types de fournisseurs, cette section couvre les connexions pour les deux plus courants : données SQL et ODBC.  Les autres sont des variations similaires sur les champs décrits ici.  
  
     Pour les données SQL :  
  
    1.  **Sélectionnez ou tapez un nom de serveur :** cliquez sur le menu de la liste déroulante pour afficher tous les serveurs de données stockés sur le réseau, puis sélectionnez\-en un.  
  
    2.  **Entrez des informations pour vous connecter au serveur :** Entrez un nom d'utilisateur et un mot de passe pour ouvrir une session sur le serveur de données.  
  
    3.  **Sélectionnez la base de données sur serveur :** cliquez sur le menu de la liste déroulante pour afficher toutes les bases de données stockées sur le serveur de données, puis sélectionnez\-en une.  
  
         ou  
  
         **Attacher un fichier de base de données en tant que nom de base de données :** pour spécifier un fichier à utiliser comme base de données ; entrez le chemin d'accès explicite.  
  
        > [!NOTE]
        >  La fonctionnalité Autoriser l'enregistrement du mot de passe de la boîte de dialogue Propriétés des liaisons de données présente un problème de sécurité.  Dans « Entrez les informations de connexion au serveur », il y a deux cases d'option :  
  
         **Utiliser la sécurité intégrée de Windows NT**  
  
         **Utiliser un nom d'utilisateur et un mot de passe spécifiques**  
  
         Si vous sélectionnez **Utiliser un nom d'utilisateur et un mot de passe spécifiques**, vous avez la possibilité d'enregistrer le mot de passe \(à l'aide de la case à cocher « Autoriser l'enregistrement du mot de passe »\). Cependant, cette option n'est pas sécurisée.  Il est recommandé de sélectionner **Utiliser la sécurité intégrée de Windows NT** ; cette option est sécurisée car elle chiffre le mot de passe.  
  
         Il peut y avoir des situations dans lesquelles vous souhaitez sélectionner "Autoriser l'enregistrement du mot de passe". Par exemple, si vous libérez une bibliothèque avec une solution privée de la base de données, vous ne devez pas accéder à la base de données directement mais plutôt employer une application intermédiaire pour vérifier l'utilisateur \(via les schémas d'authentification que vous sélectionnez\), puis limiter le tri des données disponibles pour l'utilisateur.  
  
         Pour les données ODBC :  
  
         1.  **Spécifier la source des données :** vous pouvez utiliser un nom de source de données ou une chaîne de connexion.  
  
         **Utilisez Nom de la source de données :** cette liste déroulante affiche les sources de données stockées dans votre ordinateur.  Vous pouvez installer des sources de données d'avance à l'aide [ODBC Data Source Administrator](!Alink("dasdkODBCDataSourceAdmin")).\-ou\-**\*\*\* Use connection string: \*\*\*** Soit vous entrez une chaîne de connexion que vous avez déjà obtenue, ou vous cliquez sur le bouton **Générer** ; la boîte de dialogue **\*\*\* Select Data Source \*\*\*** apparaît.  Sélectionnez un fichier ou une source de données de l'ordinateur, puis cliquez sur **OK**.  
  
        > [!NOTE]
        >  Vous pouvez obtenir une chaîne de connexion en affichant les propriétés d'une connexion existante dans l'explorateur de serveurs, ou vous pouvez créer une connexion en double\-cliquant sur **Ajouter une connexion** dans l'explorateur de serveurs.  
  
         2.  **Entrez des informations pour vous connecter au serveur :** Entrez un nom d'utilisateur et un mot de passe pour ouvrir une session sur le serveur de données.  
  
         3.  Entrez le catalogue initial à utiliser.  
  
         4.  Cliquez sur **Tester la connexion** ; si le test est réussi, cliquez sur **OK**.  Dans le cas contraire, vérifiez vos informations de connexion, essayez une autre base de données ou tentez un autre serveur de données.  
  
     **Avancé**  
     **Network settings:** Spécifient [Impersonation level](!Alink("_com_Impersonation_Levels")) \(le niveau d'emprunt d'identité que le serveur est autorisé à utiliser en empruntant l'identité du client ; correspond directement à des niveaux d'emprunt d'identité RPC\) et au **Protection level** \(le niveau de protection des données envoyées entre le client et le serveur ; correspond directement à des niveaux de sécurité RPC\).  
  
     **Autre :** dans **Connect timeout**, spécifiez le nombre de secondes d'inactivité autorisées avant l'expiration.  Dans **Autorisations d'accès**, spécifiez les autorisations d'accès sur la connexion de données.  
  
     Pour plus d'informations sur les propriétés avancées d'initialisation, reportez\-vous à la documentation de chaque fournisseur OLE DB.  
  
     **Tous**  
     Cet onglet affiche un résumé des propriétés d'initialisation pour la source de données et la connexion que vous avez spécifiées.  Vous pouvez modifier ces valeurs.  
  
     Cliquez sur **OK** pour terminer.  La boîte de dialogue **Sélectionner l'objet de base de données** s'affiche.  Dans cette boîte de dialogue, sélectionnez le tableau, la vue ou la procédure stockée que le consommateur doit utiliser.  
  
 `Class`  
 Une fois que vous avez sélectionné une source de données, cette zone contient un nom de classe par défaut basé sur la table ou la procédure stockée que vous avez sélectionnée \(consultez **Sélectionner la source de données** ci\-dessous\).  Vous pouvez modifier le nom de la classe.  
  
 **fichier .h**  
 Une fois que vous avez sélectionné une source de données, cette zone contient un nom de classe d'en\-tête par défaut basé sur la table ou la procédure stockée que vous avez sélectionnée \(consultez **Sélectionner la source de données** ci\-dessous\).  Vous pouvez modifier le nom du fichier d'en\-tête ou sélectionner un fichier d'en\-tête existant.  
  
 **Avec attributs**  
 Cette option indique si l'Assistant crée des classes de consommateur à l'aide d'attributs ou de déclarations de modèle.  Lorsque vous sélectionnez cette option, l'Assistant utilise des attributs au lieu des déclarations de modèle \(il s'agit de l'option par défaut\).  Lorsque vous désélectionnez cette option, l'Assistant utilise des déclarations de modèle à la place des attributs.  
  
-   Si vous sélectionnez un **Type** de consommateur de Table, l'Assistant utilise les attributs `db_source` et **db\_table** pour créer les déclarations de la table et de la classe d'accesseur de la table et utilise **db\_column** pour créer le mappage de colonnes, par exemple :  
  
    ```  
    // Inject table class and table accessor class declarations  
    [  
        db_source("<initialization_string>"),  
        db_table("dbo.Orders")  
    ]  
    ...  
    // Column map  
        [ db_column(1, status=m_dwOrderIDStatus,         length=m_dwOrderIDLength) ] LONG m_OrderID;  
        [ db_column(2, status=m_dwCustomerIDStatus,         length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
        ...  
    ```  
  
     au lieu d'utiliser la classe de modèle `CTable` pour déclarer la table et la classe d'accesseur de la table, et les macros BEGIN\_COLUMN\_MAP et END\_COLUMN\_MAP pour créer le mappage de colonnes, par exemple :  
  
    ```  
    // Table accessor class  
    class COrdersAccessor;  
    // Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor> >;  
    ...  
    // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor)  
        COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID,         m_dwOrderIDLength, m_dwOrderIDStatus)  
        COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID,         m_dwCustomerIDLength, m_dwCustomerIDStatus)  
        ...  
    END_COLUMN_MAP()  
    ```  
  
-   Si vous sélectionnez un **Type** de consommateur de Command, l'Assistant utilise les attributs `db_source` et **db\_command**, ainsi que **db\_column** pour créer le mappage de colonnes, par exemple :  
  
    ```  
    [  
        db_source("<initialization_string>"),  
        db_command("SQL_command")  
    ]  
    ...  
    // Column map using db_column is the same as for consumer type of 'table'  
    ```  
  
     au lieu d'utiliser les déclarations de la commande et de la classe d'accesseur de la commande dans le fichier .h de la classe Command, par exemple :  
  
    ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor> >;  
    ...  
    // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as  
    // for consumer type of 'table'  
    ```  
  
 Consultez [Basic Mechanics of Attributes](../../windows/basic-mechanics-of-attributes.md) pour plus d'informations.  
  
 **Tapez**  
 Activez l'une de ces cases d'option pour spécifier si la classe de consommateur est dérivée de `CTable` ou de `CCommand`.  
  
 **Table**  
 Sélectionnez cette option si vous voulez utiliser `CTable` ou **db\_table** pour créer les déclarations de classe de table et d'accesseur de table.  
  
 **Commande**  
 Sélectionnez cette option si vous voulez utiliser `CCommand` ou **db\_command** pour créer les déclarations de classe de commande et d'accesseur de commande.  Il s'agit du paramètre défini par défaut.  
  
 **Prise en charge**  
 Activez les cases à cocher pour spécifier les types de mises à jour prises en charge par le consommateur \(la valeur par défaut correspond à aucune prise en charge\).  Chacune des options suivantes définit [DBPROP\_IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715892.aspx) et les entrées adéquates pour [DBPROP\_UPDATABILITY](https://msdn.microsoft.com/en-us/library/ms722676.aspx) dans le mappage de la propriété Set.  
  
 **Change**  
 Spécifie que le consommateur prend en charge les mises à jour des données de ligne dans le jeu de lignes.  
  
 **Insert**  
 Spécifie que le consommateur prend en charge l'insertion de lignes dans le jeu de lignes.  
  
 **Supprimer**  
 Spécifie que le consommateur prend en charge la suppression de lignes dans le jeu de lignes.  
  
## Voir aussi  
 [ATL OLE DB Consumer](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Chaînes de connexion et liaisons de données \(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms718376.aspx)
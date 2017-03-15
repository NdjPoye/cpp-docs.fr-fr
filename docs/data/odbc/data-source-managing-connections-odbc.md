---
title: "Source de donn&#233;es&#160;: gestion des connexions (ODBC) | Microsoft Docs"
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
  - "chaînes de connexion (C++), généraliser"
  - "connexions (C++), source de données"
  - "sources de données (C++), connecter à"
  - "connexions de base de données (C++), créer"
  - "connexions de base de données (C++), classes ODBC MFC"
  - "bases de données (C++), connecter à"
  - "déconnecter de sources de données"
  - "généraliser les chaînes de connexion"
  - "GetDefaultConnect (méthode)"
  - "ODBC (C++), déconnecter de sources de données"
  - "ODBC (connexions) (C++), configurer"
  - "ODBC (connexions) (C++), connecter à une source de données"
  - "ODBC (connexions) (C++), déconnexion"
  - "ODBC (sources de données) (C++), connexions"
  - "ODBC (sources de données) (C++), environnements multi-utilisateurs"
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Source de donn&#233;es&#160;: gestion des connexions (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Cette rubrique explique :  
  
-   [Comment configurer une source de données](#_core_configuring_a_data_source)  
  
-   [Comment un environnement multi\-utilisateur affecte une source de données et ses recordsets](#_core_working_in_a_multiuser_environment)  
  
-   [Pourquoi généraliser une chaîne de connexion à une source de données](#_core_generalizing_the_connection_string)  
  
-   [Comment se connecter à une source de données](#_core_connecting_to_a_specific_data_source)  
  
-   [Comment se déconnecter d'une source de données](#_core_disconnecting_from_a_data_source)  
  
-   [Comment réutiliser un objet CDatabase](#_core_reusing_a_cdatabase_object)  
  
 La connexion à une source de données signifie l'établissement de communications avec un système de gestion de base de données \(SGBD\) pour accéder aux données.  Lorsque vous vous connectez à une source de données à partir d'une application par le biais d'un pilote ODBC, le pilote établit la connexion pour vous, localement ou via un réseau.  
  
 Vous pouvez vous connecter à toute source de données pour laquelle vous possédez un pilote ODBC.  Les utilisateurs de votre application doivent également disposer du même pilote ODBC pour leur source de données.  Pour plus d'informations sur la redistribution de pilotes ODBC, consultez [Redistribution des composants ODBC à vos clients](../../data/odbc/redistributing-odbc-components-to-your-customers.md).  
  
##  <a name="_core_configuring_a_data_source"></a> Configuration d'une source de données  
 L'Administrateur ODBC est utilisé pour configurer vos sources de données.  Vous pouvez également utiliser l'Administrateur ODBC après l'installation pour ajouter ou supprimer des sources de données.  Lorsque vous créez des applications, vous pouvez diriger vos utilisateurs vers l'Administrateur ODBC pour leur permettre d'ajouter des sources de données, ou créer cette fonctionnalité dans votre application en effectuant des appels d'installation ODBC directs.  Pour plus d'informations, consultez [Administrateur ODBC](../../data/odbc/odbc-administrator.md).  
  
 Vous pouvez utiliser un fichier Excel comme source de données que vous devez configurer afin qu'il soit enregistré et qu'il apparaisse dans la boîte de dialogue **Source de données**.  
  
#### Pour utiliser un fichier Excel comme source de données  
  
1.  Configurez le fichier avec l'Administrateur de source de données ODBC.  
  
2.  Sous l'onglet **DSN fichier**, cliquez sur **Ajouter**.  
  
3.  Dans la boîte de dialogue **Créer une nouvelle source de données**, sélectionnez un pilote Excel, puis cliquez sur **Suivant**.  
  
4.  Cliquez sur **Parcourir** et sélectionnez le nom du fichier à utiliser comme source de données.  
  
> [!NOTE]
>  Vous devrez peut\-être sélectionner **Tous les fichiers** dans le menu déroulant pour afficher tous les fichiers .xls.  
  
1.  Cliquez sur **Suivant**, puis sur **Terminer**.  
  
2.  Dans la boîte de dialogue **Installation ODBC pour Microsoft Excel**, sélectionnez la version et le classeur de la base de données.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> Utilisation dans un environnement multi\-utilisateur  
 Si plusieurs utilisateurs sont connectés à une source de données, ils peuvent modifier les données lorsque vous les manipulez dans vos recordsets.  De même, vos modifications peuvent affecter les recordsets des autres utilisateurs.  Pour plus d'informations, consultez [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) et [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_generalizing_the_connection_string"></a> Généralisation de la chaîne de connexion  
 Les Assistants utilisent une chaîne de connexion par défaut pour établir une connexion à une source de données.  Utilisez cette connexion pour afficher des tables et colonnes lorsque vous développez votre application.  Cependant, cette chaîne de connexion par défaut peut ne pas convenir aux connexions à la source de données de vos utilisateurs via votre application.  Par exemple, leur source de données et le chemin d'accès de son emplacement peuvent être différents de ceux qui ont été utilisés lors du développement de votre application.  Dans ce cas, vous devez réimplémenter la fonction membre [CRecordset::GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md) de façon plus générique et abandonner l'implémentation de l'Assistant.  Par exemple, utilisez l'une des approches suivantes :  
  
-   Enregistrez et gérez les chaînes de connexion en utilisant l'Administrateur ODBC.  
  
-   Éditez la chaîne de connexion et retirez le nom de la source de données.  La structure fournit ODBC comme source de données ; au moment de l'exécution, ODBC affiche une boîte de dialogue vous invitant à entrer le nom de la source de données ainsi que d'autres informations de connexion requises.  
  
-   N'entrez que le nom de la source de données.  ODBC vous demande l'ID utilisateur et le mot de passe, le cas échéant.  Par exemple, la chaîne de connexion ressemble à l'exemple ci\-dessous avant la généralisation :  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     Cette chaîne de connexion spécifie une connexion approuvée, qui utilise la sécurité intégrée de Windows NT.  Il convient d'éviter de coder de manière irréversible un mot de passe, ou de spécifier un mot de passe vide puisque cela compromet sérieusement la sécurité.  Vous pouvez plutôt attribuer à `GetDefaultConnect` une nouvelle chaîne de connexion afin qu'elle demande un ID utilisateur et un mot de passe.  
  
    ```  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> Connexion à une source de données spécifique  
 Pour vous connecter à une source de données spécifique, votre source de données doit déjà être configurée à l'aide de l'[Administrateur ODBC](../../data/odbc/odbc-administrator.md).  
  
#### Pour vous connecter à une source de données spécifique  
  
1.  Construisez un objet `CDatabase`.  
  
2.  Appelez sa fonction membre `OpenEx` ou **Open**.  
  
 Pour plus d'informations sur la spécification d'une source de données autre que celle que vous avez spécifiée à l'aide d'un Assistant, consultez [CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md) ou [CDatabase::Open](../Topic/CDatabase::Open.md) dans *MFC Reference*.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> Déconnexion d'une source de données  
 Vous devez fermer tous les recordsets ouverts avant d'appeler la fonction membre **Close** de `CDatabase`.  Dans les recordsets associés à l'objet `CDatabase` que vous voulez fermer, toutes les instructions `AddNew` ou **Edit** et toutes les transactions en attente sont annulées.  
  
#### Pour vous déconnecter d'une source de données  
  
1.  Appelez la fonction membre [Close](../Topic/CDatabase::Close.md) de l'objet `CDatabase`.  
  
2.  Détruisez l'objet, sauf si vous voulez le réutiliser.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> Réutilisation d'un objet CDatabase  
 Vous pouvez réutiliser un objet `CDatabase` après une déconnexion, que ce soit pour vous reconnecter à la même source de données ou pour vous connecter à une source de données différente.  
  
#### Pour réutiliser un objet CDatabase  
  
1.  Fermez la connexion initiale de l'objet.  
  
2.  Plutôt que de détruire l'objet, appelez à nouveau sa fonction membre `OpenEx` ou **Open**.  
  
## Voir aussi  
 [Source de données \(ODBC\)](../../data/odbc/data-source-odbc.md)   
 [Source de données : détermination du schéma de la source de données \(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)
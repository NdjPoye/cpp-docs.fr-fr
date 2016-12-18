---
title: "TN054&#160;: appel de DAO directement pendant l&#39;utilisation des classes DAO MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dao"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (Data Access Objects), et MFC"
  - "DAO (Data Access Objects), appeler directement"
  - "DAO (Data Access Objects), sécurité"
  - "MFC (C++), DAO et"
  - "mots de passe (C++), appeler DAO"
  - "sécurité (MFC)"
  - "sécurité (MFC), DAO"
  - "TN054"
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN054&#160;: appel de DAO directement pendant l&#39;utilisation des classes DAO MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dans Visual C\+\+ .NET, les Assistants et l'environnement Visual C\+\+ ne prennent plus en charge DAO \(même si les classes DAO sont incluses et que vous pouvez toujours les utiliser\).  Microsoft vous recommande d'utiliser les [Modèles OLE DB](../data/oledb/ole-db-templates.md) ou [ODBC et MFC](../data/odbc/odbc-and-mfc.md) pour vos nouveaux projets.  Vous ne devez utiliser DAO que dans les applications existantes.  
  
 En utilisant les classes de bases de données DAO de MFC, il peut y avoir des cas où il est nécessaire d'utiliser DAO directement.  Généralement, ce n'est pas le cas, mais MFC a fourni des mécanismes d'assistance pour faciliter le fait de rendre les appels directs à DAO simples quand on combine l'utilisation de classes MFC avec les appels directs de DAO.  Effectuer des appels directs de DAO des méthodes de l'objet DAO MFC\-managé doit nécessiter quelques lignes de code seulement.  Si vous devez créer et utiliser des objets DAO qui ne sont *pas* gérés par MFC, vous devez effectuer un peu plus de travail en appelant **Release** sur l'objet.  Cette note technique explique quand vous pouvez appeler directement DAO, ce que les programmes d'assistance de MFC peuvent faire pour vous aider, et comment utiliser les interfaces de DAO OLE.  Enfin, cette remarque fournit des fonctions d'exemple qui indiquent comment appeler directement DAO pour les fonctionnalités de sécurité de DAO.  
  
## quand faire des appels DAO directs ;  
 Les cas les plus courants pour effectuer des appels directs de DAO se produisent lorsque les collections doivent être actualisées ou lorsque vous implémentez les fonctionnalités non incluses par MFC.  La fonctionnalité la plus significative non exposée par MFC est la sécurité.  Si vous souhaitez implémenter les fonctionnalités de sécurité, vous devez utiliser des objets utilisateurs et groupes de DAO directement.  Outre la sécurité, il existe quelques autres fonctionnalités de DAO non prises en charge par MFC.  Cela inclut le clonage d'ensemble d'enregistrements et les fonctionnalités de réplication de base de données ainsi que certaines améliorations récentes de DAO.  
  
## Une vue d'ensemble de l'implémentation de MFC et DAO  
 L'encapsulation de DAO par MFC permet une utilisation de DAO plus facile en gérant plusieurs détails de sorte que vous n'avez pas à vous soucier de petites opérations.  Cela inclut l'initialisation OLE, la création et la gestion des objets DAO \(notamment les objets de collection\), la vérification des erreurs, et le fait de fournir une interface fortement typée et plus simple \(aucun argument **VARIANT** ou `BSTR` \).  Vous pouvez effectuer des appels directs à DAO et encore bénéficier de ces fonctionnalités.  Tout ce que le code doit faire consiste à appeler **Release** pour tous les objets créés par des appels directs de DAO et de ne *pas* modifier les pointeurs d'interface auxquels MFC peut avoir recours en interne.  Par exemple, ne modifiez pas le membre **m\_pDAORecordset** d'un objet ouvert `CDaoRecordset` sauf si vous connaissez *toutes* les conséquences internes.  Vous pouvez, toutefois, utiliser l'interface **m\_pDAORecordset** pour appeler directement DAO pour obtenir la collection de champs.  Dans ce cas le membre **m\_pDAORecordset** n'est pas modifié.  Vous devez simplement appeler **Release** sur l'objet de collection de champs lorsque vous en avez terminé avec l'objet.  
  
## Description des programmes d'assistance pour rendre les appels de DAO plus faciles  
 Les programmes d'assistance fournis pour rendre les appels DAO plus faciles sont les mêmes programmes d'assistance qui sont utilisés en interne dans les classes de base de données DAO de MFC.  Ces programmes d'assistance sont utilisés pour vérifier les codes de retour lors d'un appel direct de DAO, d'un enregistrement de la sortie de débogage, d'une vérification des erreurs attendues, et de la levée des exceptions appropriées si nécessaire.  Il existe deux fonctions d'assistance sous\-jacentes et quatre macros qui mappent vers un de ces deux programmes d'assistance.  La meilleure explication sera de lire le code.  Consultez **DAO\_CHECK**, **DAO\_CHECK\_ERROR**, **DAO\_CHECK\_MEM**, et **DAO\_TRACE** dans AFXDAO.H pour afficher les macros, et voir **AfxDaoCheck** et **AfxDaoTrace** dans DAOCORE.CPP.  
  
## En utilisant les interfaces de DAO OLE  
 Les interfaces OLE pour chaque objet de la hiérarchie d'objets DAO sont définies dans le fichier d'en\-tête DBDAOINT.H, qui se trouve dans le répertoire \\Program Files\\Microsoft Visual Studio .NET 2003\\VC7\\include.  Ces interfaces sont les méthodes qui vous permettent de manipuler la hiérarchie entière de DAO.  
  
 Pour plusieurs méthodes des interfaces DAO, vous devez manipuler un objet `BSTR` \(chaîne de longueur\-préfixée utilisée dans l'automation OLE\).  L'objet `BSTR` est généralement inclus dans le type de données **VARIANT**.  La classe MFC `COleVariant` elle\-même hérite du type de données **VARIANT**.  Selon que vous générez votre projet pour ANSI ou Unicode, les interfaces DAO retourneront des `BSTR` ANSI ou Unicode.  Deux macros, **V\_BSTR** et **V\_BSTRT**, sont utiles pour vérifier que l'interface DAO obtient le `BSTR` du type attendu.  
  
 **V\_BSTR** extrait le membre **bstrVal** d'un `COleVariant`.  La macro est généralement utilisée lorsque vous devez transmettre le contenu d'un `COleVariant` à une méthode d'interface DAO.  Le fragment de code suivant montre les déclarations et l'utilisation réelle pour deux méthodes de l'interface utilisateur de DAO DAOUser interface qui tirent parti de la macro **V\_BSTR** :  
  
```  
COleVariant varOldName;  
COleVariant varNewName( _T("NewUser"), VT_BSTRT );  
  
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
  
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
  
DAO_CHECK( pUser->get_Name( &V_BSTR ( &varOldName ) ));  
DAO_CHECK( pUser->put_Name( V_BSTR ( &varNewName ) ));  
```  
  
 Notez que l'argument `VT_BSTRT` spécifié dans le constructeur `COleVariant` ci\-dessus garantit qu'il y aura une `BSTR`ANSI dans `COleVariant` si vous créez une version ANSI de votre application et une `BSTR` Unicode pour une version Unicode de votre application.  C'est ce que DAO attend.  
  
 L'autre macro, **V\_BSTRT** extrait un membre **bstrVal** ANSI ou Unicode de `COleVariant` selon le type de génération \(ANSI ou Unicode\).  Le code suivant montre comment extraire la valeur `BSTR` d'un`COleVariant` dans une  `CString`:  
  
```  
COleVariant varName( _T( "MyName" ), VT_BSTRT );  
CString str = V_BSTRT( &varName );  
```  
  
 La macro **V\_BSTRT**, ainsi que d'autres techniques pour ouvrir les autres types stockés dans `COleVariant`, est illustrée dans l'exemple de DAOVIEW.  En particulier, cette traduction est exécutée dans la méthode **CCrack::strVARIANT**.  Cette méthode, si possible, convertit la valeur d'un `COleVariant` en une instance de `CString`.  
  
## Exemple simple d'un appel direct à DAO  
 Les situations peuvent survenir lorsque cela est nécessaire pour actualiser les objets de collection de DAO sous\-jacents.  Normalement, cela ne doit pas être nécessaire, mais il s'agit d'une procédure simple si nécessaire.  Un exemple de lorsqu'une collection peut être actualisée est quand on opère dans un environnement multi\-utilisateur avec plusieurs utilisateurs créant de nouveaux tabledefs.  Dans ce cas la collection de tabledefs peut devenir obsolète.  Pour actualiser la collection, vous devez simplement appeler la méthode **Actualiser** d'objet de collection spécifique et rechercher les erreurs :  
  
```  
DAO_CHECK( pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh( ) );  
```  
  
 Notez qu'actuellement toutes les interfaces d'objet de collection de DAO sont des détails d'implémentation non documentés sur les classes de bases de données DAO de MFC.  
  
## L'utilisation de DAO directement pour les fonctionnalités de sécurité de DAO  
 Les classes de bases de données DAO de MFC n'encapsulent pas les fonctionnalités de sécurité de DAO.  Vous devez appeler des méthodes d'interfaces DAO pour utiliser certaines fonctionnalités de sécurité de DAO.  La fonction suivante définit la base de données système puis modifie le mot de passe d'utilisateur.  Cette fonction appelle trois autres fonctions, qui sont ensuite définies.  
  
```  
void ChangeUserPassword( )  
{  
   // Specify path to the Microsoft Access  
   // system database  
   CString strSystemDB =   
     _T( "c:\\Program Files\\MSOffice\\access\\System.mdw" );  
  
   // Set system database before MFC initilizes DAO  
   // NOTE: An MFC module uses only one instance   
   // of a DAO database engine object. If you have   
   // called a DAO object in your application prior   
   // to calling the function below, you must call   
   // AfxDaoTerm to destroy the existing database   
   // engine object. Otherwise, the database engine   
   // object already in use will be reused, and setting  
   // a system datbase will have no effect.  
   //  
   // If you have used a DAO object prior to calling   
   // this function it is important that DAO be   
   // terminated with AfxDaoTerm since an MFC  
   // module only gets one copy of the database engine   
   // and that engine will be reused if it hasn't been   
   // terminated. In other words, if you do not call   
   // AfxDaoTerm and there is currently a database   
   // initialized, setting the system database will   
   // have no affect.  
  
   SetSystemDB( strSystemDB );  
  
   // User name and password manually added  
   // by using Microsoft Access  
   CString strUserName = _T( "NewUser" );  
   CString strOldPassword = _T( "Password" );  
   CString strNewPassword = _T( "NewPassword" );  
  
   // Set default user so that MFC will be able  
   // to log in by default using the user name and   
   // password from the system database  
   SetDefaultUser( strUserName, strOldPassword );  
  
   // Change the password. You should be able to  
   // call this function from anywhere in your   
   // MFC application  
   ChangePassword( strUserName, strOldPassword,   
                   strNewPassword );  
  
   .  
   .  
   .  
  
}  
```  
  
 Les quatre exemples suivants montrent comment effectuer les tâches suivantes :  
  
-   Définissez les bases de données DAO système \(.MDW\).  
  
-   Définissez l'utilisateur et le mot de passe par défaut.  
  
-   Modifiez le mot de passe d'un utilisateur.  
  
-   Modifiez le mot de passe d'un fichier de .MDB.  
  
### Définir la base de données système  
 Vous trouverez ci\-dessous un exemple de fonction pour définir la base de données système qui sera utilisée par une application.  Cette fonction doit être appelée avant que tous les appels de DAO soient faits.  
  
```  
// Set the system database that the   
// DAO database engine will use  
  
void SetSystemDB( CString & strSystemMDB )  
{  
   COleVariant varSystemDB( strSystemMDB, VT_BSTRT );  
  
   // Initialize DAO for MFC  
   AfxDaoInit( );  
   DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  
   ASSERT( pDBEngine != NULL );  
  
   // Call put_SystemDB method to set the   
   // system database for DAO engine  
   DAO_CHECK( pDBEngine->put_SystemDB( varSystemDB.bstrVal ) );  
}  
```  
  
### Définition de l'utilisateur et du mot de passe par défaut.  
 Pour définir l'utilisateur et le mot de passe par défaut pour une base de données système, utilisez la fonction suivante :  
  
```  
void SetDefaultUser(CString & strUserName, CString & strPassword)  
{  
  COleVariant varUserName( strUserName, VT_BSTRT );  
  COleVariant varPassword( strPassword, VT_BSTRT );  
  
  DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  ASSERT( pDBEngine != NULL );  
  
  // Set default user:  
  DAO_CHECK( pDBEngine->put_DefaultUser( varUserName.bstrVal ) );  
  
  // Set default password:  
  DAO_CHECK( pDBEngine->put_DefaultPassword( varPassword.bstrVal ) );  
}  
```  
  
### Modifier un mot de passe  
 Pour modifier un mot de passe, utilisez la fonction suivante :  
  
```  
void ChangePassword( CString &strUserName,   
                     CString &strOldPassword,   
                     CString &strNewPassword )  
{  
   // Create (open) a workspace  
   CDaoWorkspace wsp;  
   CString strWspName = _T( "Temp Workspace" );  
  
   wsp.Create( strWspName, strUserName,  
               strOldPassword );  
   wsp.Append( );  
  
   // Determine how many objects there are  
   // in the Users collection  
   short nUserCount;  
   short nCurrentUser;  
   DAOUser *pUser  = NULL;  
   DAOUsers *pUsers = NULL;  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUser object:  
   DAO_CHECK( wsp.m_pDAOWorkspace->get_Users( &pUsers ) );  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUsers object  
    DAO_CHECK( pUsers->get_Count( &nUserCount ) );  
  
   // Traverse through the list of users   
   // and change password for the userid  
   // used to create/open the workspace  
   for( nCurrentUser = 0; nCurrentUser < nUserCount;  
        nCurrentUser++ )  
   {  
       COleVariant varIndex( nCurrentUser, VT_I2 );  
       COleVariant varName;  
  
       // Retrieve information for user nCurrentUser  
       DAO_CHECK( pUsers->get_Item( varIndex, &pUser ) );  
  
       // Retrieve name for user nCurrentUser  
       DAO_CHECK( pUser->get_Name( &V_BSTR( &varName ) ) );  
  
       CString strTemp = V_BSTRT( &varName );  
  
       // If there is a match, change the password  
       if( strTemp == strUserName )  
       {  
           COleVariant varOldPwd( strOldPassword,   
                                  VT_BSTRT );  
           COleVariant varNewPwd( strNewPassword,   
                                  VT_BSTRT );  
  
           DAO_CHECK( pUser->NewPassword( V_BSTR( &varOldPwd ),  
                      V_BSTR( &varNewPwd ) ) );  
  
           TRACE( "\t Password is changed\n" );  
       }  
   }  
  
   // Clean up: decrement the usage count  
   // on the OLE objects  
   pUser->Release( );  
   pUsers->Release( );  
  
   wsp.Close( );  
}  
```  
  
### Modifier le mot de passe d'un fichier .MDB.  
 Pour modifier le mot de passe d'un fichier .MDB, utilisez la fonction suivante :  
  
```  
void SetDBPassword( LPCTSTR pDB, LPCTSTR pszOldPassword, LPCTSTR pszNewPassword )  
{  
   CDaoDatabase db;  
   CString strConnect( _T( ";pwd=" ) );  
  
   // the database must be opened as exclusive  
   // to set a password  
   db.Open( pDB, TRUE, FALSE,   
            strConnect + pszOldPassword );  
  
   COleVariant NewPassword( pszNewPassword, VT_BSTRT ),  
               OldPassword( pszOldPassword, VT_BSTRT );  
  
   DAO_CHECK( db.m_pDAODatabase->NewPassword( V_BSTR( &OldPassword ),  
              V_BSTR( &NewPassword ) ) );  
  
   db.Close();  
}  
```  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
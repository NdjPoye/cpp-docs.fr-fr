---
title: "Cr&#233;ation d&#39;un consommateur sans utiliser l&#39;Assistant | Microsoft Docs"
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
  - "consommateurs OLE DB, créer"
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un consommateur sans utiliser l&#39;Assistant
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple suivant suppose que vous ajoutez la prise en charge d'un consommateur OLE DB à un projet ATL existant.  Si vous souhaitez ajouter la prise en charge d'un consommateur OLE DB à une application MFC, vous devez exécuter l'Assistant Application MFC, qui crée la prise en charge nécessaire et appelle les routines MFC indispensables à l'exécution de l'application.  
  
 Pour ajouter la prise en charge du consommateur OLE DB sans utiliser l'Assistant Consommateur OLE DB ATL :  
  
-   Dans votre fichier Stdafx.h, ajoutez les instructions `#include` suivantes :  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 Un consommateur exécute généralement, par programme, la séquence d'opérations suivante :  
  
-   Création d'une classe d'enregistrement utilisateur qui lie les colonnes aux variables locales.  Dans cet exemple, `CMyTableNameAccessor` est la classe d'enregistrement utilisateur \(consultez [Enregistrements utilisateur](../../data/oledb/user-records.md)\).  Cette classe contient le mappage de colonnes et le mappage de paramètres.  Déclaration d'une donnée membre dans la classe d'enregistrement utilisateur pour chaque champ spécifié dans le mappage de colonnes ; pour chacune de ces données membres, déclaration aussi d'une donnée membre d'état et d'une donnée membre de longueur.  Pour plus d'informations, consultez [Données membres de l'état des champs dans les accesseurs générés par l'Assistant](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    >  Si vous écrivez votre propre consommateur, les variables de données doivent précéder les variables d'état et de longueur.  
  
-   Instanciation d'une source de données et d'une session.  Détermination du type d'accesseur et de jeu de lignes à utiliser, puis instanciation d'un jeu de lignes à l'aide de [CCommand](../../data/oledb/ccommand-class.md) ou de [CTable](../../data/oledb/ctable-class.md) :  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor> >  
    ```  
  
-   Appel de **CoInitialize** pour initialiser COM.  Cet appel est habituellement effectué dans le code principal.  Par exemple :  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   Appel de [CDataSource::Open](../../data/oledb/cdatasource-open.md) ou de l'une de ses variantes.  
  
-   Ouverture d'une connexion à la source de données, ouverture de la session, puis ouverture et initialisation du jeu de lignes \(et exécution également, s'il s'agit d'une commande\) :  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   Définition \(facultative\) des propriétés rowset en utilisant `CDBPropSet::AddProperty` et leur passation en tant que paramètre à `rs.Open`.  Pour obtenir un exemple, consultez GetRowsetProperties dans [Méthodes de consommateur générées par l'Assistant](../../data/oledb/consumer-wizard-generated-methods.md).  
  
-   Vous pouvez à présent utiliser le jeu de lignes pour récupérer\/manipuler les données.  
  
-   Une fois l'application terminée, fermeture de la connexion, de la session et du jeu de lignes :  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     Si vous utilisez une commande, vous pouvez si vous le souhaitez appeler `ReleaseCommand` après **Close**.  L'exemple de code [CCommand::Close](../../data/oledb/ccommand-close.md) illustre comment appeler **Close** et `ReleaseCommand`.  
  
-   Appel de **CoUnInitialize** pour initialiser COM.  Cet appel est habituellement effectué dans le code principal.  
  
    ```  
    CoUninitialize();  
    ```  
  
## Voir aussi  
 [Création d'un consommateur OLE DB](../../data/oledb/creating-an-ole-db-consumer.md)
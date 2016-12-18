---
title: "CDataSource::OpenFromFileName | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::OpenFromFileName"
  - "ATL::CDataSource::OpenFromFileName"
  - "OpenFromFileName"
  - "CDataSource.OpenFromFileName"
  - "ATL.CDataSource.OpenFromFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenFromFileName (méthode)"
ms.assetid: c4226de6-59da-4368-9c15-c5afab86f68b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenFromFileName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ouvre une source de données à partir d'un fichier spécifié par le nom de fichier fourni par l'utilisateur.  
  
## Syntaxe  
  
```  
  
        HRESULT OpenFromFileName(   
   LPCOLESTR szFileName    
) throw( );  
```  
  
#### Paramètres  
 `szFileName`  
 \[in\] Nom d'un fichier, généralement un fichier de connexion de source de données au format .UDL.  
  
 Pour plus d'informations sur les fichiers de liaison de données \(fichiers .udl\), consultez [Vue d'ensemble de l'API de liaison de données](https://msdn.microsoft.com/en-us/library/ms718102.aspx) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Valeur de retour  
 `HRESULT` standard.  
  
## Notes  
 Cette méthode ouvre un objet source de données à l'aide des composants de service d'oledb32.dll ; cette DLL contient l'implémentation des fonctionnalités Composants de service, telles que la mise en pool de ressources, l'inscription de transaction automatique, etc.  Pour plus d'informations, consultez « Services OLE DB » dans le Guide de référence du programmeur OLE DB à l'adresse [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)
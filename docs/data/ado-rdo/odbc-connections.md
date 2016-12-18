---
title: "Connexions ODBC | Microsoft Docs"
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
  - "ODBC (connexions), configurer"
  - "ODBC, connectivité"
ms.assetid: c9df2fa6-d9e2-4335-b885-724662968691
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Connexions ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les connexions ODBC sont configurées dans le Panneau de configuration système.  Les connexions ODBC peuvent être établies avec n'importe quelle source de données pour laquelle un pilote ODBC a été installé.  Visual C\+\+ 6.0 ou version ultérieure fournit des pilotes pour les fichiers texte, Access, FoxPro, Paradox, dBASE, Excel, SQL Server et Oracle.  Lorsque vous créez une connexion ODBC, elle reçoit automatiquement un nom de source de données \(DSN, Data Source Name\).  Le DSN est ensuite utilisé pour identifier des connexions dans les contrôles de données, tels que le contrôle de données ADO et le contrôle RemoteData RDO.  
  
 **Connexions OLE DB** Aucun effort supplémentaire n'est nécessaire pour configurer une connexion OLE DB.  Par exemple, si une source de données ODBC est créée, elle est détectée automatiquement le fournisseur OLE DB pour ODBC.  
  
### Pour configurer une source de données ODBC  
  
1.  Cliquez sur **Démarrer**, sur **Paramètres**, puis sur **Panneau de configuration**.  
  
2.  Dans le Panneau de configuration, sélectionnez ODBC 32 bits \(Windows 95 ou 98\) ou ODBC \(Windows NT ou 2000\).  
  
3.  Cliquez sur l'onglet **DSN utilisateur** ou **DSN système**.  L'onglet **DSN utilisateur** permet de créer des noms de sources de données spécifiques à l'utilisateur alors que **DSN système** permet de créer des sources de données disponibles pour tous les utilisateurs.  
  
4.  Cliquez sur **Ajouter** pour afficher une liste de pilotes ODBC installés localement.  
  
5.  Sélectionnez le pilote correspondant au type de méthode d'accès séquentiel indexé \(ISAM\) ou la base de données à laquelle vous voulez vous connecter, puis cliquez sur **Terminer**.  
  
6.  Suivez les instructions propres au pilote.  Après la fermeture, le DSN est prêt à l'emploi.  
  
 Lors de la génération d'un DSN pour certains types de pilotes ODBC, vous devez connaître l'emplacement effectif du fichier.  Par exemple, lors de la création d'un DSN Access, vous devez connaître l'emplacement du fichier .mdb.  Vous devez également avoir un nom d'utilisateur et un mot de passe valides.  Par exemple, le nom d'utilisateur système pour la plupart des systèmes Access est *admin*.  
  
 Lors de la création d'un DSN [Oracle](../../data/ado-rdo/oracle-connections.md), vous devez connaître la chaîne de connexion SQL\*Net.  
  
## Voir aussi  
 [Création de connexions de base de données](../../data/ado-rdo/creating-database-connections.md)
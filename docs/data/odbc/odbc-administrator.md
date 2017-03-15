---
title: "Administrateur ODBC | Microsoft Docs"
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
  - "administration (Administrateur ODBC)"
  - "Administrateur dans ODBC"
  - "pilotes (C++), ODBC"
  - "installer ODBC"
  - "ODBC (C++), Administrateur ODBC"
  - "ODBC (Administrateur) (C++)"
  - "ODBC (sources de données) (C++), Administrateur ODBC"
  - "ODBC (pilotes) (C++), installer"
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Administrateur ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'Administrateur ODBC enregistre et configure les [sources de données](../../data/odbc/data-source-odbc.md) disponibles en local ou sur un réseau.  Les Assistants utilisent les informations fournies par l'Administrateur ODBC pour créer du code dans vos applications afin de connecter vos utilisateurs aux sources de données.  
  
 Pour configurer une source de données ODBC à utiliser avec les classes ODBC MFC ou DAO \(Data Access Object\) MFC, vous devez d'abord enregistrer et configurer la source de données.  Utilisez l'Administrateur ODBC pour ajouter et supprimer des sources de données.  Selon le pilote ODBC, vous pouvez également créer de nouvelles sources de données.  
  
 L'Administrateur ODBC est installé lors du programme d'installation.  Si vous avez choisi l'installation **Personnalisée** et n'avez sélectionné aucun pilote ODBC dans la boîte de dialogue **Options de base de données**, vous devez réexécuter le programme d'installation pour installer les fichiers nécessaires.  
  
 Lors de l'installation, sélectionnez les pilotes ODBC que vous voulez installer.  Le programme d'installation Visual C\+\+ vous permet d'installer ultérieurement des pilotes supplémentaires livrés avec Visual C\+\+.  
  
 Si vous voulez installer des pilotes ODBC qui ne sont pas livrés avec Visual C\+\+, vous devez exécuter le programme d'installation du pilote.  
  
#### Pour installer les pilotes ODBC fournis avec Visual C\+\+  
  
1.  Exécutez le programme d'installation à partir du CD\-ROM Visual C\+\+.  
  
     La boîte de dialogue d'ouverture du programme d'installation apparaît.  
  
2.  Cliquez sur **Suivant** dans chaque boîte de dialogue jusqu'à ce que la boîte de dialogue **Options d'installation** s'affiche.  Sélectionnez **Personnalisée**, puis cliquez sur `Next`.  
  
3.  Désactivez toutes les cases à cocher de la boîte de dialogue **Installation de Microsoft Visual C\+\+** à l'exception de la case à cocher **Options de base de données**, puis cliquez sur **Détails** pour afficher la boîte de dialogue **Options de base de données**.  
  
4.  Désactivez la case à cocher **Objets d'accès aux données Microsoft**, activez la case à cocher **Pilotes ODBC Microsoft**, puis cliquez sur **Détails**.  
  
     La boîte de dialogue **Pilotes ODBC Microsoft** s'affiche.  
  
5.  Sélectionnez les pilotes que vous voulez installer, puis cliquez deux fois sur **OK**.  
  
6.  Cliquez sur **Suivant** dans les boîtes de dialogue qui s'affichent par la suite pour commencer l'installation.  Le programme d'installation vous prévient lorsque l'installation est terminée.  
  
 Dès que les pilotes sont installés, vous pouvez configurer la source de données à l'aide de l'Administrateur ODBC.  L'icône ODBC se trouve dans le Panneau de configuration.  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Source de données \(ODBC\)](../../data/odbc/data-source-odbc.md)
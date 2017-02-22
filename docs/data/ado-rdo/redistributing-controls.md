---
title: "Redistribution des contr&#244;les | Microsoft Docs"
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
  - "ActiveX, contrôles [C++], redistribution"
  - "contrôles redistribuables"
ms.assetid: 32d03b95-d328-4f10-ad9b-f3ebbe03339d
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Redistribution des contr&#244;les
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ .NET fournit des contrôles ActiveX que vous pouvez utiliser dans des applications. Vous pouvez ensuite redistribuer les contrôles en même temps que les applications. Dans la boîte de dialogue **Insérer un contrôle ActiveX**, le fait de mettre en évidence un contrôle provoque l’affichage de son fichier .ocx ou .dll.  
  
 Pour obtenir une liste des contrôles ActiveX redistribuables fournis par Visual C\+\+, consultez le fichier Program Files\\Microsoft Visual Studio .NET 2003\\redist.txt sur le disque 2 du CD\-ROM du produit Visual C\+\+ .NET. Tous les fichiers .ocx du dossier Win\\System sont redistribuables.  
  
 [Contrôles ActiveX MFC : distribution de contrôles ActiveX](../../mfc/mfc-activex-controls-distributing-activex-controls.md) explique comment installer et inscrire des contrôles ActiveX redistribuables.  
  
 [Projets de modules de fusion](http://msdn.microsoft.com/fr-fr/e92e4f85-fba5-45ee-a432-892a956daeb9) explique comment un déploiement Visual Studio .NET gère la redistribution de fichiers via les modules de fusion.  
  
 [Redistribution de fichiers de prise en charge de base de données](../../ide/redistributing-database-support-files.md) explique comment redistribuer des fichiers de prise en charge pour les technologies de base de données présents dans le Kit de développement logiciel \(SDK\) Microsoft Data Access.  
  
 Si votre application utilise un contrôle ActiveX qui se connecte à une base de données, vous devez installer ou effectuer ceci :  
  
-   **DCOM pour Windows.** Vous devez exécuter Dcom98.exe ou Dcom95.exe sur les ordinateurs exécutant des versions de Windows antérieures à Windows 2000. \(Dcom98.exe est destiné à Windows 98 ; Dcom95.exe est destiné à Windows 95.\)  
  
-   **Kit de développement logiciel \(SDK\) MDAC 2.8.** Vous devez installer le Kit de développement logiciel \(SDK\) Microsoft Data Access 2.8 sur l’ordinateur cible. Vous pouvez le télécharger depuis [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=205525](http://go.microsoft.com/fwlink/?LinkId=205525).  
  
-   **Programme de redistribution MDAC 2.8.** Le Kit de développement logiciel \(SDK\) MDAC 2.8 est conçu pour être utilisé avec le programme de redistribution MDAC 2.8 \(MDAC\_TYP.EXE\). Vous pouvez télécharger MDAC\_TYP.EXE depuis [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=164412](http://go.microsoft.com/fwlink/?LinkId=164412).  
  
-   **Répliquer le nom de source de données \(DSN\).** Vous devez aussi répliquer le DSN sur l’ordinateur cible. Vous pouvez le faire par programmation avec des fonctions comme [ConfigDSN](https://msdn.microsoft.com/en-us/library/ms709275.aspx).  
  
## Remarques importantes sur la redistribution de composants  
  
-   **Redistribution de composants DAO.** Microsoft vous recommande d’utiliser Jet 4.0 SP3 \(version 2927.04\) ou ultérieure. Jet 4.0 SP3 est livré avec Windows 2000 et Windows Me. L’utilisation de cette version de Jet réduit le nombre de versions de Jet qui doivent être testées avec votre application.  
  
     Windows XP est livré avec une version du Service Pack de Jet mise à niveau, qui ne fait pas partie des versions antérieures de Windows. Le test de votre application sur Windows XP teste automatiquement la version de Jet qui est livrée avec Windows XP. Vous devez tester les applications DAO sur les deux versions de Jet 4.0 avant de les publier.  
  
     La seule différence dans la version Windows XP est la présence de correctifs pour des problèmes trouvés depuis la publication de Windows 2000. Si les utilisateurs de votre application ne rencontrent pas de problèmes, il n’est pas nécessaire d’effectuer une mise à niveau au\-delà de Jet 4.0 SP3.  
  
-   **Problèmes connus avec les contrôles ActiveX.** Il existe un problème connu avec la création dynamique d’instances de contrôles redistribuables de contrôles ActiveX sur des ordinateurs où Visual C\+\+ n’a pas été installé, comme décrit dans l’article de la Base de connaissances, « PRB : Échec de la création dynamique de contrôles redistribuables » \(Q151804\). Vous pouvez trouver des articles de la Base de connaissances sur le CD\-ROM Bibliothèque MSDN ou à l’adresse [http:\/\/support.microsoft.com](http://support.microsoft.com). Il existe également un problème connu avec le placement de certains contrôles ActiveX sur une boîte de dialogue : vous obtenez une boîte de message indiquant que le contrôle requiert une licence d’utilisation en mode conception, comme décrit dans l’article de la Base de connaissances, « PRB : Licence d’utilisation en mode conception nécessaire pour des contrôles Microsoft ActiveX » \(Q155059\). Vous pouvez trouver des articles de la Base de connaissances sur le CD\-ROM Bibliothèque MSDN ou à l’adresse [http:\/\/support.microsoft.com](http://support.microsoft.com).  
  
-   **Contrôles sous licence Visual Studio.** Les détenteurs d’une licence Visual Studio peuvent redistribuer d’autres contrôles ActiveX spécifiques aux autres outils de développement Visual Studio. Par exemple, le contrôle Chart est distribué avec Visual Basic, qui est également livré dans Visual Studio. Ainsi, si vous utilisez Visual C\+\+ dans le cadre d’une licence Visual Studio, vous pouvez redistribuer le contrôle Chart. Cependant, si vous avez acheté seulement Visual C\+\+, vous n’avez pas de licence pour le redistribuer.  
  
## Voir aussi  
 [Utilisation des contrôles ActiveX](../../data/ado-rdo/using-activex-controls.md)   
 [Contrôles ActiveX MFC : distribution de contrôles ActiveX](../../mfc/mfc-activex-controls-distributing-activex-controls.md)
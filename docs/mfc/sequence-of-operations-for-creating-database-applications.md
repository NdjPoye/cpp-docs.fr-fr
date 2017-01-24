---
title: "Ordre des op&#233;rations pour la cr&#233;ation d&#39;applications de base de donn&#233;es | Microsoft Docs"
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
  - "applications (MFC), base de données"
  - "applications de base de données (C++)"
  - "applications de base de données (C++), créer"
  - "MFC (C++), applications de bases de données"
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ordre des op&#233;rations pour la cr&#233;ation d&#39;applications de base de donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant indique votre rôle et le rôle de .NET Framework dans l'écriture d'applications de l'infrastructure.  
  
> [!NOTE]
>  Dans Visual C\+\+ .NET, les Assistants et l'environnement Visual C\+\+ ne prennent plus en charge DAO \(même si les classes DAO sont incluses et que vous pouvez toujours les utiliser\).  Microsoft recommande l'utilisation d'ODBC pour des nouveaux projets de MFC.  Vous ne devez utiliser DAO que dans les applications existantes.  
  
### créer des applications de bases de données  
  
|Tâche|Vous faites|L'infrastructure fait|  
|-----------|-----------------|---------------------------|  
|Décidez d'utiliser les classes de données de MFC ODBC ou de DAO.|Utilisez ODBC pour les nouveaux projets MFC.  Utilisez DAO pour contenir uniquement des applications existantes.  Pour plus d'informations : [Dois\-je utiliser DAO ou ODBC ?](../data/should-i-use-dao-or-odbc-q.md) Pour obtenir des informations générales, consultez l'article [Programmation de l'accès aux données](../data/data-access-programming-mfc-atl.md).|L'infrastructure fournit des classes qui prennent en charge l'accès aux bases de données.|  
|Créez votre application squelette avec les options de base de données.|Exécutez l'application assistant MFC.  Sélectionnez les options sur la page de prise en charge des bases de données.  Si vous choisissez une option qui crée une vue de l'enregistrement, spécifiez également :<br /><br /> -   Source de données et le nom de la table ou des noms<br />-   Nom ou nom de requête.|L'Application assistant MFC crée des fichiers et spécifie les inclusions nécessaires.  Selon les options que vous spécifiez, les fichiers peuvent inclure une classe d'ensemble d'enregistrements.|  
|Concevez votre formulaire de base de données ou de formes.|Utilisez l'éditeur de boîtes de dialogue de Visual C\+\+ pour placer des contrôles sur les ressources de modèles de la boîte de dialogue pour vos classes d'affichage des enregistrements.|L'Application MFC crée une ressource modèle de la boîte de dialogue vide pour terminer.|  
|Créez la vue de journalisation supplémentaire et les classes de jeu d'enregistrements selon les besoins.|Utilisez l'affichage de classes pour créer les classes et l'éditeur de boîtes de dialogue pour concevoir des vues.|L'affichage de classes crée des fichiers supplémentaires pour vos nouvelles classes.|  
|Créez les objets recordset autant que nécessaire dans votre code.  Utilisez chaque ensemble pour manipuler des enregistrements…|Les jeux sont basés sur les classes dérivées de [CRecordset](../mfc/reference/crecordset-class.md) avec les assistants.|ODBC utilise l'échange des champs \(RFX\) pour échanger des données les données de membre de champ entre la base de données et l'ensemble des enregistrements.  Si vous utilisez une vue de l'enregistrement, les données d'échanges \(DDX\) de l'échange de données de boîtes de dialogue entre l'ensemble d'enregistrements et les contrôles sur la vue de l'enregistrement.|  
|… ou créez un explicite [CDatabase](../mfc/reference/cdatabase-class.md) dans votre code pour chaque base de données que vous souhaitez ouvrir.|Baser vos objets recordset sur les objets de la base de données.|L'objet de la base de données fournit une interface à la source de données.|  
|Colonnes de données de lien à votre recordset dynamique.|Dans ODBC, ajoutez du code à votre classe d'ensemble d'enregistrements dérivées pour gérer la liaison.  Consultez l'article [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
  
## Voir aussi  
 [Génération à partir du Framework](../mfc/building-on-the-framework.md)   
 [Ordre des opérations pour la génération d'applications MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Ordre des opérations pour la création d'applications OLE](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [Ordre des opérations pour la création de contrôles ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)
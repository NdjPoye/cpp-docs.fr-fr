---
title: "Consommateur ODBC MFC (Assistant) | Microsoft Docs"
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
  - "vc.codewiz.class.mfc.consumer.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Consommateur ODBC MFC (Assistant)"
  - "Assistants (MFC)"
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
caps.latest.revision: 7
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Consommateur ODBC MFC (Assistant)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Insérez ici le résumé « Résultats de la recherche ».  
  
 Cet Assistant définit une classe de recordset ODBC et les liaisons de données nécessaires pour accéder à la source de données spécifiée.  
  
## Liste UIElement  
 **Source de données**  
 Le bouton **Source de données** vous permet de définir la source de données spécifiée à l'aide du pilote ODBC déterminé.  Pour plus d'informations sur les fichiers de sources de données \(DSN\), consultez l'article [File Data Sources](https://msdn.microsoft.com/en-us/library/ms715401.aspx) dans le Kit de développement ODBC SDK.  La boîte de dialogue **Source de données** comprend deux onglets :  
  
-   Onglet **Sources de données fichier** : la zone **Regarder dans** spécifie le répertoire dans lequel sélectionner les fichiers à utiliser comme sources de données.  La valeur par défaut est \\Program Files\\Common Files\\ODBC\\Data Sources.  Les sources de données de fichiers existants \(fichiers .dsn\) s'affichent dans la zone de liste principale.  Vous pouvez soit configurer les sources de données à l'avance à l'aide de l'onglet **Sources de données fichier** de l'[Administrateur de sources de données ODBC](https://msdn.microsoft.com/en-us/library/ms714024.aspx), soit en créer de nouvelles à l'aide de cette boîte de dialogue.  
  
     Pour créer une nouvelle source de données de fichiers à partir de cette boîte de dialogue, cliquez sur `New` pour spécifier un nom DSN. La boîte de dialogue **Créer une nouvelle source de données** s'affiche.  Dans la boîte de dialogue **Créer une nouvelle source de données**, sélectionnez un pilote approprié et cliquez sur `Next`. Cliquez sur **Parcourir** et sélectionnez le nom du fichier à utiliser comme source de données \(vous devez sélectionner « Tous les fichiers » pour afficher les fichiers non DSN, tels que les fichiers .xls\). Cliquez sur `Next`, puis sur **Terminer**. \(Si vous avez sélectionné un fichier non DSN, vous accédez à une boîte de dialogue propre au pilote, telle que « Installation ODBC pour Microsoft Excel », qui convertit le fichier au format DSN.\)  
  
    > [!NOTE]
    >  Vous pouvez également créer préalablement une nouvelle source de données de fichiers à l'aide de l'Administrateur de sources de données ODBC.  Dans le menu **Démarrer**, sélectionnez **Paramètres**, **Panneau de configuration**, **Outils d'administration**, **Sources de données \(ODBC\)**, puis **Administrateur de sources de données ODBC**.  
  
     La zone **Nom de DNS** vous permet de spécifier un nom pour la source de données de fichiers.  Vous devez vous assurer que le nom du fichier DSN se termine par l'extension de fichier appropriée, telle que .xls pour les fichiers Excel ou .mdb pour les fichiers Access.  
  
     Pour plus d'informations sur les fichiers DSN, consultez [File Data Sources](https://msdn.microsoft.com/en-us/library/ms715401.aspx) dans le Kit de développement ODBC SDK.  
  
-   Onglet **Source de données machine** : cet onglet répertorie les sources système et de données utilisateur.  Les sources de données utilisateur sont propres à un utilisateur de cet ordinateur.  Les sources de données système peuvent être utilisées par tous les utilisateurs de cet ordinateur ou d'un service système.  Consultez [Machine Data Sources](https://msdn.microsoft.com/en-us/library/ms710952.aspx) dans le Kit de développement ODBC SDK.  
  
 Pour plus d'informations sur les sources de données ODBC, consultez [Data Sources](https://msdn.microsoft.com/en-us/library/ms711688.aspx) dans le Kit de développement ODBC SDK.  
  
 Cliquez sur **OK** pour terminer.  La boîte de dialogue **Sélectionner l'objet de base de données** s'affiche.  Dans cette boîte de dialogue, sélectionnez le tableau ou la vue que le consommateur doit utiliser.  Remarquez que vous pouvez sélectionner plusieurs vues et tableaux en maintenant la touche CTRL enfoncée et en cliquant sur les éléments.  
  
 **Classe**  
 Nom de la classe de consommateur, fondé par défaut sur le nom du fichier ou de la source de données de l'ordinateur que vous avez sélectionné.  
  
 **fichier .h**  
 Nom du fichier d'en\-tête de la classe de consommateur, fondé par défaut sur le nom du fichier ou de la source de données de l'ordinateur que vous avez sélectionné.  
  
 **fichier .cpp**  
 Nom du fichier d'implémentation de la classe de consommateur, fondé par défaut sur le nom du fichier ou de la source de données de l'ordinateur que vous avez sélectionné.  
  
 **Type**  
 Indique si le recordset est une feuille de réponse dynamique \(par défaut\) ou un instantané.  
  
-   **Dynaset** : spécifie que le recordset est un dynaset.  Un dynaset est le résultat d'une requête qui fournit une vue indexée des données de la base de données interrogée.  Un dynaset ne met en cache qu'un index intégral des données d'origine et permet ainsi d'obtenir de meilleures performances qu'un instantané.  L'index pointe directement vers chaque enregistrement trouvé à la suite d'une requête et indique si un enregistrement est supprimé.  Vous avez également accès aux informations mises à jour dans les enregistrements qui ont fait l'objet de la requête.  Il s'agit de la valeur par défaut.  
  
-   **Instantané** : spécifie que le recordset est un instantané.  Un instantané est le résultat d'une requête et représente une vue de la base de données à un moment donné.  Tous les enregistrements trouvés à la suite de la requête sont mis en cache, si bien que vous ne voyez pas les modifications apportées aux enregistrements d'origine.  
  
 **Lier toutes les colonnes**  
 Indique si toutes les colonnes de la table sélectionnée sont dépendantes.  Si vous activez cette case à cocher \(option par défaut\), toutes les colonnes sont liées. Dans le cas contraire, aucune colonne n'est liée et vous devez les lier manuellement dans la classe de recordset.  
  
## Voir aussi  
 [MFC ODBC, consommation](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)
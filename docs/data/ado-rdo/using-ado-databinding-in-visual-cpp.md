---
title: "Utilisation de la liaison de donn&#233;es ADO dans Visual&#160;C++ | Microsoft Docs"
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
  - "ADO (C++), liaison de données"
  - "contrôles dépendants (C++), ADO"
  - "contrôles dépendants (C++), RDO"
  - "liaison de données (C++), ADO"
  - "liaison de données (C++), RDO"
ms.assetid: ad193919-3437-41ee-b41c-9d353f6274e5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de la liaison de donn&#233;es ADO dans Visual&#160;C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'utilisation de la liaison de ADO dans Visual C\+\+ repose sur les étapes suivantes :  
  
-   ajout d'un contrôle de données ADO ;  
  
-   désignation d'une source de données ;  
  
-   spécification de la source de l'enregistrement \(requête SQL ou langage de récupération de données\) ;  
  
-   ajout d'un contrôle ADO lié aux données ;  
  
-   connexion du contrôle lié aux données à un contrôle de données ADO ;  
  
-   sélection des champs à lier à la source de l'enregistrement du contrôle de données ADO.  
  
### Pour utiliser la liaison de données ADO dans Visual C\+\+  
  
1.  Créez une application à boîtes de dialogue MFC ou une application Formview MFC par l'intermédiaire de l'Assistant Application MFC.  
  
2.  Ajoutez le contrôle de données Microsoft ADO à la boîte de dialogue ; consultez [Insertion du contrôle dans une application Visual C\+\+](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md).  
  
3.  Pointez le contrôle de données ADO vers la source de données OLE DB.  
  
    1.  Cliquez avec le bouton droit sur le contrôle de données ADO, puis cliquez sur **Propriétés**.  
  
    2.  Sous l'onglet **Contrôle**, cliquez sur **Utiliser la chaîne de connexion**.  Vous pouvez utiliser le fournisseur livré ou le supprimer.  
  
    3.  Cliquez sur **Générer**.  Si vous avez supprimé le fournisseur à partir de l'option **Utiliser la chaîne de connexion**, vous pouvez maintenant en définir un autre.  Après avoir défini le fournisseur, accédez de nouveau aux propriétés du contrôle de données ADO et resélectionnez **Générer** pour continuer.  
  
         Si un fournisseur est défini dans **Utiliser la chaîne de connexion** alors que vous n'avez pas encore sélectionné **Générer**, vous pouvez définir les propriétés de liaison de données.  L'Assistant Liaisons de données apparaît.  
  
    4.  Modifiez le **Fournisseur** si nécessaire, puis définissez les valeurs **Emplacement** et **Source de données**, en fonction du fournisseur.  Par exemple, si vous utilisez un fournisseur SQL Server, **Emplacement** spécifie le serveur de base de données et **Source de données** la base de données.  Si vous utilisez un fournisseur ODBC, la **Source de données** correspond au DSN ODBC.  
  
    5.  Cliquez sur l'onglet **Authentification** et définissez les valeurs pour **Nom d'utilisateur** et **Mot de passe**, si la source de données l'exige.  
  
    6.  Cliquez sur l'onglet **Connexion**, puis sur **Tester la connexion** pour tester la source de données.  Faites défiler la fenêtre des résultats jusqu'au bout pour voir si le test a réussi.  Si le test a échoué, vérifiez la configuration de la source de données.  Les erreurs courantes incluent les mots de passe non valides et les valeurs incorrectes pour les champs **Emplacement** et **Source de données**.  
  
    7.  Quittez l'Assistant Liaisons de données et retournez à la feuille de propriétés du contrôle de données ADO.  
  
4.  Sous l'onglet `RecordSource`, entrez une requête dans **Command Text \(SQL\)**.  Les contrôles liés aux données peuvent se lier aux résultats de cette requête.  La requête est habituellement SQL.  Cependant, certains fournisseurs OLE DB n'utilisent pas SQL.  
  
5.  Définissez, si nécessaire, d'autres propriétés du contrôle de données ADO et fermez la feuille de propriétés de celui\-ci.  
  
6.  Ajoutez un contrôle lié aux données.  Par exemple, ajoutez le contrôle DataGrid, qui est différent du contrôle DBGrid RDO.  
  
7.  Définissez les propriétés de DataGrid.  
  
    1.  Cliquez avec le bouton droit sur le DataGrid, puis cliquez sur **Propriétés**.  
  
    2.  Cliquez sur l'onglet **Tout**, puis affectez la propriété **DataSource** au contrôle de données ADO.  Cliquez sur la liste déroulante **DataSource** et recherchez l'identificateur du contrôle de données ADO.  L'identificateur par défaut est IDC\_ADODC1.  
  
8.  Pour fonctionner en mode test, appuyez sur CTRL\+T.  Vous pouvez faire défiler les données.  Appuyez sur la touche Échap ou fermez la boîte de dialogue pour mettre fin au mode test.  
  
 Si vous compilez et exécutez le programme, vous pouvez également faire défiler les données.  
  
## Voir aussi  
 [Liaison de données ADO](../../data/ado-rdo/ado-databinding.md)   
 [Liaison de données avec des contrôles ActiveX dans Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)
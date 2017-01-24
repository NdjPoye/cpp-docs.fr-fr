---
title: "MFC&#160;: utilisation de classes de bases de donn&#233;es avec des documents et des vues | Microsoft Docs"
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
  - "CDaoRecordView (classe), utiliser dans des applications de base de données"
  - "CDaoRecordView (classe), utiliser dans des formulaires de base de données"
  - "CRecordView (classe), utiliser dans des formulaires de base de données"
  - "DAO (C++), formulaires dans les applications de bases de données"
  - "DAO (recordsets C++)"
  - "DAO (recordsets C++), documents et vues"
  - "applications de base de données (C++), formulaires"
  - "classes de base de données (C++), MFC"
  - "architecture Document/Vue (C++), dans les bases de données"
  - "documents (C++), applications de bases de données"
  - "formulaires (C++), applications de bases de données"
  - "ODBC (C++), formulaires"
  - "ODBC (recordsets C++), documents et vues"
  - "vues des enregistrements (C++), applications basées sur les formulaires"
  - "recordsets (C++), documents et vues"
  - "vues (C++), applications de bases de données"
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC&#160;: utilisation de classes de bases de donn&#233;es avec des documents et des vues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez également utiliser les classes de bases de données MFC \(DAO ou ODBC\) avec ou sans l'architecture document\/vue.  Cette rubrique est axée sur l'utilisation des documents et des vues.  Il explique :  
  
-   [Comment écrire une application à base de formulaires](#_core_writing_a_form.2d.based_application) en utilisant l'objet `CRecordView` ou `CDaoRecordView` en tant que vue principale de votre document.  
  
-   [Comment utiliser des objets Recordset dans les documents et les vues](#_core_using_recordsets_in_documents_and_views).  
  
-   [Autres considérations](#_core_other_factors).  
  
 Pour des alternatives, consultez [MFC : utilisation de classes de bases de données sans document ni vue](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
##  <a name="_core_writing_a_form.2d.based_application"></a> Écriture d'une application à base de formulaires  
 De nombreuses applications d'accès aux données reposent sur des formulaires.  L'interface utilisateur est un formulaire contenant des contrôles dans lesquels l'utilisateur examine, entre ou modifie des données.  Pour que votre application repose sur les formulaires, utilisez la classe `CRecordView` ou `CDaoRecordView`.  Quand vous exécutez l'Assistant Application MFC et sélectionnez le type de client **ODBC** dans la page **Prise en charge des bases de données**, le projet utilise `CRecordView` pour la classe d'affichage.  Les Assistants ne prennent plus en charge DAO ; si vous voulez donc utiliser la classe `CDaoRecordView`, vous devez la coder manuellement.  
  
 Dans une application basée sur les formulaires, chaque objet recordview stocke un pointeur désignant un objet `CRecordset` ou `CDaoRecordset`.  Le mécanisme RFX \(Record Field Exchange\) de l'infrastructure échange les données entre le recordset et la source de données.  Le mécanisme d'échange de données de boîtes de dialogue \(DDX\) échange des données entre les données membres de champ de l'objet recordset et les contrôles sur le formulaire.  `CRecordView` ou `CDaoRecordView` fournit également des fonctions de gestionnaire de commandes par défaut pour naviguer entre les enregistrements sur le formulaire.  
  
 Pour créer une application à base de formulaires à l'aide de l'Assistant Application, consultez [Création d'une application MFC basée sur les formulaires](../mfc/reference/creating-a-forms-based-mfc-application.md) et [Prise en charge des bases de données, Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md)  
  
 Pour une description détaillée des formulaires, consultez [Vues des enregistrements](../data/record-views-mfc-data-access.md).  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a> Utilisation de recordsets dans des documents et des vues  
 De nombreuses applications simples à base de formulaires n'ont pas besoin de documents.  Si votre application est plus complexe, vous voudrez probablement utiliser un document en tant que proxy de la base de données, en y stockant un objet `CDatabase` ou `CDaoDatabase` qui se connecte à la source de données.  Les applications à base de formulaires stockent un pointeur désignant un objet Recordset dans la vue.  D'autres types d'applications de bases de données stockent des recordsets et des objets `CDatabase` ou `CDaoDatabase` dans le document.  Voici quelques\-unes des possibilités qu'offre l'utilisation de documents dans des applications de bases de données :  
  
-   Si vous accédez à un recordset dans un contexte local, créez un objet `CRecordset` ou `CDaoRecordset` localement dans des fonctions membres du document ou de la vue, selon le cas.  
  
     Déclarez un objet Recordset en tant que variable locale dans une fonction.  Passez la valeur **NULL** au constructeur, ce qui amène l'infrastructure à créer et à ouvrir un objet `CDatabase` ou `CDaoDatabase` temporaire pour vous.  Sinon, passez un pointeur désignant un objet `CDatabase` ou `CDaoDatabase`.  Utilisez le recordset dans la fonction, puis autorisez sa destruction automatique à la fermeture de celle\-ci.  
  
     Quand vous passez la valeur **NULL** à un constructeur de recordset, l'infrastructure utilise les informations retournées par la fonction membre `GetDefaultConnect` du recordset pour créer un objet `CDatabase` ou `CDaoDatabase` et l'ouvrir.  Les Assistants implémentent `GetDefaultConnect` à votre place.  
  
-   Si vous accédez à un recordset pendant la durée de vie de votre document, incorporez un ou plusieurs objets `CRecordset` ou `CDaoRecordset` dans votre document.  
  
     Construisez les objets Recordset soit au moment de l'initialisation du document soit au fur et à mesure des besoins.  Vous pouvez écrire une fonction qui retourne un pointeur désignant le recordset si celui\-ci existe déjà, ou qui construit et ouvre le recordset si celui\-ci n'existe pas encore.  Fermez, supprimez et recréez le recordset si nécessaire, ou appelez sa fonction membre **Requery** pour actualiser les enregistrements.  
  
-   Si vous accédez à une source de données pendant la durée de vie de votre document, incorporez dans celui\-ci l'objet `CDatabase` ou `CDaoDatabase` ou stockez\-y un pointeur désignant un objet `CDatabase` ou `CDaoDatabase`.  
  
     L'objet `CDatabase` ou `CDaoDatabase` gère une connexion à la source de données.  L'objet est généré automatiquement pendant la construction du document, et vous appelez sa fonction membre **Open** lorsque vous initialisez le document.  Quand vous construisez des objets Recordset dans des fonctions membres de document, vous passez un pointeur à l'objet `CDatabase` ou `CDaoDatabase` du document.  Vous associez ainsi chaque recordset à sa source de données.  L'objet de base de données est généralement détruit à la fermeture du document.  Les objets Recordset sont généralement détruits quand ils quittent la portée d'une fonction.  
  
##  <a name="_core_other_factors"></a> Autres facteurs  
 Les applications à base de formulaires ne font que rarement appel au mécanisme de sérialisation de document de l'infrastructure ; vous pouvez donc, le cas échéant, supprimer, désactiver ou remplacer les commandes `New` et **Ouvrir** du menu **Fichier**.  Consultez [Sérialisation : sérialisation et entrées\/sorties de base de données](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Vous pouvez également, au besoin, utiliser les nombreuses possibilités de l'interface utilisateur que l'infrastructure peut prendre en charge.  Par exemple, vous pouvez utiliser plusieurs objets `CRecordView` ou `CDaoRecordView` dans une fenêtre fractionnée, ouvrir plusieurs recordsets dans différentes fenêtres enfants MDI \(interface multidocument\), et ainsi de suite.  
  
 Vous pouvez souhaiter imprimer tout ce que contient votre vue, que ce soit un formulaire implémenté avec `CRecordView`, `CDaoRecordView` ou autre chose.  Dans la mesure où les classes dérivées de `CFormView`, `CRecordView` et `CDaoRecordView` ne prennent pas en charge l'impression, vous pouvez substituer la fonction membre `OnPrint` pour autoriser l'impression.  Pour plus d'informations, consultez la classe [CFormView](../mfc/reference/cformview-class.md).  
  
 Vous pouvez souhaiter ne pas utiliser du tout les documents et les vues.  En ce cas, consultez [MFC : utilisation de classes de bases de données sans document ni vue](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
## Voir aussi  
 [Classes de bases de données MFC \(ODBC et DAO\)](../data/mfc-database-classes-odbc-and-dao.md)
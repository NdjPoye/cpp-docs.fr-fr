---
title: "MFC&#160;: utilisation de classes de bases de donn&#233;es sans document ni vue | Microsoft Docs"
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
  - "Assistants Application (C++), créer des applications de bases de données"
  - "CDaoRecordView (classe), utiliser dans des applications de base de données"
  - "CRecordView (classe), utiliser dans des applications de base de données"
  - "DAO (C++), prise en charge des fichiers dans les applications de bases de données"
  - "DAO (C++), écrire des applications"
  - "applications de base de données (C++), Assistant Application (options)"
  - "applications de base de données (C++), sans document"
  - "applications de base de données (C++), sans vue"
  - "classes de base de données (C++), MFC"
  - "architecture Document/Vue (C++), dans les bases de données"
  - "documents (C++), applications sans"
  - "fichiers (C++), MFC"
  - "ODBC (C++), prise en charge des fichiers dans les applications de bases de données"
  - "ODBC (applications) (C++)"
  - "ODBC (applications) (C++), sans document"
  - "ODBC (applications) (C++), sans vue"
  - "interface utilisateur (C++), dessiner des informations"
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC&#160;: utilisation de classes de bases de donn&#233;es sans document ni vue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez parfois ne pas souhaiter utiliser l'architecture document\/vue de l'infrastructure dans vos applications de bases de données.  Cette rubrique explique :  
  
-   [Quand vous n'avez pas besoin d'utiliser des documents](#_core_when_you_don.92.t_need_documents) comme pour la sérialisation des documents.  
  
-   Les [options de l'assistant Application](#_core_appwizard_options_for_documents_and_views) pour prendre en charge des applications sans sérialisation et sans les commandes du menu **Fichier**, par exemple **Nouveau**, **Ouvrir**, **Enregistrer** et **Enregistrer sous**, applicables aux documents.  
  
-   [Comment utiliser une application qui utilise un document minimal](#_core_applications_with_minimal_documents).  
  
-   [Comment structurer une application sans document ni vue](#_core_applications_with_no_document).  
  
##  <a name="_core_when_you_don.92.t_need_documents"></a> Quand vous n'avez pas besoin d'utiliser des documents  
 Certaines applications ont un concept distinct du document.  Ces applications chargent généralement tout ou partie d'un fichier en mémoire à partir du support de stockage à l'aide d'une commande **Fichier Ouvrir**.  Elles réécrivent le fichier mis à jour sur le support de stockage en une fois à l'aide d'une commande **Fichier Enregistrer** ou **Enregistrer sous**.  Ce que l'utilisateur voit est un fichier de données.  
  
 Certaines catégories d'applications, cependant, n'ont pas besoin de documents.  Les applications de bases de données opèrent en termes de transactions.  L'application sélectionne des enregistrements dans une base de données et les présente à l'utilisateur, souvent un à la fois.  Ce que l'utilisateur voit est généralement un seul enregistrement en cours, qui peut être le seul en mémoire.  
  
 Si votre application ne requiert pas un document pour le stockage des données, vous pouvez vous passer de tout ou partie de l'architecture document\/vue de l'infrastructure.  La partie dont vous pouvez vous passer dépend de l'approche que vous adoptez.  Vous pouvez :  
  
-   Utiliser un document minimal en tant qu'emplacement de stockage d'une connexion à votre source de données tout en vous passant des fonctionnalités normales liées aux documents telles que la sérialisation.  Ceci est utile quand vous voulez avoir plusieurs vues des données et souhaitez synchroniser toutes les vues, les mettre à jour toutes en même temps, etc.  
  
-   Utiliser une fenêtre frame, dans laquelle vous dessinez directement, au lieu d'utiliser une vue.  En ce cas, omettez le document et stockez les données ou les connexions des données dans l'objet fenêtre frame.  
  
##  <a name="_core_appwizard_options_for_documents_and_views"></a> Options de l'Assistant Application pour les documents et les vues  
 L'Assistant Application MFC possède plusieurs options dans **Prise en charger des bases de données**, qui sont répertoriées dans le tableau ci\-dessous.  Si vous utilisez l'Assistant Application MFC pour créer une application, toutes ces options produisent des applications dotées de documents et de vues.  Certaines options fournissent des documents et des vues qui omettent la fonction de document superflue.  Pour plus d'informations, consultez [Prise en charge des bases de données, Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md).  
  
|Option|Vue|Document|  
|------------|---------|--------------|  
|**None**|Dérivée de `CView`.|N'offre aucune prise en charge des bases de données.  Il s'agit de l'option par défaut.<br /><br /> Si vous sélectionnez l'option **Prise en charge de l'architecture Document\/Vue** dans la page [Type d'application, Assistant Application MFC](../mfc/reference/application-type-mfc-application-wizard.md), vous bénéficiez d'une prise en charge complète pour le document, y compris la sérialisation et les commandes `New`, **Ouvrir**, **Enregistrer** et **Enregistrer sous** du menu **Fichier**.  Consultez [Applications sans document](#_core_applications_with_no_document).|  
|**Fichiers d'en\-tête uniquement**|Dérivée de `CView`.|Assure le niveau de base de prise en charge des bases de données pour votre application.<br /><br /> Inclut Afxdb.h.  Ajoute des bibliothèques de liens, mais ne crée pas de classes spécifiques à la base de données.  Vous pouvez créer des recordsets ultérieurement et les utiliser pour examiner et mettre à jour les enregistrements.|  
|**Vue de base de données sans prise en charge des fichiers**|Dérivée de `CRecordView`|Assure la prise en charge des documents mais pas la prise en charge de la sérialisation.  Le document peut stocker le recordset et coordonner plusieurs vues ; il ne prend pas en charge ni la sérialisation ni les commandes `New`, **Ouvrir**, **Enregistrer** et **Enregistrer sous**.  Consultez [Applications avec des documents minimaux](#_core_applications_with_minimal_documents).  Si vous choisissez d'inclure une vue de base de données, vous devez spécifier la source des données.<br /><br /> Inclut des fichiers d'en\-tête de base de données, des bibliothèques de liens, une vue de l'enregistrement et un recordset. \(Cette option n'est disponible que pour les applications pour lesquelles l'option **Prise en charge de l'architecture Document\/Vue** est sélectionnée dans la page [Type d'application, Assistant Application MFC](../mfc/reference/application-type-mfc-application-wizard.md).\)|  
|**Vue de base de données avec prise en charge des fichiers**|Dérivée de `CRecordView`|Fournit une prise en charge complète des documents, y compris la sérialisation et les commandes du menu **Fichier** applicables aux documents.  Les applications de base de données opèrent généralement par enregistrement et non par fichier ; elles n'ont donc pas besoin de la sérialisation.  Il se peut toutefois que vous utilisiez la sérialisation dans un but spécial.  Consultez [Applications avec des documents minimaux](#_core_applications_with_minimal_documents).  Si vous choisissez d'inclure une vue de base de données, vous devez spécifier la source des données.<br /><br /> Inclut des fichiers d'en\-tête de base de données, des bibliothèques de liens, une vue de l'enregistrement et un recordset. \(Cette option n'est disponible que pour les applications pour lesquelles l'option **Prise en charge de l'architecture Document\/Vue** est sélectionnée dans la page [Type d'application, Assistant Application MFC](../mfc/reference/application-type-mfc-application-wizard.md).\)|  
  
 Pour plus d'informations sur les alternatives à la sérialisation et les autres utilisations pour la sérialisation, consultez [Sérialisation : sérialisation et entrées\/sorties de base de données](../mfc/serialization-serialization-vs-database-input-output.md).  
  
##  <a name="_core_applications_with_minimal_documents"></a> Applications avec des documents minimaux  
 L'Assistant Application MFC possède deux options qui prennent en charge les applications d'accès aux données à base de formulaires.  Chaque option crée une classe d'affichage dérivée de `CRecordView` et un document.  Ces options diffèrent au niveau des éléments du document qu'elles éliminent.  
  
###  <a name="_core_a_document_without_file_support"></a> Document sans prise en charge des fichiers  
 Sélectionnez l'option de base de données de l'Assistant Application **Vue de base de données sans prise en charge des fichiers** si vous n'avez pas besoin de la sérialisation de document.  Le document répond aux objectifs utiles suivants :  
  
-   C'est un emplacement commode pour le stockage d'un objet `CRecordset`.  
  
     Cette utilisation correspond aux concepts de document ordinaires : le document stocke les données \(ou, en l'occurrence, un recordset\) et la vue est une vue du document.  
  
-   Si votre application présente plusieurs vues \(par exemple, plusieurs vues de l'enregistrement\), un document prend en charge la coordination des vues.  
  
     Si plusieurs vues affichent les mêmes données, vous pouvez utiliser la fonction membre `CDocument::UpdateAllViews` pour coordonner les mises à jour de toutes les vues quand une vue modifie les données.  
  
 Vous utilisez généralement cette option pour les applications simples basées sur des formulaires.  L'Assistant Application prend en charge automatiquement une structure pratique pour de telles applications.  
  
###  <a name="_core_a_document_with_file_support"></a> Document avec prise en charge des fichiers  
 Sélectionnez l'option de base de données de l'Assistant Application **Vue de base de données avec prise en charge des fichiers** quand vous avez une utilisation alternative pour les commandes du menu **Fichier** liées aux documents et à la sérialisation des documents.  Pour la partie accès aux données de votre programme, vous pouvez utiliser le document comme décrit dans [Document sans prise en charge des fichiers](#_core_a_document_without_file_support).  Vous pouvez utiliser la fonction de sérialisation de document, par exemple, pour lire et écrire un document de profil utilisateur sérialisé qui stocke les préférences de l'utilisateur ou d'autres informations utiles.  Pour plus d'informations, consultez [Sérialisation : sérialisation et entrées\/sorties de base de données](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 L'Assistant Application prend en charge cette option, mais vous devez écrire le code qui sérialise le document.  Stockez les informations sérialisées dans des données membres du document.  
  
##  <a name="_core_applications_with_no_document"></a> Applications sans document  
 Vous pouvez parfois souhaiter écrire une application qui n'utilise ni document ni vue.  Sans document, vous stockez les données \(telles qu'un objet `CRecordset`\) dans la classe de fenêtre frame ou la classe d'application.  Les besoins supplémentaires éventuels dépendent de la présence ou de l'absence d'une interface utilisateur dans l'application.  
  
###  <a name="_core_database_support_with_a_user_interface"></a> Prise en charge des bases de données avec une interface utilisateur  
 Si vous disposez d'une interface utilisateur \(autre, par exemple, qu'une interface de ligne de commande de console\), votre application est dessinée non pas dans une vue mais directement dans la zone cliente de la fenêtre frame.  Une telle application n'utilise ni `CRecordView`, ni `CFormView` ni `CDialog` pour son interface utilisateur principale, mais fait généralement appel à `CDialog` pour les boîtes de dialogue ordinaires.  
  
###  <a name="_core_writing_applications_without_documents"></a> Écriture d'applications sans document  
 Dans la mesure où l'Assistant Application ne prend pas en charge la création d'applications sans document, vous devez écrire votre propre classe dérivée de `CWinApp` et, le cas échéant, créer également une classe `CFrameWnd` ou `CMDIFrameWnd`.  Substituez `CWinApp::InitInstance` et déclarez un objet application en tant que :  
  
```  
CYourNameApp theApp;  
```  
  
 L'infrastructure fournit toujours le mécanisme de correspondance des messages et de nombreuses autres fonctionnalités.  
  
###  <a name="_core_database_support_separate_from_the_user_interface"></a> Prise en charge des bases de données distinctes de l'interface utilisateur  
 Certaines applications n'ont parfois pas besoin d'interface utilisateur ou ne requièrent qu'une interface utilisateur minimale.  Par exemple, vous écrivez :  
  
-   Un objet intermédiaire d'accès aux données que d'autres applications \(clientes\) appellent pour un traitement spécial des données entre l'application et la source de données.  
  
-   Une application qui traite les données sans l'intervention de l'utilisateur, par exemple une application qui convertit les données d'un format de base de données en un autre, ou une application qui effectue des calculs et exécute des mises à jour en batch.  
  
 Dans la mesure où aucun document ne possède l'objet `CRecordset` ou `CDaoRecordset`, vous souhaiterez probablement le stocker en tant que donnée membre incorporée dans votre classe d'application dérivée de `CWinApp`.  Les solutions de remplacement sont les suivantes :  
  
-   Ne pas conserver du tout un objet `CRecordset` ou `CDaoRecordset` permanent.  Vous pouvez passer la valeur **NULL** aux constructeurs de votre classe de recordset.  Dans ce cas, l'infrastructure crée un objet `CDatabase` ou `CDaoDatabase` temporaire en utilisant les informations de la fonction membre `GetDefaultConnect` du recordset.  C'est l'approche alternative la plus probable.  
  
-   Faire de l'objet `CRecordset` ou `CDaoRecordset` une variable globale.  Cette variable doit être un pointeur désignant un objet Recordset que vous créez dynamiquement lors de la substitution de `CWinApp::InitInstance`.  Vous évitez ainsi toute tentative de construction de l'objet avant l'initialisation de l'infrastructure.  
  
-   Utiliser des objets Recordset comme dans le contexte d'un document ou d'une vue.  Créez des recordsets dans les fonctions membres de l'application ou des objets de la fenêtre frame.  
  
## Voir aussi  
 [Classes de bases de données MFC \(ODBC et DAO\)](../data/mfc-database-classes-odbc-and-dao.md)
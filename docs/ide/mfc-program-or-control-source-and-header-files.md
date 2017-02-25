---
title: "Fichiers d&#39;en-t&#234;te et fichiers sources de contr&#244;le ou de programme MFC | Microsoft Docs"
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
  - "types de fichiers (C++), source et en-tête MFC"
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Fichiers d&#39;en-t&#234;te et fichiers sources de contr&#244;le ou de programme MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez un projet MFC dans Visual Studio, les fichiers suivants sont également créés en fonction des options sélectionnées pour votre nouveau projet.  Par exemple, votre projet contient les fichiers *Nomprojet*dlg.cpp et *Nomprojet*dlg.h uniquement si vous créez un projet ou une classe basés sur des boîtes de dialogue.  
  
 Tous ces fichiers sont stockés dans le répertoire *Nomprojet* et figurent soit dans le dossier Header Files \(fichiers .h\), soit dans le dossier Source Files \(fichiers .cpp\) de l'Explorateur de solutions.  
  
|Nom du fichier|Description|  
|--------------------|-----------------|  
|*Nomprojet*.h|Fichier include principal pour le programme ou la DLL.  Ce fichier contient tous les symboles globaux et directives `#include` pour les autres fichiers d'en\-tête.  Il dérive la classe `CPrjnameApp` de `CWinApp` et déclare une fonction membre `InitInstance`.  Dans le cas d'un contrôle, la classe `CPrjnameApp` est dérivée de `COleControlModule`.|  
|*Nomprojet*.cpp|Fichier source principal de programme.  Ce fichier crée un objet de la classe `CPrjnameApp`, dérivée de `CWinApp`, et se substitue à la fonction membre `InitInstance`.<br /><br /> Dans le cas des exécutables, `CPrjnameApp::InitInstance` effectue plusieurs tâches.  Il inscrit les modèles de document servant de connexion entre les documents et les vues, il crée une fenêtre frame principale et il crée un document vide \(ou il ouvre le document spécifié comme argument de ligne de commande à l'application, le cas échéant\).<br /><br /> Dans le cas des DLL et des contrôles ActiveX \(anciennement appelés OLE\), `CProjNameApp::InitInstance` inscrit la fabrique d'objet du contrôle avec OLE en appelant `COleObjectFactory::RegisterAll` et effectue un appel à `AfxOLEInit`.  En outre, la fonction membre `CProjNameApp::ExitInstance` est utilisée pour décharger le contrôle de la mémoire en appelant **AfxOleTerm**.<br /><br /> Par ailleurs, ce fichier inscrit et annule l'inscription du contrôle dans la base de données d'inscription de Windows en implémentant les fonctions `DllRegisterServer` et `DllUnregisterServer`.|  
|*Nomprojet*ctrl.h, *Nomprojet*ctrl.cpp|Déclarez et implémentez la classe `CProjnameCtrl`.  `CProjnameCtrl` est dérivé de `COleControl`, et des implémentations squelette de certaines fonctions membres sont définies pour initialiser, dessiner et sérialiser \(charger et sauvegarder\) le contrôle.  Les tables de messages, d'événements et de dispatch sont également définies dans ces fichiers.|  
|*Nomprojet*dlg.cpp, *Nomprojet*dlg.h|Fichiers créés si vous avez choisi une application basée sur des boîtes de dialogue.  Ces fichiers dérivent de la classe de boîte de dialogue nommée `CProjnameDlg` et l'implémentent, ainsi que définissent des fonctions membres squelettes pour initialiser une boîte de dialogue et effectuer l'échange de données de boîtes de dialogue \(DDX\).  Votre classe de boîte de dialogue À propos de est également stockée dans ces fichiers et pas dans *Nomprojet*.cpp.|  
|Dlgproxy.cpp, Dlgproxy.h|Dans un programme basé sur des boîtes de dialogue, fichier d'implémentation et d'en\-tête de la classe proxy Automation du projet définie pour la boîte de dialogue principale.  Ce fichier est utilisé uniquement si vous avez sélectionné une prise en charge de Automation.|  
|*Nomprojet*doc.cpp, *Nomprojet*doc.h|Fichiers qui dérivent de la classe de document nommée `CProjnameDoc` et l'implémentent, ainsi que définissent des fonctions membres squelettes pour initialiser un document, sérialiser \(enregistrer et charger\) le document et implémenter les diagnostics du débogage.|  
|*Nomprojet*set.h\/.cpp|Fichiers créés si le programme que vous créez gère une base de données et contient la classe de recordset.|  
|*Nomprojet*view.cpp, *Nomprojet*view.h|Fichiers qui dérivent de la classe d'affichage nommée `CProjnameView` et l'implémentent ; elle est utilisée pour afficher et imprimer les données d'un document.  La classe `CProjnameView` est dérivée d'une des classes MFC suivantes :<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHtmlView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> La classe d'affichage du projet définit les fonctions membres squelettes utilisées pour dessiner la vue et implémenter les diagnostics du débogage.  Si vous avez activé la prise en charge de l'impression, des entrées de la table des messages sont ajoutées pour les messages de commande relatifs à l'impression, à la configuration de l'impression et à l'aperçu avant impression.  Ces entrées appellent les fonctions membres correspondantes dans la classe d'affichage de base.|  
|*Nomprojet*PropPage.h, *Nomprojet*PropPage.cpp|Déclarez et implémentez la classe `CProjnamePropPage`.  `CProjnamePropPage` est dérivé de `COlePropertyPage` et une fonction membre squelette, `DoDataExchange`, est fournie pour implémenter la validation et l'échange des données.|  
|IPframe.cpp, IPframe.h|Fichier créé si l'option Mini\-serveur ou Serveur complet est activée dans la page **Prise en charge des documents composés** \(étape 3 sur 6\) de l'Assistant Application.  Ces fichiers dérivent de la classe de fenêtre frame sur place nommée **CInPlaceFrame** et l'implémentent ; elle est utilisée lorsque le serveur est activé sur place par un programme conteneur.|  
|Mainfrm.cpp, Mainfrm.h|Ces fichiers dérivent la classe **CMainFrame** soit de [CFrameWnd](../mfc/reference/cframewnd-class.md) \(applications SDI\), soit de [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) \(applications MDI\).  La classe **CMainFrame** gère la création des boutons de barre d'outils ainsi que la barre d'état, si les options correspondantes sont sélectionnées dans la page **Options d'application** \(étape 4 sur 6\) de l'Assistant Application.  Pour plus d'informations sur l'utilisation de **CMainFrame**, consultez [Classes de fenêtres frames créées par l'Assistant Application](../mfc/frame-window-classes-created-by-the-application-wizard.md).|  
|Childfrm.cpp, Childfrm.h|Ces fichiers dérivent la classe **CChildFrame** de [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).  La classe **CChildFrame** est utilisée pour les fenêtres frames de document MDI.  Ces fichiers sont créés dès lors que vous sélectionnez l'option MDI.|  
  
## Voir aussi  
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Fichiers d'en\-tête et fichiers sources de contrôle ou de programme ATL](../ide/atl-program-or-control-source-and-header-files.md)   
 [Projets CLR](../ide/files-created-for-clr-projects.md)
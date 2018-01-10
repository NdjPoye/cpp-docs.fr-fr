---
title: "Fichiers d’en-tête et sources de contrôle ou de programme MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adb4ba4fdcc141438b2eeb87b4e3c9151bb9a5c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-program-or-control-source-and-header-files"></a>Fichiers d'en-tête et fichiers sources de contrôle ou de programme MFC
Les fichiers suivants sont créés lorsque vous créez un projet MFC dans Visual Studio, selon les options que vous sélectionnez pour le projet que vous créez. Par exemple, votre projet contient *NomProj*fichiers dlg.cpp et *NomProj*dlg.h fichiers uniquement si vous créez un projet basé sur la boîte de dialogue ou une classe.  
  
 Tous ces fichiers se trouvent dans le *NomProj* directory et dans le dossier de fichiers d’en-tête (fichiers .h) ou le dossier des fichiers de code Source (fichiers .cpp) dans l’Explorateur de solutions.  
  
|Nom de fichier|Description|  
|---------------|-----------------|  
|*Nomproj*.h|Le principal fichier include pour le programme ou la DLL. Il contient tous les symboles globaux et `#include` des directives pour les autres fichiers d’en-tête. Il dérive le `CPrjnameApp` classe `CWinApp` et déclare un `InitInstance` fonction membre. Pour un contrôle, la `CPrjnameApp` classe est dérivée de `COleControlModule`.|  
|*Nomproj*.cpp|Le fichier source du programme principal. Crée un objet de la classe `CPrjnameApp`, qui est dérivée de `CWinApp`et remplace le `InitInstance` fonction membre.<br /><br /> Pour les fichiers exécutables, `CPrjnameApp::InitInstance` effectue plusieurs tâches. Il enregistre les modèles de document, qui servent à une connexion entre les documents et vues ; Crée une fenêtre frame principale ; et crée un document vide (ou ouvre un document s’il est spécifié comme un argument de ligne de commande à l’application).<br /><br /> Pour des contrôles ActiveX (anciennement appelés OLE) et les DLL, `CProjNameApp::InitInstance` inscrit la fabrique d’objet du contrôle avec OLE en appelant `COleObjectFactory::RegisterAll` et effectue un appel à `AfxOLEInit`. En outre, la fonction membre `CProjNameApp::ExitInstance` est utilisée pour décharger le contrôle de la mémoire avec un appel à **en appelant AfxOleTerm**.<br /><br /> Ce fichier inscrit et annule l’inscription du contrôle dans la base de données d’inscription de Windows en implémentant la `DllRegisterServer` et `DllUnregisterServer` fonctions.|  
|*Nomproj*ctrl.h, *NomProj*ctrl.cpp|Déclarez et implémentez la `CProjnameCtrl` classe. `CProjnameCtrl`est dérivé de `COleControl`, et des implémentations squelettes de certaines fonctions membres sont définies pour initialiser, dessiner et sérialiser (charger et enregistrer) le contrôle. Message, les événements et les tables de dispatch sont également définies.|  
|*Nomproj*fichiers dlg.cpp, *NomProj*dlg.h|Créé si vous choisissez une application basée sur une boîte de dialogue. Ces fichiers dérivent et implémentent la classe de boîte de dialogue, nommée `CProjnameDlg`et les fonctions membres squelettes pour initialiser une boîte de dialogue et effectuer l’échange de données de boîtes de dialogue (DDX). Votre classe à propos de la boîte de dialogue est également placé dans ces fichiers au lieu de *NomProj*.cpp.|  
|Dlgproxy.cpp, Dlgproxy.h|Dans une boîte de dialogue programme, l’implémentation et l’en-tête de fichier de classe de proxy Automation du projet pour la boîte de dialogue principale. Cela est uniquement utilisée si vous avez choisi de prise en charge Automation.|  
|*Nomproj*doc.cpp, *NomProj*doc.h|Dériver et à implémenter la classe de document nommée `CProjnameDoc`et les fonctions membres squelettes pour initialiser un document, sérialiser (Enregistrer et charger) un document et implémenter les diagnostics du débogage.|  
|*Nomproj*set.h/.cpp|Créé si vous créez un programme qui prend en charge une base de données et qui contient la classe de recordset.|  
|*Nomproj*view.cpp, *NomProj*view.h|Dériver et à implémenter la classe d’affichage, nommée `CProjnameView`, qui est utilisé pour afficher et imprimer les données du document. La `CProjnameView` classe est dérivée d’une des classes MFC suivantes :<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> Classe de vue du projet contient des fonctions membres squelettes pour dessiner la vue et implémenter les diagnostics du débogage. Si vous avez activé la prise en charge pour l’impression, les entrées de table des messages sont ajoutées pour le programme d’installation de l’impression, l’imprimer et afficher les messages de commande d’aperçu. Ces entrées appellent les fonctions de membre correspondant dans la classe d’affichage de base.|  
|*Nomproj*PropPage.h, *NomProj*PropPage.cpp|Déclarez et implémentez la `CProjnamePropPage` classe. `CProjnamePropPage`est dérivé de `COlePropertyPage` et une fonction membre squelette, `DoDataExchange`, pour implémenter l’échange et la validation.|  
|IPframe.cpp, IPframe.h|Créé si l’option mini-serveur ou serveur complet est sélectionnée dans l’Assistant application **Options d’automatisation** page (étape 3 de 6). Ces fichiers dérivent et implémentent la classe de fenêtre frame en place, nommée **CInPlaceFrame**, utilisé lorsque le serveur est activé sur place par un programme de conteneur.|  
|MainFrm.cpp, Mainfrm.h|Dériver les **CMainFrame** classe à partir de le [CFrameWnd](../mfc/reference/cframewnd-class.md) (pour les applications SDI) ou [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) (pour les applications MDI). Le **CMainFrame** classe gère la création de boutons de barre d’outils et la barre d’état, si les options correspondantes sont sélectionnées dans l’Assistant application **Application Options** page (étape 4 de 6). Pour plus d’informations sur l’utilisation de **CMainFrame**, consultez [Classes de fenêtre Frame créées par l’Assistant Application](../mfc/frame-window-classes-created-by-the-application-wizard.md).|  
|ChildFrm.cpp, Childfrm.h|Dériver les **CChildFrame** classe [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md). Le **CChildFrame** classe est utilisée pour les fenêtres frame de document MDI. Ces fichiers sont toujours créés si vous sélectionnez l’option MDI.|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Fichiers d’en-tête et sources de contrôle ou de programme ATL](../ide/atl-program-or-control-source-and-header-files.md)   
 [Projets CLR](../ide/files-created-for-clr-projects.md)
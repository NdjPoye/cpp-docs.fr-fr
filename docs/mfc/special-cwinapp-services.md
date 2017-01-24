---
title: "Services CWinApp sp&#233;ciaux | Microsoft Docs"
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
  - "LoadStdProfileSettings"
  - "EnableShellOpen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets application (C++), services"
  - "CWinApp (classe), Gestionnaire de fichiers (glisser-déplacer)"
  - "CWinApp (classe), initialiser GDI+"
  - "CWinApp (classe), documents utilisés récemment"
  - "CWinApp (classe), services"
  - "CWinApp (classe), inscription du shell"
  - "glisser-déplacer (C++), fichiers"
  - "DragAcceptFiles (méthode)"
  - "EnableShellOpen (méthode)"
  - "fichiers (C++), glisser-déplacer"
  - "fichiers (C++), utilisés le plus récemment"
  - "GDI+, initialisation pour MFC"
  - "GDI+, supprimer le thread d'arrière-plan (MFC)"
  - "LoadStdProfileSettings (méthode)"
  - "MFC (C++), opérations sur les fichiers"
  - "MFC (C++), liste des fichiers utilisés le plus récemment"
  - "MFC (C++), inscription du shell"
  - "listes utilisées récemment"
  - "inscrire des types de fichiers"
  - "RegisterShellFileTypes (méthode)"
  - "inscription (C++), shell"
  - "registre (C++), fichiers utilisés le plus récemment"
  - "services, fournis par CWinApp"
  - "Shell, inscrire des types de fichiers"
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
caps.latest.revision: 10
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Services CWinApp sp&#233;ciaux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En plus d'effectuer une boucle de message et de vous donner la possibilité d'initialiser l'application et de nettoyer après cela, [CWinApp](../mfc/reference/cwinapp-class.md) fournit plusieurs autres services.  
  
##  <a name="_core_shell_registration"></a> Inscription du Shell  
 Par défaut, l'Application MFC permet à l'utilisateur d'ouvrir les fichiers de données que votre application a créé en double\-cliquant dessus dans l'Explorateur de fichiers ou le gestionnaire de fichiers.  Si votre application est une application MDI et si vous spécifiez une extension des fichiers que votre application crée, l'Application MFC ajoute des appels à [RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md) et à [EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md) fonctions membres de la substitution [CWinApp](../mfc/reference/cwinapp-class.md) à `InitInstance` qu'il écrit pour vous.  
  
 `RegisterShellFileTypes` stocke les types de documents de votre application avec l'Explorateur de fichiers ou le gestionnaire de fichiers.  La fonction ajoute des entrées à la base de données d'inscription que windows gère.  Les entrées de chaque type de document, associent une extension au type de fichier, spécifiez une ligne de commande pour ouvrir l'application, puis spécifiez une commande d'échange dynamique de données \(DDE\) pour ouvrir un document de ce type.  
  
 `EnableShellOpen` termine le processus permettant à l'application de recevoir des commandes de DDE de navigation ou du gestionnaire de fichiers pour ouvrir le fichier choisi par l'utilisateur.  
  
 Cette prise en charge automatique d'inscription dans `CWinApp` élimine le besoin de fournir un fichier .reg à votre application ou d'exécuter un travail d'installation particulier.  
  
 Si vous souhaitez démarrer GDI\+ pour votre application \(en appelant [GdiplusStartup](_gdiplus_FUNC_GdiplusStartup_token_input_output_) dans votre fonction [InitInstance](../Topic/CWinApp::InitInstance.md) \), vous devez supprimer le thread d'arrière\-plan de GDI\+.  
  
 Faîtes cela en mettant le membre de **SuppressBackgroundThread** de la structure [GdiplusStartupInput](_gdiplus_STRUC_GdiplusStartupInput) à **TRUE**.  En supprimant le thread d'arrière\-plan de GDI\+, les appels de **NotificationHook** et de **NotificationUnhook** \(voir [GdiplusStartupOutput](_gdiplus_STRUC_GdiplusStartupOutput)\) doivent être effectuées uniquement avant d'entrer et de quitter la boucle des messages de l'application.  Par conséquent, un bon emplacement pour appeler **GdiplusStartup** et les fonctions de notification de raccordement serait dans une substitution de la fonction virtuelle [CWinApp::Run](../Topic/CWinApp::Run.md), comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/CPP/special-cwinapp-services_1.cpp)]  
  
 Si vous ne supprimez pas le thread d'arrière\-plan de GDI\+, les commandes de DDE peuvent être publiées prématurément dans l'application avant que la fenêtre principale ait été créée.  Les commandes de DDE publiées par le shell peuvent être suspendues prématurément, ce qui aboutit à des messages d'erreur.  
  
##  <a name="_core_file_manager_drag_and_drop"></a> Gestionnaire de fichiers glisser\-déplacer  
 Les fichiers peuvent être glissés de la fenêtre d'affichage de fichier dans le gestionnaire de fichiers ou de l'Explorateur de fichiers dans une fenêtre de votre application.  Vous pouvez, par exemple, activer un ou plusieurs fichiers à faire glisser vers la fenêtre principale d'une application MDI, où l'application peut extraire le nom et les fenêtres enfants MDI ouverts pour ces fichiers.  
  
 Pour activer le glisser\-déplacer de fichier dans votre application, l'Application MFC écrit un appel à la fonction membre [DragAcceptFiles](../Topic/CWnd::DragAcceptFiles.md) de [CWnd](../mfc/reference/cwnd-class.md) pour votre fenêtre cadre principale de votre `InitInstance`.  Supprimez cet appel si vous ne souhaitez pas implémenter les fonctionnalités par glisser\-déplacer.  
  
> [!NOTE]
>  Vous pouvez également implémenter des capacités de glisser\-déplacer plus générales \(comme faire glisser des données entre ou à l'intérieur de documents\) avec OLE.  Pour plus d'informations, consultez l'article [Faites glisser \(OLE DB\)](../mfc/drag-and-drop-ole.md).  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> Gestion des documents des derniers fichiers utilisés  
 Lorsque l'utilisateur ouvre et ferme des fichiers, l'objet d'application gère les quatre fichiers récemment utilisés.  Les noms de ces fichiers sont ajoutés au menu Fichier et mis à jour lorsqu'ils sont modifiés.  L'infrastructure stocke ces noms de fichiers dans le registre ou dans le fichier .ini, avec le même nom que le projet et les lit à partir du fichier lorsque votre application démarre.  La substitution de `InitInstance` que l'Application MFC crée automatiquement inclut un appel à la fonction membre [LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md)d' [CWinApp](../mfc/reference/cwinapp-class.md), ce qui charge les données dans le Registre ou le fichier .ini, y compris les noms de fichier des derniers fichiers utilisés.  
  
 Ces entrées sont stockées comme suit :  
  
-   Dans Windows NT, Windows 2000, ou les versions ultérieures, la valeur est enregistré dans une clé de Registre.  
  
-   Dans windows 3.x, la valeur est stockée dans le fichier de WIN.INI.  
  
-   Dans Windows 95 et versions ultérieures, la valeur est stockée dans une version mise en cache de WIN.INI.  
  
## Voir aussi  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)
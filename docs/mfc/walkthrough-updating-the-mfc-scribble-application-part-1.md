---
title: "Proc&#233;dure pas &#224; pas&#160;: mise &#224; jour de l&#39;application Scribble MFC (partie&#160;1) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "exemples (C++), mettre à jour des applications existantes"
  - "MFC Feature Pack, mettre à jour des applications existantes"
  - "Office Fluent (interface utilisateur), porter vers"
  - "ruban (interface utilisateur), porter vers"
  - "exemples (C++), mettre à jour des applications existantes"
  - "procédures pas à pas (C++), mettre à jour des applications existantes"
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
caps.latest.revision: 54
caps.handback.revision: 50
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: mise &#224; jour de l&#39;application Scribble MFC (partie&#160;1)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas\-à\-pas explique comment modifier une application MFC existante pour utiliser l'interface utilisateur de ruban.  Visual Studio prend en charge le ruban Office 2007 et le ruban scénique Windows 7.  Pour plus d'informations sur l'interface utilisateur de ruban, consultez [Rubans](http://go.microsoft.com/fwlink/?LinkId=129233) sur le site Web MSDN.  
  
 Cette procédure pas \- à \- pas modifie l'exemple Scribble MFC classique de Scribble 1,0 qui vous permet d'utiliser la souris pour créer des dessins constitués de traits.  Cette partie de la procédure indique comment modifier l'exemple Scribble afin qu'il affiche une barre de ruban.  [Étape 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) ajoute plusieurs boutons à la barre de ruban.  
  
## Composants requis  
 [Exemples Visual C\+\+](../top/visual-cpp-samples.md)  
  
 [Exemples Visual C\+\+](../top/visual-cpp-samples.md)  
  
##  <a name="top"></a> Sections  
 Cette partie de la procédure contient les sections suivantes :  
  
-   [Remplacer les classes de base](#replaceClass)  
  
-   [Ajouter des Bitmaps au projet](#addBitmap)  
  
-   [Ajout d'une ressource de ruban au projet](#addRibbon)  
  
-   [Création d'une instance de la barre de Ruban](#createInstance)  
  
-   [Ajout d'une catégorie ruban](#addCategory)  
  
-   [Définition du style de l'application](#setLook)  
  
##  <a name="replaceClass"></a> Remplacer les classes de base  
 Pour convertir une application qui prend en charge un menu à une application qui prend en charge un ruban, vous devez dériver l'application, la fenêtre frame, et les classes ToolBars des classes de base mises à jour. \(Nous vous suggérons que vous ne modifiez pas l'exemple d'origine Scribble ; à la place, supprimez le projet Scribble, copiez\-le dans un autre répertoire, puis modifiez la copie.\)  
  
#### Pour remplacer les classes de base dans l'application Scribble  
  
1.  Dans scribble.cpp, vérifiez que `CScribbleApp::InitInstance` inclut un appel à [AfxOleInit](../Topic/AfxOleInit.md).  
  
2.  Ajoutez le code suivant au fichier stdafx.h:  
  
    ```  
    #include <afxcontrolbars.h>  
    ```  
  
3.  Dans scribble.h, modifiez la définition de la classe `CScribbleApp` afin qu'elle soit dérivée de [CWinAppEx Class](../mfc/reference/cwinappex-class.md).  
  
    ```  
    class CScribbleApp: public CWinAppEx  
    ```  
  
4.  Scribble 1,0 a été entré lorsque les applications Windows utilisaient un fichier d'initialisation \(.ini\) pour enregistrer des données sur les préférences de l'utilisateur.  Au lieu d'un fichier d'initialisation, modifiez le Scribble pour stocker des préférences utilisateur dans le Registre.  Pour définir la clé de Registre et la base, tapez le code suivant dans `CScribbleApp::InitInstance` après l'instruction `LoadStdProfileSettings()`.  
  
    ```  
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));  
    SetRegistryBase(_T("Settings"));  
    ```  
  
5.  Le frame principal pour une application d'interface multidocument \(MDI\) n'est plus dérivé de la classe `CMDIFrameWnd`.  À la place, il est dérivé de la classe [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md).  
  
     Dans les fichiers mainfrm.h et mainfrm.cpp, remplacez toutes les références à `CMDIFrameWnd` par `CMDIFrameWndEx`.  
  
6.  Dans les fichiers childfrm.h et childfrm.cpp, remplacez `CMDIChildWnd` par `CMDIChildWndEx`.  
  
     Dans le fichier childfrm.h , remplacez `CSplitterWnd` par `CSplitterWndEx`.  
  
7.  Modifiez les barres d'outils et les barres d'état pour utiliser les nouvelles classes MFC.  
  
     Dans le fichier mainfrm.h :  
  
    1.  Remplacez `CToolBar` par `CMFCToolBar`.  
  
    2.  Remplacez `CStatusBar` par `CMFCStatusBar`.  
  
8.  Dans le fichier mainfrm.cpp :  
  
    1.  Remplacez `m_wndToolBar.SetBarStyle` par `m_wndToolBar.SetPaneStyle`  
  
    2.  Remplacez `m_wndToolBar.GetBarStyle` par `m_wndToolBar.GetPaneStyle`  
  
    3.  Remplacez `DockControlBar(&m_wndToolBar)` par `DockPane(&m_wndToolBar)`  
  
9. Dans le fichier d'ipframe.cpp, commentez les trois lignes de code suivantes.  
  
    ```  
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);  
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);  
    pWndFrame->DockPane(&m_wndToolBar);  
    ```  
  
10. Si vous projetez de lier votre application de manière statique, ajoutez le code suivant au début du fichier de ressources du projet \(.rc\).  
  
    ```  
    #include "afxribbon.rc"  
    ```  
  
     Le fichier afxribbon.rc contient les ressources requises au moment de l'exécution.  [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md) inclut automatiquement ce fichier lorsque vous créez une application.  
  
11. Enregistrez tous les changements, puis générez et exécutez l'application.  
  
 \[[Sections](#top)\]  
  
##  <a name="addBitmap"></a> Ajouter des Bitmaps au projet  
 Les quatre étapes suivantes de cette procédure requièrent des ressources bitmap.  Obtenez les bitmaps appropriées de différentes façons :  
  
-   Utilisez [Resource Editors](../mfc/resource-editors.md) pour inventer vos propres bitmaps.  Ou utilisez les éditeurs de ressources pour assembler des bitmaps à partir d'images portables des graphiques de réseau \(.png\) inclus avec [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  Ces images sont dans le répertoire `VS2008ImageLibrary`.  
  
     Toutefois, l'interface utilisateur du ruban exige que certaines bitmap prennent en charge des images transparentes.  Les bitmaps transparentes utilisent les pixels 32 bits, les 24 bits spécifient les composantes rouge, vert, et bleu de la couleur, et les 8 bits définissent *un canal alpha* qui spécifie la transparence de la couleur.  Les éditeurs de ressources actuels peuvent afficher, sans les modifier des bitmaps avec les pixels 32 bits.  Par conséquent, utilisez un éditeur d'image externe au lieu des éditeurs de ressources pour manipuler les bitmaps transparentes.  
  
-   Copiez un fichier de ressources approprié d'une autre application à votre projet puis importez les bitmap à partir de ce fichier.  
  
 Cette procédure pas \- à \- pas copie des fichiers de ressources d'une application dans le répertoire Samples.  
  
#### Pour ajouter des bitmaps au projet  
  
1.  Utilisez l'Explorateur de fichiers pour copier les fichiers suivants .bmp du répertoire Ressources \(`res`\) de l'exemple RibbonGadgets :  
  
    1.  Copiez main.bmp à votre projet Scribble.  
  
    2.  Copiez filesmall.bmp et filelarge.bmp à votre projet Scribble.  
  
    3.  Effectuez les nouvelles copies des fichiers de filelarge.bmp et de filesmall.bmp, mais enregistrer des copies dans l'exemple RibbonGadgets.  Renommez les copies homesmall.bmp et homelarge.bmp puis déplacer les copies à votre projet Scribble.  
  
    4.  Effectuez une copie du fichier de toolbar.bmp, mais enregistrez la copie dans l'exemple RibbonGadgets.  Renommez la copie panelicons.bmp puis déplacez la copie dans votre projet Scribble.  
  
2.  Importer la bitmap pour une application MFC.  Dans **Affichage des ressources**, double\-cliquez sur le nœud **scribble.rc**, double\-cliquez sur le nœud **Bitmap**, puis cliquez sur **Ajouter une ressource**.  Dans la boîte de dialogue qui apparaît, cliquez sur **Installer**.  Accédez au répertoire d'un `res`, sélectionnez le fichier de main.bmp, puis cliquez sur **Ouvrir**.  
  
     La bitmap de main.bmp contient une image 26x26.  Remplacez l'ID de la bitmap à IDB\_RIBBON\_MAIN.  
  
3.  Importez les bitmaps pour le menu fichier associé à la touche application.  
  
    1.  Importer le fichier filesmall.bmp, qui contient dix images 16x16 \(16x160\).  Comme nous avons besoin uniquement huit images 16x16 \(16x128\), utilisez **Affichage des ressources** pour modifier la largeur de cette bitmap de 160 à 128.  Remplacez l'ID de la bitmap à IDB\_RIBBON\_FILESMALL.  
  
    2.  Importez le filelarge.bmp, qui contient huit images 32x32 \(32x256\).  Remplacez l'ID de la bitmap à IDB\_RIBBON\_FILELARGE.  
  
4.  Importez les bitmaps pour les catégories ruban et les panneaux.  Chaque onglet de la barre de ruban est une catégorie, et se compose d'une étiquette de texte et d'une image facultative.  
  
    1.  Importer la bitmap de homesmall.bmp, qui contient huit images 16x16 pour les petites bitmap de bouton.  Remplacez l'ID de la bitmap à IDB\_RIBBON\_HOMESMALL.  
  
    2.  Importer la bitmap de homelarge.bmp, qui contient huit images 32x32 pour les grandes bitmap de bouton.  Remplacez l'ID de la bitmap à IDB\_RIBBON\_HOMELARGE.  
  
5.  Importez les bitmaps pour les panneaux redimensionnés de ruban.  Ces bitmaps, ou icônes du panneau, sont utilisées après une opération de redimensionnement si le ruban est trop petit pour afficher le Panel.  
  
    1.  Importer la bitmap de panelicons.bmp, qui contient huit images 16x16.  Dans la fenêtre **Propriétés Éditeur de bitmaps**, ajustez la largeur de la bitmap à 64 \(16x64\).  Remplacez l'ID de la bitmap à IDB\_PANEL\_ICONS.  
  
 \[[Sections](#top)\]  
  
##  <a name="addRibbon"></a> Ajout d'une ressource de ruban au projet  
 Lorsque vous convertissez une application qui utilise des menus à une application qui utilise un ruban, vous ne devez pas supprimer ou désactiver les menus existants.  À la place, vous créez une ressource de ruban, ajoutez des boutons de ruban, puis associez les nouveaux boutons avec des éléments de menu existants.  Bien que les menus ne sont plus visibles, les messages de la barre du ruban sont routés via les menus.  En outre, les raccourcis de menu continuent à fonctionner.  
  
 Un ruban comprend la touche application, qui est le grand bouton du côté supérieur gauche du ruban, et un ou plusieurs onglets de catégorie.  Chaque onglet de catégorie contient un ou plusieurs panneaux qui agissent comme conteneurs pour les boutons et des contrôles de ruban.  La procédure suivante indique comment créer une ressource de ruban puis personnaliser la touche application.  
  
#### Pour ajouter une ressource de ruban au projet  
  
1.  Dans le menu **Projet**, cliquez sur **Ajouter une Ressource**.  
  
2.  Dans la boîte de dialogue **Ajouter une nouvelle ressource**, sélectionnez **Ruban \(Concepteur visuel\)** puis cliquez sur **Nouveau**.  
  
     Visual Studio crée un ruban de ressources et l'ouvre dans le concepteur.  L'ID de ressource de ruban est IDR\_RIBBON1, qui s'affiche dans **Affichage des ressources**.  Le ruban contient une catégorie et un panneau.  
  
3.  Personnalisez la touche application en modifiant ses propriétés.  Les ID de message utilisés dans ce code sont déjà définis dans le menu pour le Scribble 1,0.  
  
4.  En mode Design, cliquez sur la touche application pour afficher ses propriétés.  Changez les valeurs de propriété comme suit: **Image** en `IDB_RIBBON_MAIN`, `Fichier`en **Invite** , **Clés** en `f`, `IDB_RIBBON_FILELARGE`en **Grandes images**, et **Petites images** en `IDB_RIBBON_FILESMALL`.  
  
5.  Les modifications suivantes créent le menu apparaissant lorsque l'utilisateur clique sur la touche application.  Cliquez sur le bouton de sélection \(**...**\) à côté de **Éléments principaux** pour ouvrir **Éditeur d'éléments**.  
  
    1.  Cliquez sur **Ajouter** pour ajouter un bouton.  Remplacez **Légende** par `&New`, **ID** par `ID_FILE_NEW`, **Image** par `0`, **Grande image** par `0`.  
  
    2.  Cliquez sur le bouton **Ajouter** pour ajouter un groupe.  Remplacez **Légende** par `&Save`, **ID** par `ID_FILE_SAVE`, **Image** par `2`, puis **Grande image** par `2`.  
  
    3.  Cliquez sur le bouton **Ajouter** pour ajouter un troisième boutton.  Remplacez **Légende** par `Save &As`, **ID** par `ID_FILE_SAVE_AS`, **Image** par `3`, puis **Grande image** par `3`.  
  
    4.  Cliquez sur le bouton **Ajouter** pour ajouter un quatrième bouton.  Remplacez **Légende** par `&Imprimer`, **ID** par `ID_FILE_PRINT`, **Image** par `4`, puis **Grande image** par `4`.  
  
    5.  Modifiez le type **Élément** à **Séparateur** puis cliquez sur **Ajouter**.  
  
    6.  Modifiez le type **Élément** par **Bouton**.  Cliquez sur le bouton **Ajouter** pour ajouter un cinquième bouton.  Remplacez **Légende** par `&Fermer`, **ID** par `ID_FILE_CLOSE`, **Image** par `5`, puis **Grande image** par `5`.  
  
6.  Les modifications suivantes créent un sous\-menu sous le bouton Imprimer créée à l'étape précédente.  
  
    1.  Cliquez sur le bouton **Imprimer**, remplacez le type **Élément** par **Étiquette**, puis cliquez sur **Insérer**.  Remplacez **Légende** par `Afficher un aperçu et imprimer le document`.  
  
    2.  Cliquez sur le bouton **Imprimer** , remplacez le type **Élément** par **Étiquette**, puis cliquez sur **Insérer**.  Remplacez **Légende** par `&Imprimer`, **ID** par `ID_FILE_PRINT`, **Image** par `4`, puis **Grande image** par `4`.  
  
    3.  Cliquez sur le bouton **Imprimer** puis cliquez sur **Insérer** pour ajouter un bouton.  Remplacez **Légende** par `&Impression Rapide`, **ID** par `ID_FILE_PRINT_DIRECT`, **Image** par `7`, puis **Grande image** par `7`.  
  
    4.  Cliquez sur le bouton **Imprimer** puis cliquez sur **Insérer** pour ajouter un autre bouton.  Remplacez **Légende** par `Copie Pre&affichage`, par **ID** la valeur `ID_FILE_PRINT_PREVIEW`, **Image** par `6`, puis **Grande image** par`6`.  
  
    5.  Vous avez maintenant modifié les **Éléments principaux**.  Cliquez sur **Fermer** pour quitter **Éditeur d'éléments**.  
  
7.  La modification suivante crée un bouton de sortie qui apparaît en bas du menu de touche application.  
  
    1.  Dans la fenêtre **Propriétés**, cliquez sur le bouton de sélection \(\) situé à côté de **Bouton** pour ouvrir **Editeur d'éléments**.  
  
    2.  Cliquez sur **Ajouter** pour ajouter un bouton.  Remplacez **Légende** par `E&xit`, **ID** par `ID_APP_EXIT`, **Image** par`8`.  
  
 \[[Sections](#top)\]  
  
##  <a name="createInstance"></a> Création d'une instance de la barre de Ruban  
 Les étapes suivantes indiquent comment créer une instance de la barre de ruban lorsque votre application démarre.  Pour ajouter une barre Ruban à une application, déclarez la barre du ruban dans le fichier mainfrm.h.  Puis, dans le fichier mainfrm.cpp, écrivez du code pour charger la ressource de ruban.  
  
#### Pour créer une instance de la barre de ruban  
  
1.  Dans le fichier de mainfrm.h, ajoutez une donnée membre à la section protégée `CMainFrame`, la définition de classe du frame principal.  Ce membre représente la barre de ruban.  
  
    ```  
    // Ribbon bar for the application  
    CMFCRibbonBar  m_wndRibbonBar;  
    ```  
  
2.  Dans le fichier mainfrm.cpp, ajoutez le code suivant avant l'instruction `return` finale à la fin de la fonction `CMainFrame::OnCreate`.  Cela crée une instance de barre de ruban.  
  
    ```  
    // Create the ribbon bar  
    if (!m_wndRibbonBar.Create(this))  
    {  
    return -1;   //Failed to create ribbon bar  
    }  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);  
    ```  
  
 \[[Sections](#top)\]  
  
##  <a name="addCategory"></a> Personnalisation de la ressource de ruban  
 Maintenant que vous avez créé la touche application, vous pouvez ajouter des éléments au ruban.  
  
> [!NOTE]
>  Cette procédure pas \- à \- pas utilise la même icône du panneau pour tous les panneaux.  Toutefois, vous pouvez utiliser d'autres index de liste d'images pour afficher d'autres icônes.  
  
#### Pour ajouter une catégorie et un panneau d'accueil de modification  
  
1.  Le programme Scribble requiert une seule catégorie.  En mode Design, cliquez sur **Catégorie** pour afficher ses propriétés.  Changez les valeurs de propriété comme suit: **Légende** en `&Home`, **Grandes images** en `IDB_RIBBON_HOMELARGE`, **Petites images** en `IDB_RIBBON_HOMESMALL`.  
  
2.  Chaque catégorie ruban est organisée en panneaux nommés.  Chaque panneau contient un ensemble de contrôles qui exécutent des opérations connexes.  Cette catégorie a un panneau.  Cliquez sur **Volet**, puis remplacez **Légende** par `Modification` et **Index de l'image** par `0`.  
  
3.  Dans le panneau **Edition**, ajoutez un bouton qui est responsable du dédouanement du contenu du document.  ID de message pour ce bouton a déjà été défini dans la ressource menu en IDR\_SCRIBBTYPE.  Spécifiez `Effacer tous` comme texte du bouton et index de la bitmap qui décore le bouton.  Ouvrez **Boîte à outils**, puis faites glisser **Bouton** dans le panneau **Edition**.  Cliquez sur le bouton et remplacez **Légende** par `Effacer tous`, **ID** par `ID_EDIT_CLEAR_ALL`, **Index de l'image** par `0`, **Grand index d'image** par `0`.  
  
4.  Enregistrez tous les changements, puis générez et exécutez l'application.  L'application Scribble doit être affichée, elle doit comporter une barre de ruban en haut de la fenêtre au lieu d'une barre de menus.  La barre de ruban doit avoir une catégorie, **Accueil**, et **Accueil** doit avoir un panneau, **Edition**.  Les boutons de ruban que vous avez ajouté doivent être associés aux gestionnaires d'événements existants, sur **Ouvrir**, **Fermer**, **Enregistrer**, **Imprimer**, et les boutons **Effacer tout** doivent fonctionner comme prévu.  
  
 \[[Sections](#top)\]  
  
##  <a name="setLook"></a> Définition du style de l'application  
 Un *gestionnaire visuel* est un objet global qui contrôle tout le dessin pour une application.  Puisque l'application d'origine Scribble utilise le style d'interface utilisateur \(UI\) Office 2000, l'application peut paraître un peu daté.  Réinitialisez l'application pour utiliser le Gestionnaire visuel Office 2007 afin qu'elle ressemble à une application Office 2007.  
  
#### Pour définir l'aspect de l'application  
  
1.  Dans la fonction `CMainFrame::OnCreate`, tapez le code suivant pour modifier le gestionnaire et le style visuels par défaut.  
  
    ```  
    // Set the default manager to Office 2007   
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));  
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);  
    ```  
  
2.  Enregistrez tous les changements, puis générez et exécutez l'application.  L'interface utilisateur d'application doit ressembler à Office 2007 interface utilisateur.  
  
 \[[Sections](#top)\]  
  
## Étapes suivantes  
 Vous avez modifié l'exemple Scribble MFC classique de Scribble 1,0 pour utiliser le Concepteur de ruban.  Maintenant allez à [l'Étape2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md).  
  
## Voir aussi  
 [procédures pas à pas](../mfc/walkthroughs-mfc.md)   
 [Procédure pas à pas : mise à jour de l'application Scribble MFC \(partie 2\)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)
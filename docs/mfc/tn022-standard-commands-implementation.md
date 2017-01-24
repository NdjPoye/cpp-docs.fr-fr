---
title: "TN022&#160;: impl&#233;mentation de commandes standard | Microsoft Docs"
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
  - "vc.commands"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "commandes, standard"
  - "ID_APP_ABOUT (commande)"
  - "ID_APP_EXIT (commande)"
  - "ID_CONTEXT_HELP (commande)"
  - "ID_DEFAULT_HELP (commande)"
  - "ID_EDIT_CLEAR (commande)"
  - "ID_EDIT_CLEAR_ALL (commande)"
  - "ID_EDIT_COPY (commande)"
  - "ID_EDIT_CUT (commande)"
  - "ID_EDIT_FIND (commande)"
  - "ID_EDIT_PASTE (commande)"
  - "ID_EDIT_PASTE_LINK (commande)"
  - "ID_EDIT_PASTE_SPECIAL (commande)"
  - "ID_EDIT_REDO (commande)"
  - "ID_EDIT_REPEAT (commande)"
  - "ID_EDIT_REPLACE (commande)"
  - "ID_EDIT_SELECT_ALL (commande)"
  - "ID_EDIT_UNDO (commande)"
  - "ID_FILE_CLOSE (commande)"
  - "ID_FILE_NEW (commande)"
  - "ID_FILE_OPEN (commande)"
  - "ID_FILE_PAGE_SETUP (commande)"
  - "ID_FILE_PRINT (commande)"
  - "ID_FILE_PRINT_PREVIEW (commande)"
  - "ID_FILE_PRINT_SETUP (commande)"
  - "ID_FILE_SAVE (commande)"
  - "ID_FILE_SAVE_AS (commande)"
  - "ID_FILE_SAVE_COPY_AS (commande)"
  - "ID_FILE_UPDATE (commande)"
  - "ID_HELP (commande)"
  - "ID_HELP_INDEX (commande)"
  - "ID_HELP_USING (commande)"
  - "ID_INDICATOR_CAPS (commande)"
  - "ID_INDICATOR_EXT (commande)"
  - "ID_INDICATOR_KANA (commande)"
  - "ID_INDICATOR_NUM (commande)"
  - "ID_INDICATOR_OVR (commande)"
  - "ID_INDICATOR_REC (commande)"
  - "ID_INDICATOR_SCRL (commande)"
  - "ID_NEXT_PANE (commande)"
  - "ID_OLE_EDIT_LINKS (commande)"
  - "ID_OLE_INSERT_NEW (commande)"
  - "ID_OLE_VERB_FIRST (commande)"
  - "ID_PREV_PANE (commande)"
  - "ID_VIEW_STATUS_BAR (commande)"
  - "ID_VIEW_TOOLBAR (commande)"
  - "ID_WINDOW_ARRANGE (commande)"
  - "ID_WINDOW_CASCADE (commande)"
  - "ID_WINDOW_NEW (commande)"
  - "ID_WINDOW_SPLIT (commande)"
  - "ID_WINDOW_TILE_HORZ (commande)"
  - "ID_WINDOW_TILE_VERT (commande)"
  - "commandes standard"
  - "TN022"
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN022&#160;: impl&#233;mentation de commandes standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit les implémentations standard de commandes fournies par MFC 2.0.  Lisez [Note technique 21](../mfc/tn021-command-and-message-routing.md) d'abord car elle décrit les mécanismes pour implémenter plusieurs commandes standard.  
  
 Cette procédure suppose une connaissance des architectures de MFC, des API, et de la pratique de la programmation commune.  Les API d'"implémentation seule" documentées ainsi que non documentées sont décrites.  Cet article n'est pas adapté pour commencer à apprendre les fonctionnalités de MFC ou comment programmer avec.  Reportez\-vous à Visual C\+\+ pour plus d'informations générales et pour les détails des API documentées.  
  
## Le problème  
 MFC définit un grand nombre de commandes standard dans le fichier d'en\-tête AFXRES.H.  La prise en charge de l'infrastructure de ces commandes varie.  La compréhension de où et comment les classes du framework gèrent ces commandes vous permet non seulement de voir comment le framework s'exécute en interne mais fournit aussi des informations utiles sur la façon de personnaliser les implémentations standard et vous enseigne sur les techniques permettant d'implémenter vos propres gestionnaires de commandes.  
  
## Contenu de la note technique  
 Chaque ID de commande est décrit dans deux sections :  
  
-   Le titre : le nom symbolique de l'ID de commande \(par exemple, **ID\_FILE\_SAVE**\) suivi de l'objectif de la commande \(par exemple, « enregistre le document actif »\) séparées par un deux\-points.  
  
-   Un ou de plusieurs paragraphes décrivent quelles classes implémentent la commande, ainsi que ce que l'implémentation par défaut fait.  
  
 La plupart des implémentations de commande par défaut sont précablées dans la table des messages de la classe de base du framework.  Certaines implémentations de commande qui requièrent un câblage explicite dans votre classe dérivée.  Elles sont décrites dans la section « remarque ».  Si vous choisissez les options correctes dans AppWizard, les gestionnaires par défaut sont connectés pour vous dans l'application squelette générée.  
  
## Convention d'affectation de noms  
 Les commandes standard suivent la convention d'affectation des noms simples que nous vous recommandons d'utiliser si possible.  La plupart des commandes standard sont situées dans les emplacements standard dans la barre de menus d'une application.  Le nom symbolique de début de commande commence avec « ID\_ » suivi du nom de menu contextuel standard, suivi par le nom de l'élément de menu.  Le nom symbolique est en majuscules avec les divisions entre mots avec des trait de soulignement \(\_\).  Pour les commandes qui n'ont pas de noms d'élément de menu standard, le nom de commande logique est commence par « ID\_ » \(par exemple, **ID\_NEXT\_PANE**\).  
  
 Nous utilisons le préfixe « ID\_ » pour afficher les commandes qui sont conçues pour être liées aux éléments de menu, boutons de la barre d'outils, ou à d'autres objets interface utilisateur de commande.  Les gestionnaires de commandes gestion des commandes « ID\_ » doivent utiliser `ON_COMMAND` et les mécanismes `ON_UPDATE_COMMAND_UI` de l'architecture commande MFC.  
  
 Nous vous recommandons d'utiliser le préfixe standard « IDM\_ » pour les éléments de menu qui ne respectent pas l'architecture de commande et ont besoin d'un code de menu spécifique pour les activer et désactiver.  Naturellement le nombre de commandes spécifiques au menu doit être faible puisque l'architecture de commande de MFC rend non seulement les gestionnaires de commandes plus puissants \(car ils travaillent avec des barres d'outils\) mais rend aussi le code du gestionnaire de commandes réutilisable.  
  
## Plages d'identité  
 Rendez\-vous sur [Note technique 20](../mfc/tn020-id-naming-and-numbering-conventions.md) pour plus d'informations sur l'utilisation des plages d'ID de MFC.  
  
 Les commandes standard de MFC se situent dans la plage 0xE000 à 0xEFFF.  Veuillez ne pas compter sur des valeurs spécifiques de ces ID car elles sont susceptibles d'être modifiées dans les versions ultérieures de la bibliothèque.  
  
 Votre application doit définir les commandes contenues dans la plage 0x8000 à 0xDFFF.  
  
## ID de commandes standard  
 Pour chaque ID de commande, il existe une chaîne d'invite standard de message se trouvant dans le fichier PROMPTS.RC.  L'ID de chaîne de cette invite de menu doit être identique à l'ID de commande.  
  
-   ID\_FILE\_NEW crée un nouveau\/vide document.  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     `CWinApp::OnFileNew` implémente cette commande différemment en fonction du nombre de modèles de document dans l'application.  S'il n'existe qu'un seul `CDocTemplate`, `CWinApp::OnFileNew` crée un document de ce type, ainsi que le cadre et la classe d'affichage appropriés.  
  
     S'il existe plusieurs `CDocTemplate`, `CWinApp::OnFileNew` invite l'utilisateur avec une boîte de dialogue \(**AFX\_IDD\_NEWTYPEDLG**\) permettant de sélectionner le type de document à utiliser.  Le `CDocTemplate` sélectionné est utilisé pour créer le document.  
  
     Une personnalisation courante de `ID_FILE_NEW` est de fournir un choix différent et plus graphique des types de documents.  Dans ce cas vous pouvez implémenter votre propre **CMyApp::OnFileNew** et le placer dans la table des messages à la place de `CWinApp::OnFileNew`.  Il n'est pas nécessaire d'appeler l'implémentation de la classe de base.  
  
     Une autre personnalisation courante de `ID_FILE_NEW` est de fournir une commande distincte pour créer un document de chaque type.  Dans ce cas vous devez définir de nouveaux ID de commande, par exemple ID\_FILE\_NEW\_CHART et ID\_FILE\_NEW\_SHEET.  
  
-   ID\_FILE\_OPEN ouvre un document existant.  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     `CWinApp::OnFileOpen` a une implémentation d'appel très simple **CWinApp::DoPromptFileName** suivie de `CWinApp::OpenDocumentFile` avec le fichier ou le chemin d'accès du fichier à ouvrir.  La routine d'implémentation `CWinApp` **DoPromptFileName** ouvre la boîte de dialogue FileOpen et la remplit avec les extensions de fichier obtenues à partir de modèles de document actuels.  
  
     Une personnalisation courante de `ID_FILE_OPEN` est de personnaliser la boîte de dialogue FileOpen ou d'ajouter des filtres de fichiers supplémentaires.  La méthode recommandée pour personnaliser cela consiste à remplacer l'implémentation par défaut par votre propre boîte de dialogue FileOpen, puis appeler `CWinApp::OpenDocumentFile` avec fichier ou le chemin d'accès du document.  Il n'est pas nécessaire d'appeler la classe de base.  
  
-   ID\_FILE\_CLOSE ferme le document actuellement ouvert.  
  
     **CDocument::OnFileClose** appelle `CDocument::SaveModified` pour inviter l'utilisateur à enregistrer le document s'il a été modifié puis appelle `OnCloseDocument`.  Toute la logique de fermeture, notamment la destruction document, est fait dans la routine `OnCloseDocument`.  
  
    > [!NOTE]
    >  **ID\_FILE\_CLOSE** agit différemment depuis un message`WM_CLOSE` ou une commande système **SC\_CLOSE** adressée à la fenêtre cadre de documents.  Fermer une fenêtre ferme le document uniquement si c'est la dernière fenêtre cadre du document.  Fermer le document avec **ID\_FILE\_CLOSE** ferme non seulement le document mais elle ferme toutes les fenêtres cadres affichant le document.  
  
-   ID\_FILE\_SAVE enregistre le document actuel.  
  
     L'implémentation utilise un programme d'assistance **CDocument::DoSave** utilisé pour **OnFileSave** et **OnFileSaveAs**.  Si vous enregistrez un document qui n'a pas été enregistré avant \(autrement dit, il n'a pas de nom de chemin d'accès, comme dans le cas de FileNew\) ou qui a été lu par un document en lecture seule, la logique **OnFileSave** se comportera comme la commande **ID\_FILE\_SAVE\_AS** et demandera à l'utilisateur de fournir un nouveau nom de fichier.  Le processus d'ouverture de fichier et de sauvagerde s'effectue via la fonction virtuelle `OnSaveDocument`.  
  
     Il existe deux raisons communes pour personnaliser **ID\_FILE\_SAVE**.  Pour les documents qui ne s'enregistrent pas, supprimez simplement les éléments de menu et les boutons de la barre d'outils **ID\_FILE\_SAVE** de l'interface utilisateur.  Veillez à ce que vous ne salissiez jamais votre document \(autrement dit, n'appelez jamais `CDocument::SetModifiedFlag`\) et le framework n'entraînera jamais l'enregistrement du document.  Pour les documents qui s'enregistrent dans un autre emplacement qu'un fichier de disque, attribuez une nouvelle commande pour cette opération.  
  
     Dans le cas d'un `COleServerDoc`, **ID\_FILE\_SAVE** est utilisé pour la sauvegarde du fichier \(de documents standard\) et la mise à jour de fichiers \(pour les documents imbriqués\).  
  
     Si vos données de document sont stockées dans plusieurs fichiers disque, mais vous ne souhaitez pas utiliser l'implémentation de sérialisation par défaut **CDocument**, vous devez remplacer `CDocument::OnSaveDocument` au lieu de **OnFileSave**.  
  
-   ID\_FILE\_SAVE\_AS enregistre le document actuel sous un nom de fichier différent.  
  
     L'implémentation de **CDocument::OnFileSaveAs** utilise la même routine d'assistance **CDocument::DoSave** que **OnFileSave**.  La commande **OnFileSaveAs** est gérée comme **ID\_FILE\_SAVE** si les documents n'avait aucun nom de fichier avant la sauvegarde.  **COleServerDoc::OnFileSaveAs** implémente la logique pour un fichier de données standard de document ou pour enregistrer un document serveur représentant un objet OLE incorporé dans une autre application en tant que fichier CSV.  
  
     Si vous personnalisez la logique de **ID\_FILE\_SAVE**, vous souhaiterez éventuellement personnaliser **ID\_FILE\_SAVE\_AS** de la même façon ou l'opération "sauvegarde sous" ne peut pas s'appliquer à votre document.  Vous pouvez supprimer l'élément de menu de la barre de menus si elle n'est pas nécessaire.  
  
-   ID\_FILE\_SAVE\_COPY\_AS stocke une copie du document actif sous un nouveau nom.  
  
     L'implémentation de **COleServerDoc::OnFileSaveCopyAs** est très similaire à **CDocument::OnFileSaveAs**, sauf que l'objet document « n'est pas attaché » au fichier sous\-jacent après la sauvegarde.  Autrement dit, si le document en mémoire « a été modifié » avant la sauvegarde, il est toujours "modifié".  Par ailleurs, cette commande n'a aucun effet sur le chemin d'accès ou le titre stocké dans le document.  
  
-   ID\_FILE\_UPDATE notifie le conteneur d'enregistrer le document incorporé.  
  
     L'implémentation de `COleServerDoc::OnUpdateDocument` notifies simplement le conteneur que l'incorporation doit être enregistrée.  Le conteneur appelle les API OLE appropriées pour enregistrer l'objet incorporé.  
  
-   ID\_FILE\_PAGE\_SETUP appelle une boîte de dialogue spécifique à l'application de mise en page et la mise en page.  
  
     Actuellement il n'existe aucun standard pour cette boîte de dialogue, et le framework n'a pas d'implémentation par défaut de cette commande.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_FILE\_PRINT\_SETUP appelle la boîte de dialogue standard de configuration de l'impression.  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     Cette commande appelle la boîte de dialogue standard de configuration de l'impression qui permet à l'utilisateur de personnaliser les paramètres d'impression et l'imprimante pour au moins ce document ou au plus tous les documents dans cette application.  Vous devez utiliser le panneau de configuration pour modifier les paramètres d'impression par défaut pour le système entier.  
  
     `CWinApp::OnFilePrintSetup` a une implémentation simple pour créer un objet `CPrintDialog` et appeler la fonction d'implémentation **CWinApp::DoPrintDialog**.  Cela définit l'installation de l'imprimante par défaut de l'application.  
  
     Le besoin courant de personnaliser cette commande est de permettre des paramètres d'imprimante pour chaque document, qui doivent être enregistrés avec le document une fois enregistrés.  Pour ce faire vous devez ajouter un gestionnaire de table des messages dans la classe de **CDocument** qui crée un objet `CPrintDialog`, l'initialise avec les attributs appropriés d'imprimantes \(généralement **hDevMode** et **hDevNames**\), appelle **CPrintDialog::DoModal,** et enregistre les paramètres d'imprimante modifiés.  Pour une implémentation fiable, vous devez examiner l'implémentation de **CWinApp::DoPrintDialog** pour détecter les erreurs et **CWinApp::UpdatePrinterSelection** pour traiter les défauts sensibles et suivre les modifications au niveau du système d'imprimante.  
  
-   ID\_FILE\_PRINT  Impression standard du document actif  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CView` pour activer cette fonctionnalité.  
  
     Cette commande affiche le document actuel, ou plus précisément, démarre le processus d'impression, qui consiste à appeler la boîte de dialogue Imprimer standard et lancer le moteur d'impression.  
  
     **CView::OnFilePrint** implémente cette commande et la boucle principale d'impression.  Il appelle le `CView::OnPreparePrinting` virtuel à inviter l'utilisateur avec la boîte de dialogue Imprimer.  Cela prépare la sortie contrôleur de domaine à accéder à l'imprimante, fournit la boîte de dialogue de progression d'impression \(**AFX\_IDD\_PRINTDLG**\), puis envoie la séquence d'échappement `StartDoc` à l'imprimante.  **CView::OnFilePrint** contient également la principale boucle d'impression \(orientée page\).  Pour chaque page, cela appelle le `CView::OnPrepareDC` virtuel suivi d'une séquence d'échappement `StartPage` et appelle le `CView::OnPrint` virtuel pour cette page.  Lorsque vous avez terminé, le `CView::OnEndPrinting` virtuel est appelé, et la boîte de dialogue de progression d'impression est fermée.  
  
     L'architecture d'impression MFC est destinée à donner de nombreuses manières d'imprimer et de nombreux aperçus avant impression.  Vous trouverez généralement des fonctions substituables `CView` appropriées pour toutes les tâches orientées page pour l'impression.  Uniquement dans le cas d'une application qui utilise la sortir non orienté page de l'imprimante, si vous recherchez le besoin de remplacer l'implémentation de **ID\_FILE\_PRINT**.  
  
-   ID\_FILE\_PRINT\_PREVIEW Lance le mode aperçu avant impression du document actuel.  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CView` pour activer cette fonctionnalité.  
  
     **CView::OnFilePrintPreview** démarre le mode aperçu avant impression en appelant la fonction d'assistance documentée **CView::DoPrintPreview**.  **CView::DoPrintPreview** est le moteur principal pour la boucle d'aperçu avant impression, comme **OnFilePrint** est le moteur principal pour la boucle d'impression.  
  
     L'aperçu avant impression peut être personnalisé de plusieurs façons en passant des paramètres à **DoPrintPreview**.  Rendez\-vous sur [Note technique 30](../mfc/tn030-customizing-printing-and-print-preview.md), qui traite de certains détails de l'aperçu avant impression et comment le personnaliser.  
  
-   **ID\_FILE\_MRU\_FILE1**…**FILE16**  Une plage d'ID de commande pour le fichier MRU `list`.  
  
     **CWinApp::OnUpdateRecentFileMenu** est un gestionnaire de commande interface utilisateur de mise à niveau qui est l'une des utilisations avancées du mécanisme `ON_UPDATE_COMMAND_UI`.  Dans le menu ressource, il vous suffit de définir un élément de menu avec ID **ID\_FILE\_MRU\_FILE1**.  Cet élément de menu demeure initialement désactivé.  
  
     Lorsque la liste des fichiers récents augmente, plus d'éléments de menu sont ajoutés à la liste.  L'implémentation `CWinApp` standard a par défaut la limite standard des quatre fichiers récemment utilisés.  Vous pouvez modifier le paramètre par défaut en appelant `CWinApp::LoadStdProfileSettings` avec une plus grande ou une plus petite valeur.  La liste des fichiers récents est stockée dans le fichier .ini de l'application.  La liste est chargée dans la fonction `InitInstance` de votre application si vous appelez `LoadStdProfileSettings`, et n'est pas sauvegardée lorsque votre application se termine.  Le gestionnaire de commande interface utilisateur de mise à jour de MRU convertit également les chemins d'accès absolu en chemins d'accès relatifs à des fins de affichage dans le menu fichier.  
  
     **CWinApp::OnOpenRecentFile** est le gestionnaire `ON_COMMAND` qui effectue la commande réelle.  Il récupère simplement le nom de fichier de la liste des fichiers récents et appelle `CWinApp::OpenDocumentFile`, qui effectue le travail d'ouverturer du fichier et de mise à jour de la liste des fichiers récents.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_EDIT\_CLEAR désactive la sélection actuelle  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande utilisant `CEdit::Clear`.  La commande est désactivée si il n'y a aucune sélection actuelle.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_CLEAR\_ALL désactive le document.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  Consultez l'exemple du tutoriel MFC [DESSIN A MAIN LEVÉE](../top/visual-cpp-samples.md) pour un exemple d'implémentation.  
  
-   ID\_EDIT\_COPY   Copie la sélection active vers le Presse\-papiers.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande, qui copie le texte actuellement sélectionné dans le presse\-papiers comme CF\_TEXT en utilisant `CEdit::Copy`.  La commande est désactivée si il n'y a aucune sélection actuelle.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_CUT   Coupe la sélection active dans le Presse\-papiers.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande, qui coupe le texte actuellement sélectionné dans le presse\-papiers comme CF\_TEXT en utilisant `CEdit::Cut`.  La commande est désactivée si il n'y a aucune sélection actuelle.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_FIND démarre l'opération de recherche, fournit la boîte de dialogue non modale de recherche.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande, qui appelle la fonction d'assistance à l'implémentation **OnEditFindReplace** pour utiliser et stocker les paramètres précédents de recherche\/remplacement dans des variables privées d'implémentation.  La classe `CFindReplaceDialog` est utilisée pour gérer la boîte de dialogue non modale dans ses invites utilisateur.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_PASTE insère le contenu actuel du presse\-papiers.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande, qui copie les données du Presse\-papiers en remplaçant le texte sélectionné en utilisant `CEdit::Paste`.  La commande est désactivée s'il n'existe aucun **CF\_TEXT** dans le presse\-papiers.  
  
     **COleClientDoc** fournit simplement un gestionnaire d'interface utilisateur de commande de mise à jour pour cette commande.  Si le presse\-papiers ne contient pas d'élément\/objet encastrables OLE , la commande est désactivée.  Vous êtes chargé d'écrire le gestionnaire pour que la commande réelle fasse le collage.  Si votre application OLE peut également coller d'autres formats, vous devez fournir votre propre gestionnaire d'interface utilisateur de commande de mise à jour dans votre vue ou document \(autrement dit, quelque part avant **COleClientDoc** dans le routage de cible de commande\).  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
     Pour remplacer l'implémentation standard OLE, utilisez `COleClientItem::CanPaste`.  
  
-   ID\_EDIT\_PASTE\_LINK insère un lien du contenu actuel du presse\-papiers.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `COleDocument` fournit simplement un gestionnaire d'interface utilisateur de commande de mise à jour pour cette commande.  Si le presse\-papiers ne contient pas d'élément\/objet encastrables OLE pouvant être lié, la commande est désactivée.  Vous êtes chargé d'écrire le gestionnaire pour que la commande réelle fasse le collage.  Si votre application OLE peut également coller d'autres formats, vous devez fournir votre propre gestionnaire d'interface utilisateur de commande de mise à jour dans votre vue ou document \(autrement dit, quelque part avant  `COleDocument` dans le routage de cible de commande\).  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
     Pour remplacer l'implémentation standard OLE, utilisez `COleClientItem::CanPasteLink`.  
  
-   ID\_EDIT\_PASTE\_SPECIAL insère le contenu actuel du presse\-papiers avec les options.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  MFC ne fournit pas cette boîte de dialogue.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_REPEAT répète la dernière opération.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande pour répéter la dernière opération de recherche.  Les variables privées d'implémentation de la dernière recherche sont utilisées.  La commande est désactivée si une recherche ne peut pas être tentée.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_REPLACE démarre l'opération de remplacement, fournit la boîte de dialogue non modale de remplacement.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande, qui appelle la fonction d'assistance à l'implémentation **OnEditFindReplace** pour utiliser et stocker les paramètres précédents de recherche\/remplacement dans des variables privées d'implémentation.  La classe `CFindReplaceDialog` est utilisée pour gérer la boîte de dialogue non modale dans ses invites utilisateur.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_SELECT\_ALL sélectionne le document.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande, qui sélectionne le texte du document.  La commande est désactivée s'il n'y a aucun texte à sélectionner.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_UNDO annule la dernière opération.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     `CEditView` fournit une implémentation de cette commande utilisant `CEdit::Undo`.  La commande est désactivée si `CEdit::CanUndo` retourne FALSE.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_EDIT\_REDO renouvelle la dernière opération.  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette opération pour chaque `CView`\- classe dérivée.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_WINDOW\_NEW ouvre une fenêtre dans le document actif.  
  
     **CMDIFrameWnd::OnWindowNew** implémente cette fonctionnalité puissante à l'aide du modèle de document du document actif pour créer un autre cadre contenant une autre vue du document actif.  
  
     Comme la plupart des commandes de menu Fenêtre de l'interface de documents multiples \(MDI\), la commande est désactivée s'il n'y a aucune fenêtre enfant MDI active.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  Si vous souhaitez fournir une commande qui crée des vues supplémentaires ou des cadres de fenêtres, il vous sera peut être plus aisé d'inventer votre propre commande.  Vous pouvez dupliquer le code de **CMDIFrameWnd::OnWindowNew** et le modifier pour donner le cadre et les classes de vue de votre goût.  
  
-   ID\_WINDOW\_ARRANGE organise les icônes en bas d'une fenêtre MDI.  
  
     `CMDIFrameWnd` implémente cette commande standard MDI dans une fonction d'assistance à l'implémentation **OnMDIWindowCmd**.  Le programme d'assistance mappe les ID de commande aux messages MDI Windows et peut donc partager beaucoup de code.  
  
     Comme la plupart des commandes de menu Fenêtre de l'interface de documents multiples \(MDI\), la commande est désactivée s'il n'y a aucune fenêtre enfant MDI active.  
  
     La personnalisation de ce gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_WINDOW\_CASCADE empile les fenêtre pour qu'elles se chevauchent.  
  
     `CMDIFrameWnd` implémente cette commande standard MDI dans une fonction d'assistance à l'implémentation **OnMDIWindowCmd**.  Le programme d'assistance mappe les ID de commande aux messages MDI Windows et peut donc partager beaucoup de code.  
  
     Comme la plupart des commandes de menu Fenêtre de l'interface de documents multiples \(MDI\), la commande est désactivée s'il n'y a aucune fenêtre enfant MDI active.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_WINDOW\_TILE\_HORZ Met les fenêtres en mosaïques horizontalement.  
  
     Cette commande est implémentée dans `CMDIFrameWnd` comme **ID\_WINDOW\_CASCADE**, à moins qu'un message différent MDI Windows soit utilisé pour l'opération.  
  
     Vous devez choisir l'orientation par défaut de mosaïque pour votre application.  Vous pouvez le faire en modifiant l'ID de l'élément de menu « mosaïque » de fenêtre en **ID\_WINDOW\_TILE\_HORZ** ou en **ID\_WINDOW\_TILE\_VERT**.  
  
-   ID\_WINDOW\_TILE\_VERT Dispose les fenêtres en mosaïques verticalement.  
  
     Cette commande est implémentée dans `CMDIFrameWnd` comme **ID\_WINDOW\_CASCADE**, à moins qu'un message différent MDI Windows soit utilisé pour l'opération.  
  
     Vous devez choisir l'orientation par défaut de mosaïque pour votre application.  Vous pouvez le faire en modifiant l'ID de l'élément de menu « mosaïque » de fenêtre en **ID\_WINDOW\_TILE\_HORZ** ou en **ID\_WINDOW\_TILE\_VERT**.  
  
-   ID\_WINDOW\_SPLIT Interface du clavier à séparer.  
  
     `CView` gère cette commande pour l'implémentation de `CSplitterWnd`.  Si la vue fait partie d'une fenêtre séparée, cette commande la délèguera à la fonction `CSplitterWnd::DoKeyboardSplit` d'implémentation.  Cela placera le séparateur dans un mode qui permet aux utilisateurs de clavier de séparer ou non une fenêtre.  
  
     Cette commande est désactivée si la vue n'est pas dans une fenêtre séparée.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_APP\_ABOUT appelle la boîte de dialogue A Propos.  
  
     Aucune implémentation standard pour la zone A Propos d'une application .  L'application créée avec le AppWizard par défaut crée une classe de la boîte de dialogue personnalisée pour votre application et l'utilise comme zone A Propos.  AppWizard écrit aussi le gestionnaire de commandes triviales qui gère la commande et appelle le dialogue.  
  
     Vous implémenterez presque toujours cette commande.  
  
-   ID\_APP\_EXIT Quitter l'application  
  
     **CWinApp::OnAppExit** gère cet ordre en envoyant un message `WM_CLOSE` à la fenêtre principale de l'application.  L'arrêt standard de l'application \(invite pour les fichiers modifiés et ainsi de suite\) est géré par l'implémentation de `CFrameWnd`.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  Remplacer `CWinApp::SaveAllModified` ou la logique de fermeture `CFrameWnd` est recommandé.  
  
     Si vous choisissez d'implémenter cette commande, nous vous recommandons d'utiliser cet ID de commande  
  
-   ID\_HELP\_INDEX répertorie les rubriques d'aide du fichier .HLP.  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     `CWinApp::OnHelpIndex` gère cette commande en appelant trivialement `CWinApp::WinHelp`.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_HELP\_USING Affiche une aide sur l'utilisation de l'aide.  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     `CWinApp::OnHelpUsing` gère cette commande en appelant trivialement `CWinApp::WinHelp`.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_CONTEXT\_HELP Lance le mode d'aide SHIFT\-F1.  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     `CWinApp::OnContextHelp` gère cette commande en désactivant le curseur de mode d'aide, en entrant une boucle modale et en attendant que l'utilisateur sélectionne une fenêtre pour laquelle obtenir de l'aide.  Rendez\-vous sur [Note technique 28](../mfc/tn028-context-sensitive-help-support.md) pour plus d'informations sur l'implémentation d'aide de MFC.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_HELP fournit de l'aide sur le contexte actuel  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     `CWinApp::OnHelp` gère cette commande en obtenant le bon contexte d'aide pour le contexte actuel de l'application.  Cela gère l'aide F1\), et aide sur les boîtes messages et ainsi de suite.  Rendez\-vous sur [Note technique 28](../mfc/tn028-context-sensitive-help-support.md) pour plus d'informations sur l'implémentation d'aide de MFC.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_DEFAULT\_HELP Affiche l'aide par défaut du contexte  
  
    > [!NOTE]
    >  Vous devez connecter cela à la table des messages de votre classe dérivée de `CWinApp` pour activer cette fonctionnalité.  
  
     Cette commande est généralement mappée à `CWinApp::OnHelpIndex`.  
  
     Un gestionnaire de commandes différent peut être spécifié si une distinction entre l'aide défaut et l'index de l'aide est souhaitée.  
  
-   ID\_NEXT\_PANE passe au volet suivant  
  
     `CView` gère cette commande pour l'implémentation de `CSplitterWnd`.  Si la vue fait partie d'une fenêtre séparée, cette commande la délèguera à la fonction **CSplitterWnd::OnNextPaneCmd** d'implémentation.  Cela se déplacera la vue active vers le volet suivant dans le séparateur.  
  
     Cette commande est désactivée si la vue n'est pas dans un séparateur ou s'ilm n'y a aucun volet suivant auquel accéder.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_PREV\_PANE passe au volet précédent  
  
     `CView` gère cette commande pour l'implémentation de `CSplitterWnd`.  Si la vue fait partie d'une fenêtre séparée, cette commande la délèguera à la fonction **CSplitterWnd::OnNextPaneCmd** d'implémentation.  Cela se déplacera la vue active vers le volet précédent dans le séparateur.  
  
     Cette commande est désactivée si la vue n'est pas dans un séparateur ou s'il n'y a aucun volet suivant auquel accéder.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_OLE\_INSERT\_NEW insère un objet OLE  
  
     Actuellement il n'existe aucune implémentation standard pour cette commande.  Vous devez implémenter cette valeur pour votre classe dérivée de `CView` pour insérer un nouvel élément\/objet OLE à la sélection actuelle.  
  
     Toutes les applications OLE clientes doivent implémenter cette commande.  AppWizard, avec l'option OLE, crée une implémentation squelette de **OnInsertObject** dans la classe d'affichage que vous devez terminer.  
  
     Consultez l'exemple [OCLIENT](../top/visual-cpp-samples.md) pour une implémentation complète de cette commande.  
  
-   ID\_OLE\_EDIT\_LINKS Modifie les liens OLE  
  
     `COleDocument` gère cette commande à l'aide de l'implémentation de dialogue standard de liens OLE fournie par MFC.  L'implémentation de ce dialogue est accessible via la classe `COleLinksDialog`.  Si le document actif ne contient pas de lien, la commande est désactivée.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   ID\_OLE\_VERB\_FIRST… LAST Une plage d'ID de verbes OLE  
  
     `COleDocument` utilise cette plage d'ID de commande pour les verbes pris en charge par l'élément\/objet OLE actuellement sélectionné.  Il doit s'agir d'une plage puisque 'un élément\/type d'objet OLE donné peut prendre en charge zéro ou plus verbes personnalisés  Dans le menu de votre application, vous devez avoir un élément de menu avec l'ID de **ID\_OLE\_VERB\_FIRST**.  Lorsque le programme est exécuté, le menu sera mis à jour avec la description appropriée de verbe de menu \(ou dans le menu contextuel avec plusieurs verbes\).  La gestion de menu OLE est gérée par `AfxOleSetEditMenu`, effectuée dans le gestionnaire de commande interface utilisateur de mise à jour pour cette commande.  
  
     Il n'y a aucun responsable de commandes explicite pour gérer et de l'ID de commande dans cette plage.  **COleDocument::OnCmdMsg** est substituée pour intercepter tous les ID de commande dans cette plage, pour les transformer en nombres de verbes, et pour lancer le serveur pour le verbe \(en utilisant `COleClientItem::DoVerb`\).  
  
     La personnalisation ou une autre utilisation de cette plage d'ID de commande n'est pas recommandée.  
  
-   ctive et désactive la barre d'outils  
  
     `CFrameWnd` gère cette commande et le gestionnaire d'interface utilisateur de commande de de mise à jourdans son activation de l'état visible de la barre d'outils.  La barre d'outils doit être une fenêtre enfant du cadre avec l'ID de fenêtre enfant de `AFX_IDW_TOOLBAR`.  Le gestionnaire de commandes active la visibilité de la fenêtre de la barre d'outils.  `CFrameWnd::RecalcLayout` est utilisé pour redessiner la fenêtre cadre avec la barre d'outils dans son nouvel état.  Le gestionnaire de commande à l'interface utilisateur active l'élément de menu quand la barre d'outils est visible.  
  
     La personnalisation du gestionnaire de commandes n'est pas recommandée.  Si vous souhaitez ajouter des barres d'outils supplémentaires, vous souhaiterez cloner et modificier le gestionnaire de commandes et le gestionnaire de mise à jour de commande d'interface utilisateur pour cette commande.  
  
-   ID\_VIEW\_STATUS\_BAR active et désactive la barre d'état.  
  
     Cette commande est implémentée dans `CFrameWnd` comme **ID\_VIEW\_TOOLBAR**, sauf qu'un ID différent de fenêtre enfant \(**AFX\_IDW\_STATUS\_BAR**\) est utilisé.  
  
## Gestionnaires de commandes de mise à jour exclusivement  
 Plusieurs identificateurs standard de commande sont utilisés comme indicateurs dans les barres d'état.  Ils utilisent le même mécanisme de gestion de commande de mise à jour d'interface utilisateur pour afficher l'état actuel pendant la durée d'inactivité de l'application.  Puisqu'ils ne peuvent pas être sélectionnés par l'utilisateur \(autrement dit, vous ne pouvez pas transmettre un volet barre d'état\), il n'est pas pertinent de disposer d'un gestionnaire `ON_COMMAND` pour ces ID de commande.  
  
-   **ID\_INDICATOR\_CAPS** : Indicateur de fonction de verrouillage caps\-lock  
  
-   **ID\_INDICATOR\_CAPS** : Indicateur de fonction de verrouillage numérique  
  
-   **ID\_INDICATOR\_CAPS** : Indicateur de fonction de verrouillage DÉFIL  
  
-   **ID\_INDICATOR\_KANA** : Indicateur de verrou de KANA \(s'applique uniquement aux systèmes japonais\).  
  
 Ces trois éléments sont implémentés dans **CFrameWnd::OnUpdateKeyIndicator**, un programme d'assistance à l'implémentation qui utilise l'ID de commande pour mapper la clé virtuelle appropriée.  Une implémentation commune active ou désactive \(pour les volets d'état désactivé \= aucun texte\) l'objet `CCmdUI` selon que la clé virtuelle appropriée est actuellement verrouillée ou non.  
  
 La personnalisation du gestionnaire de commandes n'est pas recommandée.  
  
-   **ID\_INDICATOR\_EXT : EXT** indicateur de séléction terminé.  
  
-   **ID\_INDICATOR\_OVR : OV**e**R**Indicateur de frappe.  
  
-   **ID\_INDICATOR\_REC : REC**indicateur d'ording.  
  
 Actuellement il n'existe aucune implémentation standard pour ces indicateurs.  
  
 Si vous choisissez d'implémenter ces indicateurs, nous vous recommandons d'utiliser ces ID d'indicateur et gérer le classement des indicateurs dans la barre d'état \(autrement dit, dans l'ordre : EXT., CAP, NUM, DÉFIL, OVR, REC\).  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
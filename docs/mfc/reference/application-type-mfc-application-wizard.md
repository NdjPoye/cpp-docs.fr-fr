---
title: "Type d&#39;application, Assistant Application MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.apptype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèques statiques, MFC"
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Type d&#39;application, Assistant Application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez la page [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md) pour concevoir et ajouter des fonctionnalités de base à une nouvelle application MFC.  
  
 **Type d'application**  
 Spécifie le type de prise en charge de document que vous voulez créer dans l'application.  Le type d'application sélectionné détermine les options d'interface utilisateur disponibles dans votre application.  Pour plus d'informations, consultez [Fonctionnalités de l'interface utilisateur, Assistant Application MFC](../../mfc/reference/user-interface-features-mfc-application-wizard.md).  
  
 Pour plus d'informations sur les types de documents, consultez :  
  
-   [SDI et MDI](../../mfc/sdi-and-mdi.md)  
  
-   [Fenêtres frame](../../mfc/frame-windows.md)  
  
-   [Classes de fenêtre frame](../../mfc/frame-window-classes.md)  
  
-   [Documents, vues et le Framework](../../mfc/documents-views-and-the-framework.md)  
  
-   [Boîtes de dialogue](../../mfc/dialog-boxes.md)  
  
|Option|Description|  
|------------|-----------------|  
|**Monodocument \(SDI\)**|Crée une architecture dotée d'une interface monodocument \(SDI\) pour votre application, avec une classe d'affichage basée sur [CView Class](../../mfc/reference/cview-class.md).  Vous pouvez modifier la classe de base de la vue dans la page [Classes générées, Assistant Application MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md) de l'Assistant.  Par exemple, pour créer une application basée sur les formulaires, utilisez [CFormView Class](../../mfc/reference/cformview-class.md) pour la classe d'affichage.<br /><br /> Dans ce type d'application, la fenêtre frame de document ne peut contenir qu'un seul document.|  
|**Multidocument \(MDI\)**|Crée une architecture dotée d'une interface multidocument \(MDI\) pour votre application, avec une classe d'affichage basée sur `CView`.  Vous pouvez modifier la classe de base de la vue dans la page **Classes générées** de l'Assistant.  Par exemple, pour créer une application basée sur les formulaires, utilisez `CFormView` pour la classe d'affichage.<br /><br /> Dans ce type d'application, la fenêtre frame de document peut contenir plusieurs fenêtres enfants.|  
|**Documents avec onglet**|Place chaque document sur un onglet séparé.|  
|**Basée sur des boîtes de dialogue**|Crée une architecture basée sur des boîtes de dialogue pour votre application, avec une classe de boîte de dialogue basée sur `CDialog`. \(Pour créer une boîte de dialogue HTML, activez la case à cocher **Utiliser la boîte de dialogue HTML**.\)|  
|**Boîte de dialogue HTML**|Uniquement destiné aux applications basées sur des boîtes de dialogue.  Dérive la classe de boîte de dialogue [CDHtmlDialog Class](../../mfc/reference/cdhtmldialog-class.md) à la place de [CDialog Class](../../mfc/reference/cdialog-class.md).  Si vous activez cette case à cocher, la classe `CDHtmlDialog` est répertoriée dans la zone **Classe de base** de la page [Classes générées, Assistant Application MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md) de l'Assistant.<br /><br /> Une boîte de dialogue dérivée de `CDHtmlDialog` affiche des boîtes de dialogue HTML, échange des données avec les contrôles HTML et gère les événements HTML.|  
|**Plusieurs documents de niveau supérieur**|Crée une architecture prenant en charge plusieurs documents de niveau supérieur pour votre application, avec une classe d'affichage basée sur `CView`.<br /><br /> Dans ce type d'application, lorsqu'un utilisateur clique sur **Nouveau** \(ou sur **Nouveau Frame**\) dans le menu **Fichier**, l'application crée une fenêtre dont le bureau est implicitement le parent.  Le frame du nouveau document apparaît dans la barre des tâches et ne se limite pas à la zone cliente de la fenêtre de l'application.|  
  
 **Prise en charge de l'architecture Document\/Vue**  
 Spécifie si l'architecture Document\/Vue doit être incluse dans votre application à l'aide des classes de base [CDocument Class](../../mfc/reference/cdocument-class.md) et [CView Class](../../mfc/reference/cview-class.md) \(par défaut\).  Désactivez cette case à cocher si vous procédez au portage d'une application non\-MFC ou si vous voulez réduire la taille de l'exécutable compilé.  Par défaut, une application sans architecture Document\/Vue est dérivée de [CWinApp Class](../../mfc/reference/cwinapp-class.md) et n'inclut pas de prise en charge MFC pour l'ouverture d'un document à partir d'un fichier sur disque.  
  
 **Langue des ressources**  
 Définit le langage de vos ressources.  La liste affiche les langues disponibles sur votre système, telles qu'installées par Visual Studio.  Si vous voulez sélectionner une langue autre que celle de votre système, le dossier de modèles approprié à cette langue doit déjà être installé.  Pour plus d'informations sur l'installation de ressources de langue différentes des valeurs par défaut figurant dans la liste **Langue des ressources**, consultez [Prise en charge d'autres langues par l'Assistant](../../ide/wizard-support-for-other-languages.md).  
  
 La langue sélectionnée est répercutée dans l'option **Chaînes traduites** de la page [Chaînes modèles de document, Assistant Application MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md) de l'Assistant.  
  
 **Utiliser des bibliothèques Unicode**  
 Spécifie si la version utilisée pour les bibliothèques MFC est Unicode ou non.  
  
 **Style du projet**  
 Indique si votre application possède une architecture et un affichage MFC, Explorateur Windows, Visual Studio ou Office standard.  Pour plus d'informations, consultez [Création d'une application MFC de style Explorateur de fichiers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).  
  
|Option|Description|  
|------------|-----------------|  
|**Standard MFC**|Implémente une architecture d'application MFC standard.|  
|**Explorateur de fichiers**|Implémente une application de style Explorateur Windows en utilisant une fenêtre fractionnée où le volet de gauche est une classe [CTreeView Class](../../mfc/reference/ctreeview-class.md) et le volet de droite est une classe [CListView Class](../../mfc/reference/clistview-class.md).|  
|**Visual Studio**|Implémente une application de style Visual Studio qui contient quatre volets ancrables \(**Affichage des fichiers**, **Affichage de classes**, **Propriétés** et **Sortie**\) dérivés de [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) et une fenêtre frame principale dérivée de [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md) \(valeur par défaut\).|  
|**Office**|Implémente une application de style Office qui contient un ruban dérivé de [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md), une barre Outlook dérivée de [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md), une barre de légende dérivée de [CMFCCaptionBar, Classe](../../mfc/reference/cmfccaptionbar-class.md), et un frame principal dérivé de [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md).|  
  
 **Style Visuel et couleurs**  
 Détermine le type visuel de l'application.  Les options disponibles sont les suivantes :  
  
-   **Natif\/valeur par défaut de Windows**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007 \(thème Bleu\)**  
  
-   **Office 2007 \(thème Noir\)**  
  
-   **Office 2007 \(thème Argent\)**  
  
-   **Office 2007 \(thème Cyan\)**  
  
 **Activer la commutation de style visuel**  
 Spécifie si l'utilisateur peut modifier le style visuel de l'application pendant l'exécution, habituellement en sélectionnant le style visuel approprié dans un menu ou un ruban.  
  
 **Utilisation des MFC**  
 Spécifie comment établir un lien vers la bibliothèque MFC.  Par défaut, la bibliothèque MFC est liée sous la forme d'une DLL partagée.  
  
|Option|Description|  
|------------|-----------------|  
|**Utiliser les MFC dans une DLL partagée**|Établit un lien entre la bibliothèque MFC et une application sous la forme d'une DLL partagée.  L'application effectue des appels à la bibliothèque MFC au moment de l'exécution.  Cette option permet de réduire les besoins en disque et en mémoire des applications qui se composent de plusieurs fichiers exécutables utilisant la bibliothèque MFC.  Les applications Win32 et MFC peuvent appeler des fonctions dans votre DLL \(valeur par défaut\).|  
|**Utiliser les MFC dans une bibliothèque statique**|Établit un lien entre une application et la bibliothèque MFC statique au moment de la génération.|  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)   
 [Types de fichiers créés pour les projets Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md)
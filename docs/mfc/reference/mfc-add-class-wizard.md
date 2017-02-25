---
title: "Assistant Ajouter une classe MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.simple.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Ajouter une classe MFC"
  - "Assistants (MFC)"
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Assistant Ajouter une classe MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant Code pour ajouter une classe à un projet MFC existant ou à un projet ATL prenant en charge MFC.  Il est également possible d'ajouter des classes MFC à des projets Win32 prenant en charge MFC.  Les fonctionnalités que vous avez spécifiées lors de la création de votre projet déterminent les options disponibles dans cette boîte de dialogue.  
  
## Noms  
 Dans cette page, spécifiez le nom de la classe, la classe de base et le nom des fichiers de la nouvelle classe.  
  
 **Nom de classe**  
 Spécifie le nom de la nouvelle classe et fournit la base par défaut pour les noms des ID et des fichiers de cette page.  Les classes C\+\+ commencent généralement par « C ». Par exemple, « CMyClass » devient « MyClass.h », etc.  
  
 **Classe de base**  
 Définit le nom de la classe de base de votre nouvelle classe.  Par défaut, la classe de base est [CWnd](../../mfc/reference/cwnd-class.md).  La classe de base que vous sélectionnez détermine si les autres zones de cette page sont actives.  
  
 Le type de classe que vous définissez comme la classe de base détermine si la classe a un ID de boîte de dialogue ou un ID de ressource.  Les types généraux de classes sont les suivants :  
  
-   Classes telles que [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md)ou [CDocument](../../mfc/reference/cdocument-class.md), qui ne requièrent pas un ID de boîte de dialogue ou un ID de ressource.  Ces classes n'utilisent pas un ID de boîte de dialogue ou de ressource.  Si vous sélectionnez l'une de ces classes pour votre classe de base, la zone **ID de boîte de dialogue** et la zone **ID de ressource DHTML** sont estompées.  
  
-   Classes telles que [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md) ou [CPropertyPage](../../mfc/reference/cpropertypage-class.md), qui nécessitent un ID de boîte de dialogue.  
  
-   Classe [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), qui nécessite un ID de boîte de dialogue, un ID de ressource DHTML et un nom de fichier HTML.  
  
 Pour les classes qui requièrent un ID de boîte de dialogue, vous pouvez trouver plus efficace d'utiliser l'[éditeur de ressources](../../mfc/resource-editors.md) pour créer la ressource de boîte de dialogue, assigner son ID dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), puis créer une classe associée à cet ID de ressource.  Consultez [Création d'une nouvelle boîte de dialogue](../../mfc/creating-a-new-dialog-box.md) pour plus d'informations sur la création d'une boîte de dialogue Windows standard.  
  
> [!NOTE]
>  Si vous créez d'abord une ressource boîte de dialogue, puis que vous dérivez sa nouvelle classe de `CDHtmlDialog`, supprimez les boutons **OK** et **Annuler** standard de Windows qui s'affichent dans la boîte de dialogue par défaut.  La boîte de dialogue Windows standard héberge le formulaire DHTML, qui contient ses propres boutons **OK** et **Annuler**.  
  
 Même si votre boîte de dialogue peut contenir à la fois des contrôles Windows et des contrôles DHTML, cela n'est pas recommandé.  
  
 **ID de la boîte de dialogue**  
 Spécifie l'ID de la boîte de dialogue, si vous avez sélectionné `CDialog`, `CFormView`, `CPropertyPage` ou `CDHtmlDialog` comme **Classe de base**.  
  
 **fichier .h**  
 Définit le nom du fichier d'en\-tête de la nouvelle classe d'objets.  Par défaut, ce nom est fondé sur celui que vous avez entré dans la zone **Nom de la classe**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous sélectionnez un fichier existant, l'Assistant ne l'enregistrera pas à l'emplacement choisi tant que vous n'aurez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d'implémentation pour la nouvelle classe d'objet.  Par défaut, ce nom est fondé sur celui que vous avez entré dans la zone **Nom de la classe**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix.  Le fichier n'est pas enregistré à l'emplacement souhaité tant que vous n'avez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous invite à indiquer si l'implémentation de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **Active accessibility**  
 Active la prise en charge d'Active Accessibility par MFC en appelant [EnableActiveAccessibility](../Topic/CWnd::EnableActiveAccessibility.md) dans le constructeur.  Cette option est disponible pour les classes dérivées de [CWnd](../../mfc/reference/cwnd-class.md).  
  
 **ID de ressource DHTML**  
 S'applique aux classes dérivées de `CDHtmlDialog` uniquement.  Spécifie l'ID de ressource de la boîte de dialogue DHTML.  L'ID de ressource s'affiche dans la section HTML du fichier .rc du projet, accompagné du nom du fichier de la boîte de dialogue HTML.  La ressource DHTML, identifiée par cet ID, est hébergée par la boîte de dialogue, identifiée par l'**ID de boîte de dialogue**.  
  
 **Fichier .HTM**  
 S'applique aux classes dérivées de `CDHtmlDialog` uniquement.  Définit le nom du fichier HTML de la boîte de dialogue DHTML.  Par défaut, ce nom de fichier est fondé sur le nom de la classe.  Le nom du fichier s'affiche dans la section HTML du fichier .rc du projet, accompagné de l'ID de ressource de la boîte de dialogue DHTML.  
  
 **Automation**  
 Définit le niveau de prise en charge d'[Automation](../../mfc/automation.md) de la classe.  L'Automation au niveau de la classe est disponible pour toutes les classes prenant en charge Automation.  Est également disponible pour les projets créés avec la prise en charge d'Automation.  Autrement dit, soit un projet MFC qui [prend en charge ATL](../../atl/reference/mfc-support-in-atl-projects.md), soit un projet MFC pour lequel vous avez activé la case à cocher **Automation** dans la page [Fonctionnalités avancées](../../mfc/reference/advanced-features-mfc-application-wizard.md) de l'Assistant Application MFC.  
  
|Option|Description|  
|------------|-----------------|  
|**None**|Indique que la classe ne possède aucune prise en charge d'Automation.|  
|**Automation**|Indique que la classe prend en charge Automation.  Si vous sélectionnez cette option, la classe que vous venez de créer est disponible en tant qu'objet programmable par les applications client Automation, telles que Microsoft Visual Basic et Microsoft Excel.  Cette option n'est pas disponible pour les classes de base énumérées après ce tableau.|  
|**Création possible par ID de type**|Indique que la classe et le projet prennent en charge d'autres applications créant des objets de cette classe à l'aide d'Automation.  Avec cette option, les clients Automation peuvent créer directement un objet Automation.  L'ID du type spécifié dans la zone de texte est utilisé par l'application cliente pour spécifier l'objet à créer. Il est valide à l'échelle du système et doit être unique.  Cette option n'est pas disponible pour les classes de base énumérées après ce tableau.|  
  
 La prise en charge d'Automation n'est pas disponible pour les classes de base suivantes :  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **ID de type**  
 Définit l'ID du type de la classe.  La zone **ID de type** concatène le nom du projet et celui de la nouvelle classe de la manière suivante : *MFCProj.MFCClass*.  Cet ID ne peut être modifié que si vous avez sélectionné **Création possible par ID de type** pour l'option **Automation**.  
  
 **Générer des ressources DocTemplate**  
 Indique que les documents créés par l'application possèdent des ressources de modèles de documents.  Pour activer cette case à cocher, le projet doit prendre en charge l'architecture Document\/Vue MFC et la classe de base de cette classe doit être [CFormView](../../mfc/reference/cformview-class.md).  
  
 Pour plus d'informations, consultez [Modèles de document et processus de création document\/vue](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Voir aussi  
 [MFC, classe](../../mfc/reference/adding-an-mfc-class.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)
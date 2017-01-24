---
title: "Comment&#160;: ajouter la prise en charge du Gestionnaire de red&#233;marrage | Microsoft Docs"
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
  - "Gestionnaire de redémarrage"
  - "C++, prise en charge des arrêts brutaux des applications"
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: ajouter la prise en charge du Gestionnaire de red&#233;marrage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le Gestionnaire de redémarrage est une fonctionnalité ajoutée à [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]. Le Gestionnaire de redémarrage prend en charge votre application, si elle se ferme ou redémarre de façon inattendue. Le comportement du Gestionnaire de redémarrage dépend du type de votre application. Si votre application est un éditeur de documents, le Gestionnaire de redémarrage permet à votre application d’enregistrer automatiquement l’état et le contenu des documents ouverts. Par ailleurs, il redémarre votre application après une fermeture inattendue. Si votre application n’est pas un éditeur de documents, le Gestionnaire de redémarrage la redémarre. Toutefois, il ne peut pas enregistrer l’état de l’application par défaut.  
  
 Après avoir redémarré, l’application affiche une boîte de dialogue de tâches si l’application est au format Unicode. S’il s’agit d’une application ANSI, celle\-ci affiche une boîte de message Windows. À ce stade, l’utilisateur choisit de restaurer ou non les documents enregistrés automatiquement. Si l’utilisateur ne restaure pas les documents enregistrés automatiquement, le Gestionnaire de redémarrage ignore les fichiers temporaires.  
  
> [!NOTE]
>  Vous pouvez substituer le comportement par défaut du Gestionnaire de redémarrage pour l’enregistrement des données et le redémarrage de l’application.  
  
 Par défaut, les applications MFC créées à l’aide de l’Assistant Projet dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] prennent en charge le Gestionnaire de redémarrage quand elles sont exécutées sur un ordinateur [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]. Si vous ne souhaitez pas que votre application prenne en charge le Gestionnaire de redémarrage, vous pouvez le désactiver dans l’Assistant Nouveau projet.  
  
### Pour ajouter la prise en charge du Gestionnaire de redémarrage à une application existante  
  
1.  Ouvrez une application MFC existante dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
2.  Ouvrez le fichier source de votre application principale. Par défaut, il s’agit du fichier .cpp qui porte le même nom que votre application. Par exemple, le fichier source de l’application principale pour MyProject est MyProject.cpp.  
  
3.  Recherchez le constructeur de votre application principale. Par exemple, si votre projet est MyProject, le constructeur est `CMyProjectApp::CMyProjectApp()`.  
  
4.  Ajoutez la ligne de code suivante à votre constructeur.  
  
    ```  
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;  
    ```  
  
5.  Assurez\-vous que la méthode `InitInstance` de votre application appelle sa méthode `InitInstance` parente : [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) ou `CWinAppEx::InitInstance`. La méthode `InitInstance` est chargée de vérifier le paramètre `m_dwRestartManagerSupportFlags`.  
  
6.  Compilez et exécutez votre application.  
  
## Voir aussi  
 [CDataRecoveryHandler Class](../mfc/reference/cdatarecoveryhandler-class.md)   
 [CWinApp::m\_dwRestartManagerSupportFlags](../Topic/CWinApp::m_dwRestartManagerSupportFlags.md)   
 [CWinApp Class](../mfc/reference/cwinapp-class.md)   
 [CWinApp::m\_nAutosaveInterval](../Topic/CWinApp::m_nAutosaveInterval.md)   
 [CDocument::OnDocumentEvent](../Topic/CDocument::OnDocumentEvent.md)
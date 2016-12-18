---
title: "CUserToolsManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUserToolsManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserToolsManager class"
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserToolsManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Met à jour la collection d'objets de [CUserTool Class](../../mfc/reference/cusertool-class.md) dans une application.  Un outil d'utilisateur est un élément de menu qui exécute une application externe.  L'objet d' `CUserToolsManager` permet à l'utilisateur ou au développeur d'ajouter de nouveaux outils utilisateur à l'application.  Il prend en charge l'exécution des commandes associées aux outils utilisateur, et il enregistre également des informations sur les outils utilisateur dans le Registre Windows.  
  
## Syntaxe  
  
```  
class CUserToolsManager : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CUserToolsManager::CUserToolsManager](../Topic/CUserToolsManager::CUserToolsManager.md)|Construit un `CUserToolsManager`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md)|Crée un nouvel outil d'utilisateur.|  
|[CUserToolsManager::FindTool](../Topic/CUserToolsManager::FindTool.md)|Retourne le pointeur vers l'objet d' `CMFCUserTool` associé à un ID de commande spécifiée|  
|[CUserToolsManager::GetArgumentsMenuID](../Topic/CUserToolsManager::GetArgumentsMenuID.md)|Retourne l'ID de ressource associé au menu **Arguments** sous l'onglet **Outils** de la boîte de dialogue **Personnaliser** .|  
|[CUserToolsManager::GetDefExt](../Topic/CUserToolsManager::GetDefExt.md)|Retourne l'extension par défaut que la boîte de dialogue **Ouvrir** \([CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)\) utilise dans le domaine **Commande** sous l'onglet **Outils** de la boîte de dialogue **Personnaliser** .|  
|[CUserToolsManager::GetFilter](../Topic/CUserToolsManager::GetFilter.md)|Retourne le filtre de fichiers que la boîte de dialogue **Ouvrir** \([CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\) utilise dans le domaine **Commande** sous l'onglet **Outils** de la boîte de dialogue **Personnaliser** .|  
|[CUserToolsManager::GetInitialDirMenuID](../Topic/CUserToolsManager::GetInitialDirMenuID.md)|Retourne l'ID de ressource associé au menu **Répertoire initial** sous l'onglet **Outils** de la boîte de dialogue **Personnaliser** .|  
|[CUserToolsManager::GetMaxTools](../Topic/CUserToolsManager::GetMaxTools.md)|Retourne le nombre maximal d'outils utilisateur qui peuvent être alloués dans l'application.|  
|[CUserToolsManager::GetToolsEntryCmd](../Topic/CUserToolsManager::GetToolsEntryCmd.md)|Retourne l'ID de commande de l'espace réservé d'élément de menu pour les outils utilisateur.|  
|[CUserToolsManager::GetUserTools](../Topic/CUserToolsManager::GetUserTools.md)|Retourne une référence à la liste d'outils utilisateur.|  
|[CUserToolsManager::InvokeTool](../Topic/CUserToolsManager::InvokeTool.md)|Exécute une application associée à l'outil d'utilisateur qui a un ID de commande spécifiée|  
|[CUserToolsManager::IsUserToolCmd](../Topic/CUserToolsManager::IsUserToolCmd.md)|Détermine si un ID de commande est associé à un outil d'utilisateur.|  
|[CUserToolsManager::LoadState](../Topic/CUserToolsManager::LoadState.md)|Charge des informations sur les outils utilisateur du Registre Windows.|  
|[CUserToolsManager::MoveToolDown](../Topic/CUserToolsManager::MoveToolDown.md)|Déplace l'outil spécifié d'utilisateur vers le bas dans la liste d'outils utilisateur.|  
|[CUserToolsManager::MoveToolUp](../Topic/CUserToolsManager::MoveToolUp.md)|Déplace l'outil spécifié d'utilisateur dans la liste d'outils utilisateur.|  
|[CUserToolsManager::RemoveTool](../Topic/CUserToolsManager::RemoveTool.md)|Supprime l'outil spécifié d'utilisateur de l'application.|  
|[CUserToolsManager::SaveState](../Topic/CUserToolsManager::SaveState.md)|Stocke des informations sur les outils utilisateur dans le Registre Windows.|  
|[CUserToolsManager::SetDefExt](../Topic/CUserToolsManager::SetDefExt.md)|Spécifie l'extension par défaut que la boîte de dialogue **Ouvrir** \([CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\) utilise dans le domaine **Commande** sous l'onglet **Outils** de la boîte de dialogue **Personnaliser** .|  
|[CUserToolsManager::SetFilter](../Topic/CUserToolsManager::SetFilter.md)|Spécifie le filtre de fichiers que la boîte de dialogue **Ouvrir** \([CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\) utilise dans le domaine **Commande** sous l'onglet **Outils** de la boîte de dialogue **Personnaliser** .|  
  
## Notes  
 Pour incorporer des outils utilisateur à votre application, vous devez :  
  
 1.  Réservez un élément de menu et un ID de commande associé à une entrée de menu d'outil d'utilisateur.  
  
 2.  Réservez un ID de commande séquentiel pour chaque outil d'utilisateur qu'un utilisateur peut définir dans votre application.  
  
 3.  Appelez la méthode de [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md) et fournissez les paramètres suivants : ID de commande de menu, le premier ID de commande d'outil d'utilisateur, et dernière ID de commande d'outil d'utilisateur  
  
 Il doit y avoir qu'un objet global d' `CUserToolsManager` par application.  
  
 Pour obtenir un exemple des outils utilisateur, consultez l'exemple de projet VisualStudioDemo.  
  
## Exemple  
 L'exemple suivant montre comment récupérer une référence à un objet d' `CUserToolsManager` et comment créer de nouveaux outils utilisateur.  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/CPP/cusertoolsmanager-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxusertoolsmanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CUserTool Class](../../mfc/reference/cusertool-class.md)
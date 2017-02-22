---
title: "CUserTool Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUserTool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserTool class"
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CUserTool Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un outil d'utilisateur est un élément de menu qui exécute une application externe.  L'onglet **Outils** de la boîte de dialogue **Personnaliser** \([CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)\) permet à l'utilisateur d'ajouter des outils utilisateur, et de spécifier le nom, la commande, les arguments, et le dossier d'origine pour chaque outil d'utilisateur.  
  
## Syntaxe  
  
```  
class CUserTool : public CObject  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CUserTool::CopyIconToClipboard](../Topic/CUserTool::CopyIconToClipboard.md)||  
|[CUserTool::DrawToolIcon](../Topic/CUserTool::DrawToolIcon.md)|Dessine l'icône d'outil d'utilisateur dans un rectangle spécifié.|  
|[CUserTool::GetCommand](../Topic/CUserTool::GetCommand.md)|Retourne une chaîne qui contient le texte de la commande associée à l'outil d'utilisateur.|  
|[CUserTool::GetCommandId](../Topic/CUserTool::GetCommandId.md)|Retourne l'ID de commande de l'élément de menu de l'outil d'utilisateur.|  
|[CUserTool::Invoke](../Topic/CUserTool::Invoke.md)|Exécute la commande associée à l'outil d'utilisateur.|  
|[CUserTool::Serialize](../Topic/CUserTool::Serialize.md)|Lit ou écrit cet objet ou y retourne une archive.  \(Substitutions [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CUserTool::SetCommand](../Topic/CUserTool::SetCommand.md)|Définit la commande associée à l'outil d'utilisateur.|  
|[CUserTool::SetToolIcon](../Topic/CUserTool::SetToolIcon.md)|Charge l'icône de l'outil d'utilisateur de l'application associée à l'outil.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CUserTool::LoadDefaultIcon](../Topic/CUserTool::LoadDefaultIcon.md)|Charge l'icône par défaut par un outil d'utilisateur.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CUserTool::m\_strArguments](../Topic/CUserTool::m_strArguments.md)|Les arguments de ligne de commande pour l'outil d'utilisateur.|  
|[CUserTool::m\_strInitialDirectory](../Topic/CUserTool::m_strInitialDirectory.md)|Le répertoire initial de l'outil d'utilisateur.|  
|[CUserTool::m\_strLabel](../Topic/CUserTool::m_strLabel.md)|Le nom d'outil qui s'affiche dans l'élément de menu pour l'outil.|  
  
## Notes  
 Pour plus d'informations sur l'activation des outils utilisateur dans votre application, consultez [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md).  
  
## Exemple  
 L'exemple suivant montre comment créer un outil d'un objet d' `CUserToolsManager` , définir la variable membre d' `m_strLabel` , et définir l'application que l'outil d'utilisateur exécute.  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/CPP/cusertool-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## Configuration requise  
 **en\-tête :** afxusertool.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md)
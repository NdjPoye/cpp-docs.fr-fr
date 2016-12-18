---
title: "CCommandLineInfo Class | Microsoft Docs"
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
  - "CCommandLineInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application flags [C++]"
  - "argv argument"
  - "CCommandLineInfo class"
  - "ligne de commande, analyser"
  - "analyser, arguments de ligne de commande"
  - "code de démarrage, parsing command-line arguments"
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommandLineInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet en analysant la ligne de commande au démarrage de l'application.  
  
## Syntaxe  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](../Topic/CCommandLineInfo::CCommandLineInfo.md)|Construit un objet par défaut d' `CCommandLineInfo` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCommandLineInfo::ParseParam](../Topic/CCommandLineInfo::ParseParam.md)|Remplacez ce rappel pour analyser des paramètres.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md)|Indique l'option d' **\/Automation** de ligne de commande a été trouvé.|  
|[CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md)|Indique l'option d' **\/Embedding** de ligne de commande a été trouvé.|  
|[CCommandLineInfo::m\_bShowSplash](../Topic/CCommandLineInfo::m_bShowSplash.md)|Indique si un écran de démarrage est affiché.|  
|[CCommandLineInfo::m\_nShellCommand](../Topic/CCommandLineInfo::m_nShellCommand.md)|Indique l'ordre d'environnement soit traité.|  
|[CCommandLineInfo::m\_strDriverName](../Topic/CCommandLineInfo::m_strDriverName.md)|Indique le nom du gestionnaire si la commande d'environnement est copie la valeur ; sinon vide.|  
|[CCommandLineInfo::m\_strFileName](../Topic/CCommandLineInfo::m_strFileName.md)|Indique le nom de fichier à ouvrir ou être imprimé ; vide si la commande d'environnement est nouveau ou DDE.|  
|[CCommandLineInfo::m\_strPortName](../Topic/CCommandLineInfo::m_strPortName.md)|Indique le nom de port si la commande d'environnement est copie la valeur ; sinon vide.|  
|[CCommandLineInfo::m\_strPrinterName](../Topic/CCommandLineInfo::m_strPrinterName.md)|Indique le nom d'imprimante si la commande d'environnement est copie la valeur ; sinon vide.|  
|[CCommandLineInfo::m\_strRestartIdentifier](../Topic/CCommandLineInfo::m_strRestartIdentifier.md)|Indique le seul identificateur de redémarrage pour le gestionnaire de redémarrage si le gestionnaire de redémarrage relançait l'application.|  
  
## Notes  
 Une application MFC crée généralement une instance locale de cette classe dans la fonction d' [InitInstance](../Topic/CWinApp::InitInstance.md) de son objet de l'application.  Cet objet est ensuite passé à [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md), qui appelle à plusieurs reprises [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) pour remplir l'objet d' `CCommandLineInfo` .  L'objet d' `CCommandLineInfo` est ensuite passé à [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md) pour gérer les arguments de ligne de commande et des balises.  
  
 Vous pouvez utiliser cet objet pour encapsuler les options de ligne de commande et les paramètres suivants :  
  
|Argument de ligne de commande|Commande exécutée|  
|-----------------------------------|-----------------------|  
|*application*|Fichier.|  
|Nom du fichier d'*application*|Fichier ouvert.|  
|Nom du fichier de**\/p** d'*application*|Fichier d'impression à l'imprimante par défaut.|  
|Port de pilote d'imprimante de nom de fichier de**\/pt***d'application*|Fichier d'impression à l'imprimante spécifiée.|  
|*application* **\/dde**|Démarrez et attendez que la commande de DDE.|  
|*application* **\/Automation**|Démarrez en tant que OLE serveur Automation.|  
|*application* **\/Embedding**|Démarrez jusqu'à la modification d'un élément OLE incorporé.|  
|*application* **\/Register**<br /><br /> *application* **\/Regserver**|Indique à l'application d'exécuter toutes les tâches d'inscription.|  
|*application* **\/Unregister**<br /><br /> *application* **\/Unregserver**|Indique à l'application d'exécuter toutes les tâches d'ONU\- inscription.|  
  
 Dérivez une nouvelle classe d' `CCommandLineInfo` pour gérer d'autres balises et valeurs de paramètre.  Substitution [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) pour gérer les nouvelles balises.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)   
 [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)
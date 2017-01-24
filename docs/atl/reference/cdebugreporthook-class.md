---
title: "CDebugReportHook Class | Microsoft Docs"
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
  - "ATL.CDebugReportHook"
  - "CDebugReportHook"
  - "ATL::CDebugReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDebugReportHook class"
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDebugReportHook Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cette classe pour envoyer des rapports de débogage vers un canal nommé.  
  
## Syntaxe  
  
```  
  
class CDebugReportHook  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDebugReportHook::CDebugReportHook](../Topic/CDebugReportHook::CDebugReportHook.md)|Appels [SetPipeName](../Topic/CDebugReportHook::SetPipeName.md), [SetTimeout](../Topic/CDebugReportHook::SetTimeout.md), et [SetHook](../Topic/CDebugReportHook::SetHook.md).|  
|[CDebugReportHook::~CDebugReportHook](../Topic/CDebugReportHook::~CDebugReportHook.md)|Appels [CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md).|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](../Topic/CDebugReportHook::CDebugReportHookProc.md)|\(Statique\) la fonction personnalisée qui est accrochée dans le runtime C debug le processus d'enregistrement.|  
|[CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md)|Appelez cette méthode pour arrêter d'envoyer des rapports de débogage dans le canal nommé et restaurer le raccordement précédent d'état.|  
|[CDebugReportHook::SetHook](../Topic/CDebugReportHook::SetHook.md)|Appelez cette méthode pour commencer à envoyer des rapports de débogage dans le canal nommé.|  
|[CDebugReportHook::SetPipeName](../Topic/CDebugReportHook::SetPipeName.md)|Appelez cette méthode pour définir l'ordinateur et le nom du canal dans lequel les rapports de débogage seront envoyés.|  
|[CDebugReportHook::SetTimeout](../Topic/CDebugReportHook::SetTimeout.md)|Appelez cette méthode pour définir l'heure en millisecondes que cette classe attend le canal nommé soit disponible.|  
  
## Notes  
 Créez une instance de cette classe dans les versions debug de vos services ou applications d'envoyer des rapports de débogage vers un canal nommé.  Les rapports de débogage sont générés en appelant [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) ou à l'aide d'un wrapper pour cette fonction telle que les macros d' [ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md) et d' [ATLASSERT](../Topic/ATLASSERT.md) .  
  
 L'utilisation de cette classe vous permet de déboguer interactivement des composants en [stations de fenêtre](http://msdn.microsoft.com/library/windows/desktop/ms687096)non interactif.  
  
 Notez que les rapports de débogage sont envoyés en utilisant le contexte de sécurité sous\-jacent du thread.  L'emprunt d'identité est désactivé de façon temporaire afin que les rapports de débogage peuvent être affichés dans les cas où l'emprunt d'identité de bas utilisateur de privilège nécessaire, comme dans les applications Web.  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)
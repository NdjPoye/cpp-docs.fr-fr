---
title: "CHotKeyCtrl Class | Microsoft Docs"
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
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl class"
  - "hot key controls"
  - "Windows common controls [C++], CHotKeyCtrl"
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHotKeyCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle commun de touche d'accès rapide windows.  
  
## Syntaxe  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](../Topic/CHotKeyCtrl::CHotKeyCtrl.md)|Construit un objet `CHotKeyCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHotKeyCtrl::Create](../Topic/CHotKeyCtrl::Create.md)|Crée un contrôle de touche d'accès rapide et l'attache à un objet d' `CHotKeyCtrl` .|  
|[CHotKeyCtrl::CreateEx](../Topic/CHotKeyCtrl::CreateEx.md)|Crée un contrôle de touche d'accès rapide avec les styles étendus par windows spécifiées et l'attache à un objet d' `CHotKeyCtrl` .|  
|[CHotKeyCtrl::GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md)|Récupère le code de clé virtuelle et les indicateurs de touches de modification d'une touche d'accès rapide pour un contrôle de touche d'accès rapide.|  
|[CHotKeyCtrl::GetHotKeyName](../Topic/CHotKeyCtrl::GetHotKeyName.md)|Extrait le nom de la clé, dans le jeu de caractères local, assigné à une touche d'accès rapide.|  
|[CHotKeyCtrl::GetKeyName](../Topic/CHotKeyCtrl::GetKeyName.md)|Extrait le nom de la clé, dans le jeu de caractères local, assigné au code de clé virtuelle spécifié.|  
|[CHotKeyCtrl::SetHotKey](../Topic/CHotKeyCtrl::SetHotKey.md)|Définit la combinaison de touches d'accès rapide pour un contrôle de touche d'accès rapide.|  
|[CHotKeyCtrl::SetRules](../Topic/CHotKeyCtrl::SetRules.md)|Définit les combinaisons valides et la combinaison par défaut de modificateur pour un contrôle de touche d'accès rapide.|  
  
## Notes  
 Un « contrôle de touche d'accès rapide » est une fenêtre qui permet à l'utilisateur de créer une touche d'accès rapide.  Une « touche d'accès rapide » est une combinaison de touches que l'utilisateur peut cliquer pour exécuter une action rapidement.  \(Par exemple, un utilisateur peut créer une touche d'accès rapide qui lance une fenêtre spécifiée et l'apporte au début de l'ordre de plan.\) Le contrôle de touche d'accès rapide affiche les choix de l'utilisateur et les garantit que l'utilisateur sélectionne une combinaison de touches valide.  
  
 Ce contrôle \(et par conséquent la classe d' `CHotKeyCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 Lorsque l'utilisateur a sélectionné une combinaison de touches, l'application peut récupérer la combinaison de touches spécifiée du contrôle et utiliser le message de **WM\_SETHOTKEY** pour installer la touche d'accès rapide dans le système.  Chaque fois que l'utilisateur appuie sur la touche d'accès rapide ensuite, d'une partie du système, la fenêtre spécifiée dans le message de **WM\_SETHOTKEY** reçoit un message d' `WM_SYSCOMMAND` spécifiant **SC\_HOTKEY**.  Ce message active la fenêtre qui reçoit.  La touche d'accès rapide reste valide jusqu'à ce que l'application qui a appelé des sorties de **WM\_SETHOTKEY** .  
  
 Ce mécanisme est différent du support de touche d'accès rapide qui dépend du message de **WM\_HOTKEY** et les fenêtres [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) et [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) s'exécute.  
  
 Pour plus d'informations sur l'utilisation `CHotKeyCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
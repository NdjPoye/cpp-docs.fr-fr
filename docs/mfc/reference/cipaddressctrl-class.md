---
title: "CIPAddressCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CIPAddressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIPAddressCtrl class"
  - "contrôles communs, Internet Explorer 4.0"
  - "Internet address edit box"
  - "Internet Explorer 4.0 common controls"
  - "Internet protocol address box"
  - "IP address control"
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CIPAddressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle adresses IP communs windows.  
  
## Syntaxe  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](../Topic/CIPAddressCtrl::CIPAddressCtrl.md)|Construit un objet `CIPAddressCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CIPAddressCtrl::ClearAddress](../Topic/CIPAddressCtrl::ClearAddress.md)|Efface le contenu du contrôle adresses IP.|  
|[CIPAddressCtrl::Create](../Topic/CIPAddressCtrl::Create.md)|Crée un contrôle adresses IP et l'attache à un objet d' `CIPAddressCtrl` .|  
|[CIPAddressCtrl::CreateEx](../Topic/CIPAddressCtrl::CreateEx.md)|Crée un contrôle adresses IP avec les styles étendus par windows spécifiées et l'attache à un objet d' `CIPAddressCtrl` .|  
|[CIPAddressCtrl::GetAddress](../Topic/CIPAddressCtrl::GetAddress.md)|Récupère les valeurs d'adresses pour les quatre champs dans le contrôle adresses IP.|  
|[CIPAddressCtrl::IsBlank](../Topic/CIPAddressCtrl::IsBlank.md)|Détermine si tous les champs dans le contrôle adresses IP sont vides.|  
|[CIPAddressCtrl::SetAddress](../Topic/CIPAddressCtrl::SetAddress.md)|Définit les valeurs d'adresses pour les quatre champs dans le contrôle adresses IP.|  
|[CIPAddressCtrl::SetFieldFocus](../Topic/CIPAddressCtrl::SetFieldFocus.md)|Place le focus clavier au champ spécifié dans le contrôle adresses IP.|  
|[CIPAddressCtrl::SetFieldRange](../Topic/CIPAddressCtrl::SetFieldRange.md)|Définit l'intervalle dans le champ spécifié dans le contrôle adresses IP.|  
  
## Notes  
 Un contrôle adresses IP, un contrôle similaire à un contrôle d'édition, vous permet d'entrer et manipuler une adresse numérique au format integration \(IP\) process protocole Internet.  
  
 Ce contrôle \(et par conséquent la classe d' `CIPAddressCtrl` \) est disponible uniquement aux programmes s'exécutant sous Microsoft Internet Explorer 4,0 et versions ultérieures.  Il est également disponible sous des versions ultérieures de windows et de Windows NT.  
  
 Pour plus d'informations générales sur le contrôle adresses IP, consultez [Contrôles adresses IP](http://msdn.microsoft.com/library/windows/desktop/bb761372) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
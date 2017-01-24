---
title: "COccManager Class | Microsoft Docs"
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
  - "COccManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conteneurs de contrôles ActiveX (C++), control site"
  - "CNoTrackObject class"
  - "COccManager class"
  - "contrôles personnalisés (MFC), sites"
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COccManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère des sites de contrôle personnalisé ; implémentée par `COleControlContainer` et les objets d' `COleControlSite` .  
  
## Syntaxe  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COccManager::CreateContainer](../Topic/COccManager::CreateContainer.md)|Crée un objet de **COleContainer** .|  
|[COccManager::CreateDlgControls](../Topic/COccManager::CreateDlgControls.md)|Crée des contrôles ActiveX, hébergés par l'objet associé à `COleContainer` .|  
|[COccManager::CreateSite](../Topic/COccManager::CreateSite.md)|Crée un objet `COleClientSite`.|  
|[COccManager::GetDefBtnCode](../Topic/COccManager::GetDefBtnCode.md)|Récupère le code du bouton par défaut.|  
|[COccManager::IsDialogMessage](../Topic/COccManager::IsDialogMessage.md)|Détermine la cible d'un message de dialogue.|  
|[COccManager::IsLabelControl](../Topic/COccManager::IsLabelControl.md)|Détermine si le contrôle spécifié est un contrôle label.|  
|[COccManager::IsMatchingMnemonic](../Topic/COccManager::IsMatchingMnemonic.md)|Détermine si les mnémoniques de actif correspond mnémoniques du contrôle spécifié.|  
|[COccManager::OnEvent](../Topic/COccManager::OnEvent.md)|Tente de gérer l'événement spécifié.|  
|[COccManager::PostCreateDialog](../Topic/COccManager::PostCreateDialog.md)|Libère les ressources allouées pendant la création de dialogue.|  
|[COccManager::PreCreateDialog](../Topic/COccManager::PreCreateDialog.md)|Traite un modèle de boîte de dialogue pour les contrôles ActiveX.|  
|[COccManager::SetDefaultButton](../Topic/COccManager::SetDefaultButton.md)|Bascule l'état par défaut du contrôle spécifié.|  
|[COccManager::SplitDialogTemplate](../Topic/COccManager::SplitDialogTemplate.md)|Sépare les contrôles ActiveX existants des contrôles communs dans le modèle de boîte de dialogue spécifié.|  
  
## Notes  
 La classe de base, **CNoTrackObject**, est une classe de base non documentée \(située dans AFXTLS.H\).  Conçu pour être utilisée par de l'infrastructure MFC, les classes dérivées de la classe de **CNoTrackObject** sont exemptées de la détection des fuites de mémoire.  Il n'est pas recommandé dériviez directement de **CNoTrackObject**.  
  
## Hiérarchie d'héritage  
 `CNoTrackObject`  
  
 `COccManager`  
  
## Configuration requise  
 **Header:** afxocc.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)
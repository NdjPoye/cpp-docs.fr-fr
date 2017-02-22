---
title: "IView Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IView class"
  - "views [MFC]"
  - "vues, classes"
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IView Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente plusieurs méthodes qui utilise pour [CWinFormsView](../../mfc/reference/cwinformsview-class.md) d'envoyer des notifications de vue à un contrôle managé.  
  
## Syntaxe  
  
```  
interface class IView  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IView::OnActivateView](../Topic/IView::OnActivateView.md)|Appelé par les MFC lorsqu'une vue est activée ou désactivée.|  
|[IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md)|Appelé par l'infrastructure après que la vue est d'abord liée au document, mais avant que la vue est initialement affiche.|  
|[IView::OnUpdate](../Topic/IView::OnUpdate.md)|Appelé par les MFC après le document de la vue a été modifié ; cette fonction permet à la vue pour mettre à jour son affichage pour refléter les modifications.|  
  
## Notes  
 `IView` implémente plusieurs méthodes qu' `CWinFormsView` utilise pour envoyer des notifications courantes de vue à un contrôle managé hébergé.  Ce sont [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md), [OnUpdate](../Topic/IView::OnUpdate.md) et [OnActivateView](../Topic/IView::OnActivateView.md).  
  
 `IView` est semblable à [CView](../../mfc/reference/cview-class.md), mais est utilisé uniquement avec les vues managées et des contrôles.  
  
 Pour plus d'informations sur l'utilisation de Windows Forms, consultez l' [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Configuration requise  
 En\-tête : afxwinforms.h \(défini dans l'assembly atlmfc \\ lib \\ mfcmifc80.dll\)  
  
## Voir aussi  
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)
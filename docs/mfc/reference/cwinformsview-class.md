---
title: "CWinFormsView Class | Microsoft Docs"
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
  - "CWinFormsView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsView class"
  - "MFC (C++), prise en charge Windows Forms"
  - "Windows Forms (C++), MFC support"
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit la fonctionnalité générique pour l'hébergement d'un contrôle Windows Forms en tant que vue MFC.  
  
## Syntaxe  
  
```  
class CWinFormsView : public CView;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinFormsView::CWinFormsView](../Topic/CWinFormsView::CWinFormsView.md)|Construit un objet `CWinFormsView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md)|Extrait un pointeur vers le contrôle Windows Forms.|  
  
### Opérateurs publics  
  
|Nom||  
|---------|-|  
|[CWinFormsView::operator Control^](../Topic/CWinFormsView::operator%20Control%5E.md)|Effectue un type en tant que pointeur vers un contrôle Windows Forms.|  
  
## Notes  
 MFC utilise la classe d' `CWinFormsView` pour héberger un contrôle Windows Forms .NET Framework dans une vue MFC.  Le contrôle est un enfant de la vue native et occupe la zone cliente entière de la vue MFC.  Le résultat est semblable à une vue d' `CFormView` , ce qui vous permet de tirer parti du Concepteur Windows Forms et au moment de l'exécution de créer des vues basées sur les formulaires riches.  
  
 Pour plus d'informations sur l'utilisation de Windows Forms, consultez l' [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  L'intégration de MFC Windows Forms fonctionne uniquement dans les projets qui lient dynamiquement avec MFC \(les projets dans lesquels AFXDLL est défini\).  
  
> [!NOTE]
>  CWinFormsView ne prend pas en charge la fenêtre fractionnée MFC \([CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)\).  Actuel uniquement le contrôle separator Windows Forms \(<xref:System.Windows.Forms.Splitter>\) est pris en charge.  
  
## Configuration requise  
 **en\-tête :** afxwinforms.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl Class](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog Class](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)
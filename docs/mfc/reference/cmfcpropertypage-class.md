---
title: "CMFCPropertyPage Class | Microsoft Docs"
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
  - "CMFCPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyPage class"
  - "CMFCPropertyPage::CreateObject method"
  - "CMFCPropertyPage::OnSetActive method"
  - "CMFCPropertyPage::PreTranslateMessage method"
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCPropertyPage` prend en charge l'affichage des menus contextuels sur une page de propriétés.  
  
## Syntaxe  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](../Topic/CMFCPropertyPage::CMFCPropertyPage.md)|Construit un objet `CMFCPropertyPage`.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCPropertyPage::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|`CMFCPropertyPage::OnSetActive`|Cette fonction membre est appelée par l'infrastructure lorsque la page est choisie par l'utilisateur et devient la page active.  \(Substitutions [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md).\)|  
|`CMFCPropertyPage::PreTranslateMessage`|Traduit des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  Pour plus de syntaxe d'informations et de méthode, consultez [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Substitutions `CPropertyPage::PreTranslateMessage`.\)|  
  
## Notes  
 La classe d' `CMFCPropertyPage` représente des pages individuelles d'une feuille de propriétés, sinon appelé une boîte de dialogue d'onglet.  
  
 Utilisez la classe d' `CMFCPropertyPage` avec la classe de [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) .  Pour utiliser des menus d'une page de propriétés, remplacez toutes les occurrences de la classe d' `CPropertyPage` par la classe d' `CMFCPropertyPage` .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## Configuration requise  
 **en\-tête :** afxpropertypage.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet Class](../../mfc/reference/cmfcpropertysheet-class.md)
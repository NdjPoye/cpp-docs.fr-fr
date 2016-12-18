---
title: "CSplitButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitButton class"
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CSplitButton` représente un contrôle bouton partagé.  Le contrôle bouton partagé est le comportement par défaut lorsqu'un utilisateur clique sur la majeure partie du bouton, et affiche un menu déroulant lorsqu'un utilisateur clique sur la flèche déroulante du bouton.  
  
## Syntaxe  
  
```  
class CSplitButton : public CButton  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSplitButton::CSplitButton](../Topic/CSplitButton::CSplitButton.md)|Construit un objet `CSplitButton`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSplitButton::Create](../Topic/CSplitButton::Create.md)|Crée un contrôle bouton partagé avec les styles spécifiés et l'attache à l'objet actuel d' `CSplitButton` .|  
|[CSplitButton::SetDropDownMenu](../Topic/CSplitButton::SetDropDownMenu.md)|Définit la zone déroulante qui s'affiche lorsqu'un utilisateur clique sur la flèche de déroulement du contrôle actuel de bouton partagé.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CSplitButton::OnDropDown](../Topic/CSplitButton::OnDropDown.md)|Traite la notification d' `BCN_DROPDOWN` que le système envoie lorsqu'un utilisateur clique sur la flèche de déroulement du contrôle actuel de bouton partagé.|  
  
## Notes  
 La classe d' `CSplitButton` est dérivée de la classe de [CButton](../../mfc/reference/cbutton-class.md) .  Le contrôle bouton partagé est un contrôle bouton dont le style est `BS_SPLITBUTTON`.  Il affiche un menu personnalisé lorsqu'un utilisateur clique sur la flèche déroulante.  Pour plus d'informations, consultez les styles d' `BS_SPLITBUTTON` et d' `BS_DEFSPLITBUTTON` dans [styles des boutons](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 L'illustration suivante représente une boîte de dialogue qui contient un contrôle pager et \(1\) un contrôle bouton partagé.  \(2\) La flèche de déroulement a déjà été cliqué et \(3\) le sous\-menu s'affiche.  
  
 ![Dialogue avec un bouton partagé et un contrôle pager.](../../mfc/reference/media/splitbutton_pager.png "SplitButton\_Pager")  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## Configuration requise  
 **en\-tête :** afxcmn.h  
  
 Cette classe est prise en [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] et versions ultérieures.  
  
 Les spécifications supplémentaires pour cette classe sont décrites dans [Configuration requise pour les contrôles communs Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
## Voir aussi  
 [CSplitButton Class](../../mfc/reference/csplitbutton-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)
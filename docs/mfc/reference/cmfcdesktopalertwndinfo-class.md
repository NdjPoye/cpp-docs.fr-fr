---
title: "CMFCDesktopAlertWndInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDesktopAlertWndInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndInfo class"
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCDesktopAlertWndInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe `CMFCDesktopAlertWndInfo` est utilisée avec [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md).  Elle spécifie les contrôles affichés si la fenêtre d'alerte sur le Bureau apparaît.  
  
## Syntaxe  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator\=](../Topic/CMFCDesktopAlertWndInfo::operator=.md)||  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md)|Un handle vers l'icône affichée.|  
|[CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md)|L'ID de commande associé à un lien dans la fenêtre d'alerte sur le bureau.|  
|[CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md)|Le texte affiché dans la fenêtre d'alerte sur le bureau.|  
|[CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md)|Le lien qui s'affiche dans la fenêtre d'alerte sur le bureau.|  
  
## Notes  
 La classe d' `CMFCDesktopAlertWndInfo` est passée à la méthode de [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) pour spécifier les éléments affichés dans la boîte de dialogue par défaut de la fenêtre d'alerte sur le Bureau.  La boîte de dialogue par défaut peut contenir trois éléments :  
  
-   Une icône, qui est définie en appelant [CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md).  
  
-   Une étiquette, ou message texte, qui est défini en appelant [CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md).  
  
-   Un lien, qui est défini en appelant [CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md).  Pour définir la commande exécutée lorsque le lien est effectué sur, appelez [CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md).  
  
 Si la boîte de dialogue par défaut n'est pas suffisant, vous pouvez créer une boîte de dialogue personnalisé et le passer à la méthode de [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) au lieu d'utiliser cette classe.  Pour plus d'informations, consultez [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser différents membres de la classe d' `CMFCDesktopAlertWndInfo` .  L'exemple montre comment définir le handle vers l'icône affichée, le texte affiché dans la fenêtre d'alerte sur le bureau, le lien qui s'affiche dans la fenêtre d'alerte sur le bureau, et l'ID de commande qui est associé à un lien dans la fenêtre d'alerte sur le bureau.  Cet exemple est extrait d' [Exemple d'alerte de démonstration de Bureau](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## Configuration requise  
 **en\-tête :** afxDesktopAlertDialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)
---
title: "CPageSetupDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPageSetupDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPageSetupDialog class"
  - "OLE Page Setup dialog box"
  - "mise en page"
  - "Mise en page (boîte de dialogue)"
  - "Print Setup dialog box"
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CPageSetupDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les services fournis par boîte de dialogue commune de disposition windows OLE avec prise en charge supplémentaire pour définir et modifier les marges d'impression.  
  
## Syntaxe  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](../Topic/CPageSetupDialog::CPageSetupDialog.md)|Construit un objet `CPageSetupDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](../Topic/CPageSetupDialog::CreatePrinterDC.md)|Crée un contexte de périphérique pour imprimer.|  
|[CPageSetupDialog::DoModal](../Topic/CPageSetupDialog::DoModal.md)|Affiche la boîte de dialogue et permet l'utilisateur ont une sélection.|  
|[CPageSetupDialog::GetDeviceName](../Topic/CPageSetupDialog::GetDeviceName.md)|Retourne le nom de périphérique d'impression.|  
|[CPageSetupDialog::GetDevMode](../Topic/CPageSetupDialog::GetDevMode.md)|Retourne `DEVMODE` actuel de l'imprimante.|  
|[CPageSetupDialog::GetDriverName](../Topic/CPageSetupDialog::GetDriverName.md)|Retourne le gestionnaire utilisé par l'imprimante.|  
|[CPageSetupDialog::GetMargins](../Topic/CPageSetupDialog::GetMargins.md)|Retourne les paramètres de marge de l'imprimante.|  
|[CPageSetupDialog::GetPaperSize](../Topic/CPageSetupDialog::GetPaperSize.md)|Retourne le format du papier de l'imprimante.|  
|[CPageSetupDialog::GetPortName](../Topic/CPageSetupDialog::GetPortName.md)|Retourne le nom de port de sortie.|  
|[CPageSetupDialog::OnDrawPage](../Topic/CPageSetupDialog::OnDrawPage.md)|Appelé par l'infrastructure pour afficher une image de l'écran d'une page imprimée.|  
|[CPageSetupDialog::PreDrawPage](../Topic/CPageSetupDialog::PreDrawPage.md)|Appelé par l'infrastructure avant d'afficher une image de l'écran d'une page imprimée.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPageSetupDialog::m\_psd](../Topic/CPageSetupDialog::m_psd.md)|Une structure utilisée pour personnaliser un objet d' `CPageSetupDialog` .|  
  
## Notes  
 Cette classe est conçue pour remplacer la boîte de dialogue de configuration de l'impression.  
  
 Pour utiliser un objet d' `CPageSetupDialog` , créez d'abord l'objet à l'aide de le constructeur d' `CPageSetupDialog` .  Une fois la boîte de dialogue a été générée, vous pouvez définir ou modifier les valeurs dans le membre d' `m_psd` pour initialiser les valeurs des contrôles de la boîte de dialogue.  La structure de [m\_psd](../Topic/CPageSetupDialog::m_psd.md) est de type **PAGESETUPDLG**.  
  
 Après avoir initialisé les contrôles de boîte de dialogue, appelez la fonction membre d' `DoModal` pour afficher la boîte de dialogue et autoriser l'utilisateur à des options d'impression sélectionnées.  `DoModal` retourne si l'utilisateur a sélectionné le bouton OK d'**IDOK**\(\) ou d'annulation \(**IDCANCEL**\).  
  
 Si `DoModal` retourne **IDOK**, vous pouvez utiliser plusieurs des fonctions membres d'`CPageSetupDialog`, ou accédez à la donnée membre d' `m_psd` , pour récupérer l'entrée des informations par utilisateur.  
  
> [!NOTE]
>  Après que OLE boîte de dialogue commune de disposition est fermée, aucune modification apportée par l'utilisateur ne sera enregistrée par l'infrastructure.  Elle est jusqu'à l'application elle\-même d'enregistrer toutes les valeurs de cette boîte de dialogue à un emplacement permanent, tel que le membre du document de l'application ou de la classe d'application.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## Configuration requise  
 **Header:** afxdlgs.h  
  
## Voir aussi  
 [exemple MFC WORDPAD](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
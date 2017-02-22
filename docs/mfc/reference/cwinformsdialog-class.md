---
title: "CWinFormsDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinFormsDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsDialog class"
  - "MFC (C++), prise en charge Windows Forms"
  - "Windows Forms (C++), MFC support"
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CWinFormsDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour une classe de boîte de dialogue MFC qui héberge un contrôle utilisateur Windows Forms.  
  
## Syntaxe  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
   public CDialog  
```  
  
#### Paramètres  
 `TManagedControl`  
 Le contrôle utilisateur .NET Framework à afficher dans l'application MFC.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](../Topic/CWinFormsDialog::CWinFormsDialog.md)|Construit un objet `CWinFormsDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinFormsDialog::GetControl](../Topic/CWinFormsDialog::GetControl.md)|Extrait une référence au contrôle utilisateur Windows Forms.|  
|[CWinFormsDialog::GetControlHandle](../Topic/CWinFormsDialog::GetControlHandle.md)|Récupère un handle de fenêtre vers le contrôle utilisateur Windows Forms.|  
|[CWinFormsDialog::OnInitDialog](../Topic/CWinFormsDialog::OnInitDialog.md)|Initialise la boîte de dialogue MFC en créant et en hébergeant un contrôle utilisateur Windows Forms sur.|  
  
### Opérateurs publics  
  
|Nom||  
|---------|-|  
|[CWinFormsDialog::operator \-\>](../Topic/CWinFormsDialog::operator%20-%3E.md)|Remplace [CWinFormsDialog::GetControl](../Topic/CWinFormsDialog::GetControl.md) dans des expressions.|  
|[CWinFormsDialog::operator TManagedControl^](../Topic/CWinFormsDialog::operator%20TManagedControl%5E.md)|Effectue un type en tant que référence à un contrôle utilisateur Windows Forms.|  
  
## Notes  
 `CWinFormsDialog` est un wrapper pour une classe de boîte de dialogue MFC \([CDialog](../../mfc/reference/cdialog-class.md)\) qui les héberge un contrôle utilisateur Windows Forms \(<xref:System.Windows.Forms.UserControl>\).  Cela permet l'affichage des contrôles du .NET Framework sur une boîte de dialogue modale ou non modale MFC.  
  
 Pour plus d'informations sur l'utilisation de Windows Forms, consultez [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) et le [Hébergement d'un contrôle utilisateur Windows Form en tant que boîte de dialogue MFC](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## Configuration requise  
 **en\-tête :** afxwinforms.h  
  
## Voir aussi  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)
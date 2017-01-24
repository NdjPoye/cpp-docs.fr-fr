---
title: "CFontDialog Class | Microsoft Docs"
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
  - "CFontDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontDialog class"
  - "boîtes de dialogue, polices"
  - "polices"
  - "polices, sélectionner"
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFontDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet de lier une boîte de dialogue de sélection polices à votre application.  
  
## Syntaxe  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFontDialog::CFontDialog](../Topic/CFontDialog::CFontDialog.md)|Construit un objet `CFontDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFontDialog::DoModal](../Topic/CFontDialog::DoModal.md)|Affiche la boîte de dialogue et permet à l'utilisateur d'effectuer une sélection.|  
|[CFontDialog::GetCharFormat](../Topic/CFontDialog::GetCharFormat.md)|Extrait la mise en forme des caractères de la police sélectionnée.|  
|[CFontDialog::GetColor](../Topic/CFontDialog::GetColor.md)|Retourne la couleur de la police sélectionnée.|  
|[CFontDialog::GetCurrentFont](../Topic/CFontDialog::GetCurrentFont.md)|Assigne les caractéristiques de police sélectionnée à une structure d' `LOGFONT` .|  
|[CFontDialog::GetFaceName](../Topic/CFontDialog::GetFaceName.md)|Retourne le nom de type de police de la police sélectionnée.|  
|[CFontDialog::GetSize](../Topic/CFontDialog::GetSize.md)|Retourne la taille de la police sélectionnée.|  
|[CFontDialog::GetStyleName](../Topic/CFontDialog::GetStyleName.md)|Retourne le nom de style de police sélectionnée.|  
|[CFontDialog::GetWeight](../Topic/CFontDialog::GetWeight.md)|Retourne le poids de la police sélectionnée.|  
|[CFontDialog::IsBold](../Topic/CFontDialog::IsBold.md)|Détermine si la police est en gras.|  
|[CFontDialog::IsItalic](../Topic/CFontDialog::IsItalic.md)|Détermine si la police est en italique.|  
|[CFontDialog::IsStrikeOut](../Topic/CFontDialog::IsStrikeOut.md)|Détermine si la police est affichée avec la biffure.|  
|[CFontDialog::IsUnderline](../Topic/CFontDialog::IsUnderline.md)|Détermine si la police est soulignée.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFontDialog::m\_cf](../Topic/CFontDialog::m_cf.md)|Une structure utilisée pour personnaliser un objet d' `CFontDialog` .|  
  
## Notes  
 Un objet d' `CFontDialog` est une boîte de dialogue avec une liste des polices actuellement installées dans le système.  L'utilisateur peut sélectionner une police particulière de la liste, et cette sélection est ensuite effectuée une connexion à l'application.  
  
 Pour construire un objet d' `CFontDialog` , utilisez le constructeur fourni ou dériver une nouvelle sous\-classe et utiliser votre propre constructeur personnalisé.  
  
 Une fois qu'un objet d' `CFontDialog` construit, vous pouvez utiliser la structure d' `m_cf` pour initialiser les valeurs ou les états des contrôles dans la boîte de dialogue.  La structure de [m\_cf](../Topic/CFontDialog::m_cf.md) est de type [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832).  Pour plus d'informations sur cette structure, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Après avoir initialisé les contrôles de l'objet dialog, appelez la fonction membre d' `DoModal` pour afficher la boîte de dialogue et permettre à l'utilisateur de sélectionner une police.  `DoModal` retourne si l'utilisateur a sélectionné le bouton OK d'**IDOK**\(\) ou d'annulation \(**IDCANCEL**\).  
  
 Si `DoModal` retourne **IDOK**, vous pouvez utiliser l'une des fonctions membres d'`CFontDialog` pour récupérer l'entrée des informations par utilisateur.  
  
 Vous pouvez utiliser la fonction de [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) windows pour déterminer si une erreur s'est produite pendant l'initialisation de la boîte de dialogue et pour en savoir plus sur l'erreur.  Pour plus d'informations sur cette fonction, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CFontDialog` repose sur le fichier de COMMDLG.DLL fourni avec les versions de Windows 3,1 et versions ultérieures.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe d' `CFontDialog`, fournissez un modèle de boîte de dialogue personnalisé, puis ajoutez une table des messages pour traiter les messages de notification des contrôles étendus.  Tous les messages non\-traités doivent être passés à la classe de base.  
  
 Personnaliser la fonction de raccordement n'est pas obligatoire.  
  
 Pour plus d'informations sur l'utilisation `CFontDialog`, consultez [Classes de boîte de dialogue courantes](../../mfc/common-dialog-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## Configuration requise  
 **Header:** afxdlgs.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
---
title: "CColorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColorDialog class"
  - "couleurs, boîte de dialogue"
  - "boîtes de dialogue, couleurs"
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet de lier une boîte de dialogue de couleur\- sélection à votre application.  
  
## Syntaxe  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CColorDialog::CColorDialog](../Topic/CColorDialog::CColorDialog.md)|Construit un objet `CColorDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CColorDialog::DoModal](../Topic/CColorDialog::DoModal.md)|Affiche une boîte de dialogue de couleurs et permet à l'utilisateur d'effectuer une sélection.|  
|[CColorDialog::GetColor](../Topic/CColorDialog::GetColor.md)|Retourne une structure de **COLORREF** contenant les valeurs de la couleur sélectionnée.|  
|[CColorDialog::GetSavedCustomColors](../Topic/CColorDialog::GetSavedCustomColors.md)|Récupère des couleurs personnalisées créées par l'utilisateur.|  
|[CColorDialog::SetCurrentColor](../Topic/CColorDialog::SetCurrentColor.md)|Force la sélection de couleurs actuelle à la couleur spécifiée.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CColorDialog::OnColorOK](../Topic/CColorDialog::OnColorOK.md)|Substitution pour valider la couleur entrée dans la boîte de dialogue.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CColorDialog::m\_cc](../Topic/CColorDialog::m_cc.md)|Une structure utilisée pour personnaliser les paramètres de la boîte de dialogue.|  
  
## Notes  
 Un objet d' `CColorDialog` est une boîte de dialogue avec une liste de couleurs qui sont définies pour le système d'affichage.  L'utilisateur peut sélectionner ou créer une couleur particulière de la liste, qui est ensuite effectuée une connexion à l'application lorsque la boîte de dialogue se ferme.  
  
 Pour construire un objet d' `CColorDialog` , utilisez le constructeur fourni ou dériver une nouvelle classe et utiliser votre propre constructeur personnalisé.  
  
 Une fois la boîte de dialogue a été générée, vous pouvez définir ou modifier les valeurs dans la structure de[m\_cc](../Topic/CColorDialog::m_cc.md) pour initialiser les valeurs des contrôles de la boîte de dialogue.  La structure d' `m_cc` est de type [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 Après avoir initialisé les contrôles de la boîte de dialogue, appelez la fonction membre d' `DoModal` pour afficher la boîte de dialogue et permettre à l'utilisateur de sélectionner une couleur.  `DoModal` retourne la sélection de l'utilisateur de la boîte de dialogue OK \(**IDOK**\) ou du bouton cancel \(**IDCANCEL**\).  
  
 Si `DoModal` retourne **IDOK**, vous pouvez utiliser l'une des fonctions membres d'`CColorDialog` pour récupérer l'entrée des informations par utilisateur.  
  
 Vous pouvez utiliser la fonction de [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) windows pour déterminer si une erreur s'est produite pendant l'initialisation de la boîte de dialogue et pour en savoir plus sur l'erreur.  
  
 `CColorDialog` repose sur le fichier de COMMDLG.DLL fourni avec les versions de Windows 3,1 et versions ultérieures.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe d' `CColorDialog`, fournissez un modèle de boîte de dialogue personnalisé, puis ajoutez une table des messages pour traiter les messages de notification des contrôles étendus.  Tous les messages non\-traités doivent être passés à la classe de base.  
  
 Personnaliser la fonction de raccordement n'est pas obligatoire.  
  
> [!NOTE]
>  Sur certaines installations l'objet d' `CColorDialog` n'affiche pas avec un arrière\-plan gris si vous avez utilisé l'infrastructure pour effectuer d'autres objets d' `CDialog` griser.  
  
 Pour plus d'informations sur l'utilisation `CColorDialog`, consultez [Classes de boîte de dialogue courantes](../../mfc/common-dialog-classes.md)  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## Configuration requise  
 **Header:** afxdlgs.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [DRAWCLI exemple MFC](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
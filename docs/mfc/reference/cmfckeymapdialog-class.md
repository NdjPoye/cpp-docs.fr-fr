---
title: "CMFCKeyMapDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCKeyMapDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCKeyMapDialog class"
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCKeyMapDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCKeyMapDialog` prend un contrôle qui mappe des commandes aux touches du clavier.  
  
## Syntaxe  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](../Topic/CMFCKeyMapDialog::CMFCKeyMapDialog.md)|Construit un objet `CMFCKeyMapDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCKeyMapDialog::DoModal](../Topic/CMFCKeyMapDialog::DoModal.md)|Affiche une boîte de dialogue de mappage de clavier.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](../Topic/CMFCKeyMapDialog::FormatItem.md)|Appelé par l'infrastructure pour générer une chaîne qui décrit un mappage principal.  Par défaut, la chaîne contient le nom de la commande, les touches de raccourci utilisées, et la description de touches de raccourci.|  
|[CMFCKeyMapDialog::GetCommandKeys](../Topic/CMFCKeyMapDialog::GetCommandKeys.md)|Extrait une chaîne qui contient une liste de touches de raccourci associées à la commande spécifiée.|  
|[CMFCKeyMapDialog::OnInsertItem](../Topic/CMFCKeyMapDialog::OnInsertItem.md)|Appelé par l'infrastructure avant qu'un nouvel élément à insérer dans le contrôle de liste interne qui prend en charge le contrôle de mappage de clavier.|  
|[CMFCKeyMapDialog::OnPrintHeader](../Topic/CMFCKeyMapDialog::OnPrintHeader.md)|Appelé par l'infrastructure pour imprimer l'en\-tête du mappage de clavier sur une page.|  
|[CMFCKeyMapDialog::OnPrintItem](../Topic/CMFCKeyMapDialog::OnPrintItem.md)|Appelé par l'infrastructure pour imprimer un élément de mappage de clavier.|  
|[CMFCKeyMapDialog::OnSetColumns](../Topic/CMFCKeyMapDialog::OnSetColumns.md)|Appelé par l'infrastructure pour définir des légendes pour les colonnes dans le contrôle de liste interne qui prend en charge le contrôle de mappage de clavier.|  
|[CMFCKeyMapDialog::PrintKeyMap](../Topic/CMFCKeyMapDialog::PrintKeyMap.md)|Appelé par l'infrastructure lorsqu'un utilisateur clique sur le bouton **copie** .|  
|[CMFCKeyMapDialog::SetColumnsWidth](../Topic/CMFCKeyMapDialog::SetColumnsWidth.md)|Appelé par l'infrastructure pour définir la largeur des colonnes dans le contrôle de liste interne qui prend en charge le contrôle de mappage de clavier.|  
  
## Notes  
 Utilisez la classe d' `CMFCKeyMapDialog` pour implémenter une boîte de dialogue redimensionnable de mappage de clavier.  La boîte de dialogue utilise un contrôle liste view pour afficher les raccourcis clavier et leurs commandes associées.  
  
 Pour utiliser la classe d' `CMFCKeyMapDialog` dans une application, passez un pointeur à la fenêtre frame principale comme paramètre au constructeur d' `CMFCKeyMapDialog` .  Appelez la méthode d' `DoModal` pour démarrer une boîte de dialogue modale.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## Configuration requise  
 **en\-tête :** afxkeymapdialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)
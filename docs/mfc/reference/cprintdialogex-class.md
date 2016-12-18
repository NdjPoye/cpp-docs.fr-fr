---
title: "CPrintDialogEx Class | Microsoft Docs"
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
  - "CPrintDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialogEx class"
  - "Imprimer (boîte de dialogue)"
  - "Print Setup dialog box"
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrintDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les services fournis par la feuille de propriétés d'impression Windows 2000.  
  
## Syntaxe  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](../Topic/CPrintDialogEx::CPrintDialogEx.md)|Construit un objet `CPrintDialogEx`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](../Topic/CPrintDialogEx::CreatePrinterDC.md)|Crée un contexte de périphérique d'imprimante sans afficher la boîte de dialogue d'impression.|  
|[CPrintDialogEx::DoModal](../Topic/CPrintDialogEx::DoModal.md)|Affiche la boîte de dialogue et permet à l'utilisateur d'effectuer des sélections.|  
|[CPrintDialogEx::GetCopies](../Topic/CPrintDialogEx::GetCopies.md)|Récupère le nombre de copies demandé.|  
|[CPrintDialogEx::GetDefaults](../Topic/CPrintDialogEx::GetDefaults.md)|Récupère les valeurs par défaut du périphérique sans afficher une boîte de dialogue.|  
|[CPrintDialogEx::GetDeviceName](../Topic/CPrintDialogEx::GetDeviceName.md)|Récupère le nom de périphérique d'impression actuellement sélectionné.|  
|[CPrintDialogEx::GetDevMode](../Topic/CPrintDialogEx::GetDevMode.md)|Extrait la structure d' `DEVMODE` .|  
|[CPrintDialogEx::GetDriverName](../Topic/CPrintDialogEx::GetDriverName.md)|Extrait le nom du pilote de périphérique défini par le système d'impression.|  
|[CPrintDialogEx::GetPortName](../Topic/CPrintDialogEx::GetPortName.md)|Extrait le nom du port imprimante actuellement sélectionné.|  
|[CPrintDialogEx::GetPrinterDC](../Topic/CPrintDialogEx::GetPrinterDC.md)|Récupère un handle au contexte de périphérique d'impression.|  
|[CPrintDialogEx::PrintAll](../Topic/CPrintDialogEx::PrintAll.md)|Détermine si imprimer toutes les pages du document.|  
|[CPrintDialogEx::PrintCollate](../Topic/CPrintDialogEx::PrintCollate.md)|Détermine si des copies assemblys sont demandées.|  
|[CPrintDialogEx::PrintCurrentPage](../Topic/CPrintDialogEx::PrintCurrentPage.md)|Détermine si imprimer la page active du document.|  
|[CPrintDialogEx::PrintRange](../Topic/CPrintDialogEx::PrintRange.md)|Détermine si l'impression qu'un intervalle spécifié des pages.|  
|[CPrintDialogEx::PrintSelection](../Topic/CPrintDialogEx::PrintSelection.md)|Détermine si l'impression actuel uniquement les éléments sélectionnés.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintDialogEx::m\_pdex](../Topic/CPrintDialogEx::m_pdex.md)|Une structure utilisée pour personnaliser un objet d' `CPrintDialogEx` .|  
  
## Notes  
 Vous pouvez compter sur l'infrastructure pour gérer de nombreux aspects du processus d'impression de votre application.  Pour plus d'informations sur l'utilisation de l'infrastructure pour gérer des travaux d'impression, consultez l'article [imprimer](../../mfc/printing.md).  
  
 Si votre application doit gérer l'impression sans participation de l'infrastructure, vous pouvez utiliser la classe d' `CPrintDialogEx` « comme est » avec le constructeur fourni, ou vous pouvez dériver votre propre classe de boîte de dialogue d' `CPrintDialogEx` et écrire un constructeur pour l'adapter à vos besoins.  Dans les deux cas, ces boîtes de dialogue se comporteront comme les boîtes de dialogue MFC standard car elles sont dérivées de la classe `CCommonDialog`.  
  
 Pour utiliser un objet d' `CPrintDialogEx` , créez d'abord l'objet à l'aide de le constructeur d' `CPrintDialogEx` .  Une fois la boîte de dialogue a été générée, vous pouvez définir ou modifier les valeurs dans la structure de [m\_pdex](../Topic/CPrintDialogEx::m_pdex.md) pour initialiser les valeurs des contrôles de la boîte de dialogue.  La structure d' `m_pdex` est de type [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844).  Pour plus d'informations sur cette structure, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Si vous ne fournissez pas vos propres handles dans `m_pdex` pour les membres de **hDevMode** et de **hDevNames** , veillez à appeler la fonction Windows **GlobalFree** pour les handles lorsque vous avez terminé avec la boîte de dialogue.  
  
 Après avoir initialisé les contrôles de boîte de dialogue, appelez la fonction membre d' `DoModal` pour afficher la boîte de dialogue et autoriser l'utilisateur à des options d'impression sélectionnées.  Lorsque `DoModal` retourne, vous pouvez déterminer si l'utilisateur a sélectionné OK, vous appliquez, ou bouton Annuler.  
  
 Si l'utilisateur appuyait OK, vous pouvez utiliser les fonctions membres d'`CPrintDialogEx` pour récupérer l'entrée des informations par utilisateur.  
  
 La fonction membre d' `CPrintDialogEx::GetDefaults` est utile pour récupérer les valeurs par défaut actuelles d'imprimante sans afficher une boîte de dialogue.  Cette méthode ne requiert aucune intervention de l'utilisateur.  
  
 Vous pouvez utiliser la fonction de **CommDlgExtendedError** windows pour déterminer si une erreur s'est produite pendant l'initialisation de la boîte de dialogue et pour en savoir plus sur l'erreur.  Pour plus d'informations sur cette fonction, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations sur l'utilisation `CPrintDialogEx`, consultez [Classes de boîte de dialogue courantes](../../mfc/common-dialog-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## Configuration requise  
 **Header:** afxdlgs.h  
  
## Voir aussi  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Structure](../../mfc/reference/cprintinfo-structure.md)
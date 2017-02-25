---
title: "CPrintDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialog class"
  - "Imprimer (boîte de dialogue)"
  - "Print Setup dialog box"
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CPrintDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les services fournis par la boîte de dialogue commune windows pour imprimer.  
  
## Syntaxe  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintDialog::CPrintDialog](../Topic/CPrintDialog::CPrintDialog.md)|Construit un objet `CPrintDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintDialog::CreatePrinterDC](../Topic/CPrintDialog::CreatePrinterDC.md)|Crée un contexte de périphérique d'imprimante sans afficher la boîte de dialogue d'impression.|  
|[CPrintDialog::DoModal](../Topic/CPrintDialog::DoModal.md)|Affiche la boîte de dialogue et permet à l'utilisateur d'effectuer une sélection.|  
|[CPrintDialog::GetCopies](../Topic/CPrintDialog::GetCopies.md)|Récupère le nombre de copies demandé.|  
|[CPrintDialog::GetDefaults](../Topic/CPrintDialog::GetDefaults.md)|Récupère les valeurs par défaut du périphérique sans afficher une boîte de dialogue.|  
|[CPrintDialog::GetDeviceName](../Topic/CPrintDialog::GetDeviceName.md)|Récupère le nom de périphérique d'impression actuellement sélectionné.|  
|[CPrintDialog::GetDevMode](../Topic/CPrintDialog::GetDevMode.md)|Extrait la structure d' `DEVMODE` .|  
|[CPrintDialog::GetDriverName](../Topic/CPrintDialog::GetDriverName.md)|Extrait le nom du pilote d'imprimante actuellement sélectionné.|  
|[CPrintDialog::GetFromPage](../Topic/CPrintDialog::GetFromPage.md)|Extrait la page de début de la plage d'impression.|  
|[CPrintDialog::GetPortName](../Topic/CPrintDialog::GetPortName.md)|Extrait le nom du port imprimante actuellement sélectionné.|  
|[CPrintDialog::GetPrinterDC](../Topic/CPrintDialog::GetPrinterDC.md)|Récupère un handle au contexte de périphérique d'impression.|  
|[CPrintDialog::GetToPage](../Topic/CPrintDialog::GetToPage.md)|Extrait la page final de l'intervalle d'impression.|  
|[CPrintDialog::PrintAll](../Topic/CPrintDialog::PrintAll.md)|Détermine si imprimer toutes les pages du document.|  
|[CPrintDialog::PrintCollate](../Topic/CPrintDialog::PrintCollate.md)|Détermine si des copies assemblys sont demandées.|  
|[CPrintDialog::PrintRange](../Topic/CPrintDialog::PrintRange.md)|Détermine si l'impression qu'un intervalle spécifié des pages.|  
|[CPrintDialog::PrintSelection](../Topic/CPrintDialog::PrintSelection.md)|Détermine si l'impression actuel uniquement les éléments sélectionnés.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPrintDialog::m\_pd](../Topic/CPrintDialog::m_pd.md)|Une structure utilisée pour personnaliser un objet d' `CPrintDialog` .|  
  
## Notes  
 Les boîtes de dialogue courantes d'impression offrent un moyen simple d'implémenter des boîtes de dialogue d'impression et de configuration de l'impression d'une manière conformes aux normes windows.  
  
> [!NOTE]
>  La classe d' `CPrintDialogEx` encapsule les services fournis par la feuille de propriétés d'impression Windows 2000.  Pour plus d'informations consultez la vue d'ensemble de [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) .  
  
 La fonctionnalité d'`CPrintDialog` est remplacée par celle de [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), conçue pour vous donner une boîte de dialogue commune pour la configuration de l'impression et la disposition.  
  
 Vous pouvez compter sur l'infrastructure pour gérer de nombreux aspects du processus d'impression de votre application.  Dans ce cas, l'infrastructure affiche automatiquement la boîte de dialogue commune windows pour imprimer.  Vous pouvez également avoir l'impression de handle d'infrastructure pour votre application sans remplacer la boîte de dialogue courante d'impression avec votre propre boîte de dialogue d'impression.  Pour plus d'informations sur l'utilisation de l'infrastructure pour gérer des travaux d'impression, consultez l'article [imprimer](../../mfc/printing.md).  
  
 Si votre application doit gérer l'impression sans participation de l'infrastructure, vous pouvez utiliser la classe d' `CPrintDialog` « comme est » avec le constructeur fourni, ou vous pouvez dériver votre propre classe de boîte de dialogue d' `CPrintDialog` et écrire un constructeur pour l'adapter à vos besoins.  Dans les deux cas, ces boîtes de dialogue se comporteront comme les boîtes de dialogue MFC standard car elles sont dérivées de la classe `CCommonDialog`.  
  
 Pour utiliser un objet d' `CPrintDialog` , créez d'abord l'objet à l'aide de le constructeur d' `CPrintDialog` .  Une fois la boîte de dialogue a été générée, vous pouvez définir ou modifier les valeurs dans la structure de [m\_pd](../Topic/CPrintDialog::m_pd.md) pour initialiser les valeurs des contrôles de la boîte de dialogue.  La structure d' `m_pd` est de type [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843).  Pour plus d'informations sur cette structure, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Si vous ne fournissez pas vos propres handles dans `m_pd` pour les membres de **hDevMode** et de **hDevNames** , veillez à appeler la fonction Windows **GlobalFree** pour les handles lorsque vous avez terminé avec la boîte de dialogue.  Lorsque vous utilisez l'implémentation de configuration de l'impression de l'infrastructure fournie par `CWinApp::OnFilePrintSetup`, vous ne devez pas libérer les handles.  Les handles sont mis à jour par `CWinApp` et est libéré dans le destructeur d'`CWinApp`.  Il n'est nécessaire de libérer les handles lors de l'utilisation `CPrintDialog` autonome.  
  
 Après avoir initialisé les contrôles de boîte de dialogue, appelez la fonction membre d' `DoModal` pour afficher la boîte de dialogue et autoriser l'utilisateur à des options d'impression sélectionnées.  `DoModal` retourne si l'utilisateur a sélectionné le bouton OK d'**IDOK**\(\) ou d'annulation \(**IDCANCEL**\).  
  
 Si `DoModal` retourne **IDOK**, vous pouvez utiliser l'une des fonctions membres d'`CPrintDialog` pour récupérer l'entrée des informations par utilisateur.  
  
 La fonction membre d' `CPrintDialog::GetDefaults` est utile pour récupérer les valeurs par défaut actuelles d'imprimante sans afficher une boîte de dialogue.  Cette fonction membre ne requiert aucune intervention de l'utilisateur.  
  
 Vous pouvez utiliser la fonction de **CommDlgExtendedError** windows pour déterminer si une erreur s'est produite pendant l'initialisation de la boîte de dialogue et pour en savoir plus sur l'erreur.  Pour plus d'informations sur cette fonction, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CPrintDialog` repose sur le fichier de COMMDLG.DLL fourni avec les versions de Windows 3,1 et versions ultérieures.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe d' `CPrintDialog`, fournissez un modèle de boîte de dialogue personnalisé, puis ajoutez une table des messages pour traiter les messages de notification des contrôles étendus.  Tous les messages non\-traités doivent être passés en fonction de la classe de base.  Personnaliser la fonction de raccordement n'est pas obligatoire.  
  
 Pour traiter le même selon que de message différemment la boîte de dialogue est copie ou configuration de l'impression, vous devez dériver une classe pour chaque boîte de dialogue.  Vous devez substituer la fonction d' **AttachOnSetup** windows, qui gère la création d'une boîte de dialogue lorsque le bouton de configuration de l'impression est sélectionné dans une boîte de dialogue d'impression.  
  
 Pour plus d'informations sur l'utilisation `CPrintDialog`, consultez [Classes de boîte de dialogue courantes](../../mfc/common-dialog-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## Configuration requise  
 **Header:** afxdlgs.h  
  
## Voir aussi  
 [DIBLOOK exemple MFC](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Structure](../../mfc/reference/cprintinfo-structure.md)
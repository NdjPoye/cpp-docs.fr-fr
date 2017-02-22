---
title: "CMFCEditBrowseCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCEditBrowseCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCEditBrowseCtrl class"
  - "CMFCEditBrowseCtrl constructor"
  - "CMFCEditBrowseCtrl::PreTranslateMessage method"
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCEditBrowseCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCEditBrowseCtrl` prend en charge la modification parcourir le contrôle, qui est une zone de texte modifiable qui contient également un bouton Parcourir.  Lorsque l'utilisateur clique sur le bouton Parcourir, le contrôle exécute une action personnalisée ou affiche une boîte de dialogue standard qui contient un explorateur de fichiers ou une recherche des dossiers.  
  
## Syntaxe  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Constructeur par défaut.|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md)|Active ou désactive \(les\) masque le bouton Parcourir.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFileBrowseButton.md)|Active le bouton Parcourir et met la modification parcourir le contrôle en *mode de navigation de fichier* .|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFolderBrowseButton.md)|Active le bouton Parcourir et met la modification parcourir le contrôle en *mode de navigation de dossier* .|  
|[CMFCEditBrowseCtrl::GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md)|Retourne le mode de navigation actuel.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](../Topic/CMFCEditBrowseCtrl::OnAfterUpdate.md)|Appelé par l'infrastructure après la modification recherchez le contrôle est mis à jour avec le résultat d'une action rechercher.|  
|[CMFCEditBrowseCtrl::OnBrowse](../Topic/CMFCEditBrowseCtrl::OnBrowse.md)|Appelé par l'infrastructure après l'utilisateur clique sur le bouton Parcourir.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](../Topic/CMFCEditBrowseCtrl::OnChangeLayout.md)|Redessine la modification actuelle parcourir le contrôle.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](../Topic/CMFCEditBrowseCtrl::OnDrawBrowseButton.md)|Appelé par l'infrastructure pour dessiner le bouton Parcourir.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](../Topic/CMFCEditBrowseCtrl::OnIllegalFileName.md)|Appelé par l'infrastructure lorsqu'un nom de fichier non conforme a été écrit dans le contrôle d'édition.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Traduit des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  Pour la syntaxe et plus d'informations, consultez [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](../Topic/CMFCEditBrowseCtrl::SetBrowseButtonImage.md)|Définit une icône personnalisée pour le bouton Parcourir.|  
  
## Notes  
 Utilisez une modification parcourir le contrôle pour sélectionner un nom de fichier ou dossier.  Éventuellement, utilisez le contrôle pour effectuer une action personnalisée comme d'afficher une boîte de dialogue.  Vous pouvez afficher ou ne pas afficher le bouton Parcourir, et vous pouvez appliquer une étiquette personnalisé ou une image sur le bouton.  
  
 *Le mode de navigation* de manipulation parcourir le contrôle détermine s'il affiche un bouton Parcourir et l'action qui se produit lorsque l'utilisateur clique sur le bouton.  Pour plus d'informations, consultez la méthode de [GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md) .  
  
 La classe d' `CMFCEditBrowseCtrl` prend en charge les modes suivants.  
  
 `custom mode`  
 Une action personnalisée est exécutée lorsque l'utilisateur clique sur le bouton Parcourir.  Par exemple, vous pouvez afficher une boîte de dialogue spécifique à l'application.  
  
 `file mode`  
 Une boîte de dialogue standard de sélection de fichier s'affiche lorsque l'utilisateur clique sur le bouton Parcourir.  
  
 `folder mode`  
 Une boîte de dialogue standard de sélection de dossier s'affiche lorsque l'utilisateur clique sur le bouton Parcourir.  
  
## " Comment " : Spécifiez une modification parcourir le contrôle  
 Exécutez les étapes suivantes pour incorporer une modification parcourir le contrôle dans votre application :  
  
1.  Si vous souhaitez implémenter un mode de navigation personnalisé, dérivez votre propre classe de la classe d' `CMFCEditBrowseCtrl` puis remplacez la méthode d' [CMFCEditBrowseCtrl::OnBrowse](../Topic/CMFCEditBrowseCtrl::OnBrowse.md) .  Dans la méthode substituée, exécutez une action Parcourir personnalisé et mettre à jour la modification parcourir le contrôle avec le résultat.  
  
2.  Incluez ou l'objet d' `CMFCEditBrowseCtrl` ou la modification dérivée parcourent l'objet contrôle dans l'objet window parent.  
  
3.  Si vous utilisez **Assistant Classe** pour créer une boîte de dialogue, ajoutez un contrôle d'édition \(`CEdit`\) au formulaire de boîte de dialogue.  En outre, ajoutez une variable pour accéder au contrôle dans votre fichier d'en\-tête.  Dans le fichier d'en\-tête, remplacez le type de la variable d' `CEdit` par `CMFCEditBrowseCtrl`.  La modification parcourir le contrôle sera créée automatiquement.  Si vous n'utilisez pas **Assistant Classe**, ajoutez une variable d' `CMFCEditBrowseCtrl` à votre fichier d'en\-tête puis appelez sa méthode d' `Create` .  
  
4.  Si vous ajoutez une modification recherchez le contrôle à une boîte de dialogue, utilisez l'outil **ClassWizard** pour installer l'échange de données.  
  
5.  Appelez la méthode d' [EnableFolderBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFolderBrowseButton.md), d' [EnableFileBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFileBrowseButton.md), ou d' [EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md) pour définir le mode de navigation et afficher le bouton Parcourir.  Appelez la méthode de [GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md) pour obtenir le mode de navigation actuel.  
  
6.  Pour fournir une icône personnalisée pour le bouton Parcourir, appelez la méthode de [SetBrowseButtonImage](../Topic/CMFCEditBrowseCtrl::SetBrowseButtonImage.md) ou remplacez la méthode d' [OnDrawBrowseButton](../Topic/CMFCEditBrowseCtrl::OnDrawBrowseButton.md) .  
  
7.  Pour supprimer le bouton Parcourir de la modification recherchez le contrôle, appelez la méthode d' [EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md) avec le jeu de paramètres d' `bEnable` à `FALSE`.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## Exemple  
 L'exemple suivant montre comment utiliser deux méthodes dans la classe d' `CMFCEditBrowseCtrl` : `EnableFolderBrowseButton` et `EnableFileBrowseButton`.  Cet exemple fait partie de [Nouvel exemples de contrôles](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/CPP/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/CPP/cmfceditbrowsectrl-class_2.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxeditbrowsectrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)
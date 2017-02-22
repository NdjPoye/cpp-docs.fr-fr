---
title: "CFindReplaceDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFindReplaceDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFindReplaceDialog class"
  - "Find/Replace dialog box"
  - "remplacer du texte"
  - "remplacer du texte, CFindReplaceDialog class"
  - "recherches de texte, CFindReplaceDialog class"
  - "recherches de texte, remplacer du texte"
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CFindReplaceDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet d'implémenter la recherche standard de chaîne\/substitue les boîtes de dialogue dans votre application.  
  
## Syntaxe  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](../Topic/CFindReplaceDialog::CFindReplaceDialog.md)|Appelez cette fonction pour construire un objet d' `CFindReplaceDialog` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFindReplaceDialog::Create](../Topic/CFindReplaceDialog::Create.md)|Crée et affiche une boîte de dialogue d' `CFindReplaceDialog` .|  
|[CFindReplaceDialog::FindNext](../Topic/CFindReplaceDialog::FindNext.md)|Appelez cette fonction pour déterminer si l'utilisateur souhaite rechercher l'occurrence suivante de la chaîne de recherche.|  
|[CFindReplaceDialog::GetFindString](../Topic/CFindReplaceDialog::GetFindString.md)|Appelez cette fonction pour extraire la chaîne actuelle de recherche.|  
|[CFindReplaceDialog::GetNotifier](../Topic/CFindReplaceDialog::GetNotifier.md)|Appelez cette fonction pour récupérer la structure de **FINDREPLACE** dans votre gestionnaire de messages stocké.|  
|[CFindReplaceDialog::GetReplaceString](../Topic/CFindReplaceDialog::GetReplaceString.md)|Appelez cette fonction pour extraire le actuel substituent la chaîne.|  
|[CFindReplaceDialog::IsTerminating](../Topic/CFindReplaceDialog::IsTerminating.md)|Appelez cette fonction pour déterminer si la boîte de dialogue se termine.|  
|[CFindReplaceDialog::MatchCase](../Topic/CFindReplaceDialog::MatchCase.md)|Appelez cette fonction pour déterminer si l'utilisateur souhaite faire correspondre le cas de la chaîne de recherche exactement.|  
|[CFindReplaceDialog::MatchWholeWord](../Topic/CFindReplaceDialog::MatchWholeWord.md)|Appelez cette fonction pour déterminer si l'utilisateur souhaite rechercher des mots entiers uniquement.|  
|[CFindReplaceDialog::ReplaceAll](../Topic/CFindReplaceDialog::ReplaceAll.md)|Appelez cette fonction pour déterminer si l'utilisateur souhaite toutes les occurrences de la chaîne à remplacer.|  
|[CFindReplaceDialog::ReplaceCurrent](../Topic/CFindReplaceDialog::ReplaceCurrent.md)|Appelez cette fonction pour déterminer si l'utilisateur souhaite le mot actuel à remplacer.|  
|[CFindReplaceDialog::SearchDown](../Topic/CFindReplaceDialog::SearchDown.md)|Appelez cette fonction pour déterminer si l'utilisateur souhaite la recherche pour continuer dans une direction de haut en bas.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFindReplaceDialog::m\_fr](../Topic/CFindReplaceDialog::m_fr.md)|Une structure utilisée pour personnaliser un objet d' `CFindReplaceDialog` .|  
  
## Notes  
 Contrairement aux autres boîtes de dialogue courantes de windows, les objets d' `CFindReplaceDialog` sont non modaux, permettant aux utilisateurs d'interagir avec d'autres fenêtres pendant qu'ils sont à l'écran.  Il existe deux types d'objets d' `CFindReplaceDialog` : Les boîtes de dialogue recherche et la zone rechercher\/substituent les boîtes de dialogue.  Bien que les boîtes de dialogue permettent l'utilisateur à la recherche d'entrée et de la zone rechercher\/remplacer des chaînes, ils ne satisfont pas les fonctions de recherche ou de substitutions l'une des.  Vous devez ajouter ces derniers à l'application.  
  
 Pour construire un objet d' `CFindReplaceDialog` , utilisez le constructeur fourni \(sans argument\).  Comme il s'agit d'une boîte de dialogue non modale, allouez l'objet sur le tas à l'aide de l'opérateur **nouveau** , plutôt que sur la pile.  
  
 Une fois qu'un objet d' `CFindReplaceDialog` construit, vous devez appeler la fonction membre de [Create](../Topic/CFindReplaceDialog::Create.md) pour créer et afficher la boîte de dialogue.  
  
 Utilisez la structure de [m\_fr](../Topic/CFindReplaceDialog::m_fr.md) pour initialiser la boîte de dialogue avant d'appeler **Créer**.  La structure d' `m_fr` est de type [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835).  Pour plus d'informations sur cette structure, consultez [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour que la fenêtre parente est avisée de la zone rechercher\/substituez les demandes, vous devez utiliser la fonction de [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) windows et utiliser la macro de table des messages d' [ON\_REGISTERED\_MESSAGE](../Topic/ON_REGISTERED_MESSAGE.md) dans votre fenêtre frame qui gère ce message stocké.  
  
 Vous pouvez déterminer si l'utilisateur a décidé de terminer la boîte de dialogue avec la fonction membre d' `IsTerminating` .  
  
 `CFindReplaceDialog` repose sur le fichier de COMMDLG.DLL fourni avec les versions de Windows 3,1 et versions ultérieures.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe d' `CFindReplaceDialog`, fournissez un modèle de boîte de dialogue personnalisé, puis ajoutez une table des messages pour traiter les messages de notification des contrôles étendus.  Tous les messages non\-traités doivent être passés à la classe de base.  
  
 Personnaliser la fonction de raccordement n'est pas obligatoire.  
  
 Pour plus d'informations sur l'utilisation `CFindReplaceDialog`, consultez [Classes de boîte de dialogue courantes](../../mfc/common-dialog-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## Configuration requise  
 **Header:** afxdlgs.h  
  
## Voir aussi  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)